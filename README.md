# Probot Github App

> A GitHub App built with [Probot](https://github.com/probot/probot) - Welcome Comment on new issues.
> Check the Issues tab for the demo run.

## Setup

Getting started - [Probot](https://probot.github.io/docs/development/)

create-probot-app is the best way to start building a new app. It will generate a new app with everything you need to get started and run your app in production.

To get started, run:

```sh
npx create-probot-app my-app
cd my-app
npm install       # Install dependencies
npm start         # Run the bot
```

## Configuring a GitHub App

Follow the guide [here](https://probot.github.io/docs/development/#configuring-a-github-app).

NOTE 1: **Use your machine ip instead of localhost while setting up github app in this step. You can get it by running `hostname -I`**

NOTE 2: **If using bot as an app in turborepo, remove tsc from the build script in `package.json`**


## Local Development

To setup probot for local development, you would need a webhook url for your github app to hit.
You can use ngrok to create a tunnel to your localhost. Suppose your bot runs on localhost:3000, then you can run:

```
ngrok http 3000
```

After executing that command you should see something like this:

    Forwarding      https://9add-49-43-98-101.ngrok-free.app -> http://localhost:3000

**The Default URL for probot is /api/github/webhooks.**
Hence you can use `https://9add-49-43-98-101.ngrok-free.app/api/github/webhooks` as your webhook url in the github app.

## Docker

```sh
# 1. Build container
docker build -t gh-bot .

# 2. Start container
docker run -e APP_ID=<app-id> -e PRIVATE_KEY=<pem-value> gh-bot
```

## Contributing

If you have suggestions for how gh-bot could be improved, or want to report a bug, open an issue! We'd love all and any contributions.

For more, check out the [Contributing Guide](CONTRIBUTING.md).

## License

[ISC](LICENSE) © 2024 Jogeshwar Singh
