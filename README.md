# reference-remote-fields-stripe

> Query product and price data from [Stripe](https://stripe.com/docs/api) using GraphCMS [Remote Fields](https://graphcms.com/docs/schema/field-types#remote) 💳

## About

This reference is basic example of Content Federation, using Remote Fields to connect a `PricingPlan` type with third-party product and pricing data from Stripe. A common use case would be to enrich recurring or one-time Stripe products with data from GraphCMS (such as images or additional text content).

Built with [Next.js](https://nextjs.org/) and [Tailwind CSS](https://tailwindcss.com).

## Usage

> This assumes you have already created a GraphCMS project and have an existing Stripe account

1. Clone with repository with [`degit`](https://github.com/Rich-Harris/degit) and install project dependencies.

```bash
npx degit GraphCMS/reference-remote-fields-stripe#main reference-remote-fields-stripe
cd reference-remote-fields-stripe
yarn
```

2. Add a `.env` file by cloning the provided `.env.sample` and providing the required variable values.

```
GRAPHCMS_MIGRATION_TOKEN=
GRAPHCMS_TOKEN=
GRAPHCMS_URL=
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=
STRIPE_SECRET_KEY=
```

2. Build the required GraphCMS schema, including Remote Fields, using the Management SDK. This repository [includes](migration.js) the migration script that was used to bootstrap this project. You can run the provided migration with `yarn migrate`.

3. Populate your GraphCMS project with `PricingPlan` content entries. Be sure you to provide the relevant IDs (`stripeMonthlyPriceId`, `stripeAnnualPriceId`) for the Stripe prices created in your Stripe dashboard.

4. Start the project!

```
yarn dev
```
