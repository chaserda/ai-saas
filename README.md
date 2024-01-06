## Getting Started

First, run the following command

`npm i` or `npm install` to install all dependencies

## Next, Create accounts for environment variables

You will need accounts from the following

- Stripe
- Clerk.js
- OpenAI
- PlanetScale

## Creating your PlanetScale account

You only need to run a free tier server for this application to work, however, you can pay for a higher tier if you would like.

## Update your environment variables

You will need to populate the following environment variables in your .env file with the account keys you made from the previous step

- Your Stripe Secret Key will be under the env var `STRIPE_API_KEY`
- Clerk.js keys will be `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY` and `CLERK_SECRET_KEY`
- Planetscale will be your `DATABASE_URL`
- Your OpenAI API Key will be `OPENAI_API_KEY`
- You will also need a environment variable `NEXT_PUBLIC_APP_URL=http://localhost:3000` or the endpoint your Next.js app is served on
- Lastly, you will need the following environment variables for Clerk:
  - `NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in`
  - `NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up`
  - `NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/dashboard`
  - `NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/dashboard`

## Setup your PrismaDB

The Prisma Schema is already established so in order to properly use it, run the following commands 
- IMPORTANT: Make sure your PlanetScale DB is setup before running this step 
- `npm i @prisma/client`
- `npx prisma db push`
- `npx prisma generate`

You can access a local Prisma client by running
- `npx prisma studio`

## Setup your Stripe Webhook

In order for the PlanetScale to sync with Stripe profiles, you will need to setup your Stripe Webhook. Go to Stripe > Dashboard > Developers > WebHooks

- You will then need to click `Add Endpoint`
- Click `Test in local environment` and run the prompted commands
- After these commands are completed you will be presented a Webhook Key. Put this key in your .env file under `STRIPE_WEBHOOK_SECRET`
- IMPORTANT: You will need to run this listener every time you start up your application.

## Now start up your app in a new terminal!

`npm run dev`

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.
