# Telegram bot with MiniApp

> 🛠️ Repo content cloned from the [deno-fresh-web-app]([examples/setups/deno-fresh-web-app at main · grammyjs/examples · GitHub](https://github.com/grammyjs/examples/tree/main/setups/deno-fresh-web-app)) example app.

This repository is the template for a Telegram bot integrated with a MiniApp.

## Technology stack

- Deno: Secure runtime environment for JavaScript and TypeScript applications.

- Fresh: Island architecture based framework for scalable Deno web apps.

- Preact: Lightweight front-end library for user interfaces based on components.

- Grammy: Telegram bot framework.

## Preparation

1. Create a project on [Deno Deploy](https://deno.com/deploy).
2. Set the `TELEGRAM_BOT_TOKEN` variable to your token (this can be done in project’s setting's environment variables).
3. Set the `WEBAPP_URL` variable to your fresh app url (this can be done in project’s setting's environment variables) as `https://<PROJECT_NAME>.deno.dev` (replacing `<...>` with respective values)
4. Set your bot’s webhook url by visiting your new project url `https://<PROJECT_NAME>.deno.dev`
   (replacing `<...>` with respective values). This will automatically set the webhook url to your Deno Deploy subdomain.

### Deploying with GitHub (easy)

5. Push your project to a GitHub repository.
6. Set up GitHub Integration in the project’s settings. Select `main.ts` as
   entry point.
7. You’re done! New versions will be automatically deployed on push.

### Deploying with `deployctl` (advanced)

5. Install [`deployctl`](https://github.com/denoland/deployctl)
6. Create a new [access token](https://dash.deno.com/account#access-tokens). Save it somewhere
7. Run this command to deploy:
   `deployctl deploy --project <PROJECT_NAME> ./main.ts --prod --token <ACCESS_TOKEN>`

## Running the bot and web app locally

> Copy the `.env.example` file to `.env` and set the `TELEGRAM_BOT_TOKEN` variable to your token and the `WEBAPP_URL` variable to a proxy url of your fresh app url as `https://llreoesss.proxy.web.app`. You can use [Ngrok](https://ngrok.com/) or [Cloudflare's TryCloudflare](https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/do-more-with-tunnels/trycloudflare/#using-trycloudflare) to get a free proxy url.

### Running the bot only locally

Run this command in your terminal `deno task bot` to only run the bot locally for development.

### Running the bot and web app locally

Run this command in your terminal `deno task dev` to run the bot and web app locally for development.

Note that by running the bot and/or webapp locally, it will delete the webhook URL and you’ll need to repeat the 3rd step to be able to run the bot on Deno Deploy. To avoid that, please create a test bot and use its token for local development.

## Testing the bot

Use the `/start` command to test the bot. This will display a welcome message and a button to open the web app.
