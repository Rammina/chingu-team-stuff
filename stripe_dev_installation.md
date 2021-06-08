# Stripe CLI & Webhook Installation for Development Environment

<hr>

## Purpose

These are dev environment installation guidelines for using Stripe webhooks and installing Stripe CLI, meant to be used in our team's application, [RestoFund](https://github.com/chingu-voyages/v30-bears-team-07) (for Chingu voyage 30, v30-bears-team-07).
Without completing this process, the server routes will not be able to listen to checkout completion, and the database will not be updated after a checkout.

<hr>

## Instructions

### Install Stripe CLI

Follow the [Stripe CLI installation guide](https://stripe.com/docs/stripe-cli#install) for your operating system. For instance, click the `Windows` option and follow its instructions if you are running a Windows system.

Only steps 1 & 2 are needed to install Stripe CLI.

To check that Stripe is working, run this command on the terminal (on the directory where Stripe was installed):

```bash
stripe status
```

If the installation and setup works, it should return `All services are online.` or a similar message. Otherwise, there is likely a mistake in the installation process.

### Stripe Webhook Listener

Run your server (in this case, on localhost:5000) on a **different terminal window**.

```bash
npm run server
```

Next, set up Stripe CLI to forward events to your local server on a **different terminal window** and on the **directory where Stripe was installed**, so you can test your event handler locally:

```bash
stripe listen --forward-to localhost:5000/stripe/webhook
```

It should return a webhook signing secret in the format of:

```bash
whsec_<VALUE>
```

**Note: If no value like that was returned, there is something wrong done in the installation process.**

Place (or replace if already existing) this in the .env of the / (root) directory:

```bash
STRIPE_ENDPOINT_SECRET=whsec_<VALUE>
```

**Note: replace <VALUE> with the value returned by the Stripe listen command. Make sure to remove the <>**

### Testing Webhook via Checkout

Next, go through Checkout as a customer:

- Click your checkout button (you probably set this up in the Accept a payment guide)
- Fill out your payment form with test data
- Enter 4242 4242 4242 4242 as the card number
- Enter any future date for card expiry
- Enter any 3-digit number for CVV
- Enter any billing ZIP code (90210)
- Click the Pay button

You should see:

- A checkout.session.completed in the stripe listen output
- A print statement from your server’s event logs with the checkout.session.completed event
- Changes in the value of amount_donated after checkout (both in the Project page or in MongoDB)
