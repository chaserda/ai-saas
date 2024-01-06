## Getting Started

First, run the following command

`npm i` or `npm install` to install all dependencies

## Next, Create accounts for environment variables

You will need accounts from the following

- Stripe
- Clerk.js
- OpenAI
- Planetscale

## Update your environment variables

You will need to populate the following environment variables in your .env file with the account keys you made from the previous step

- Your Stripe Secret Key will be under the env var `STRIPE_API_KEY`
- Clerk.js keys will be `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY` and `CLERK_SECRET_KEY`
- Planetscale will be your `DATABASE_URL`
- Your OpenAI API Key will be `OPENAI_API_KEY`
- You will also need a environment variable `NEXT_PUBLIC_APP_URL=http://localhost:3000` or the endpoint your Next.js is served on
- Lastly, you will need the following environment variables for Clerk:
  - `NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in`
  - `NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up`
  - `NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/dashboard`
  - `NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/dashboard`

## Setup your PrismaDB

The Prisma Schema is already established so in order to properly use it, run the following commands ( Make sure your PlanetScale DB is setup before running this step )
- `npm i @prisma/client`
- `npx prisma db push`
- `npx prisma generate`

You can access a local Prima client by running
- `npx prisma studio`

## Now start up your app!

`npm run dev`

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.
