# Payments and subscriptions

When you’re ready to charge for your app—subscriptions, one-time purchases, or usage-based billing, CodeWords connects to Stripe to handle checkout, renewals, and billing management. This page explains what you need, how to set it up, and what happens once payments are live.

### How it works

CodeWords uses Stripe for payment processing. Stripe handles sensitive card data securely, so your app never stores or processes credit card numbers. Your users complete payment on Stripe Checkout, and Stripe notifies your app about billing events through webhooks.

### What you need

Before Cody can set up payments, you’ll need a Stripe account and a few values from the Stripe dashboard.

#### Stripe account

Create an account at Stripe and complete verification so Stripe can pay out to your bank. You’ll provide identity verification and banking details during setup.

#### API keys

Stripe provides two sets of keys:

* **Test keys** for development
* **Live keys** for production

You can find both in **Stripe → Developers → API keys**.

| Key             | Starts with             | Used where                                             | Safe for frontend? |
| --------------- | ----------------------- | ------------------------------------------------------ | ------------------ |
| Publishable key | `pk_test_` / `pk_live_` | Frontend (loads Stripe Checkout)                       | Yes                |
| Secret key      | `sk_test_` / `sk_live_` | Backend only (creates sessions, manages subscriptions) | No                 |

Cody will ask for both. The publishable key is used in the frontend. The secret key is stored as a backend-only environment variable and must never be exposed.

#### Webhook signing secret

Webhooks let Stripe tell your app when something happens: payments succeed, renewals fail, subscriptions cancel, and more.

When Cody creates your webhook endpoint, you’ll add it in **Stripe → Developers → Webhooks**. Stripe will give you a signing secret (starts with `whsec_`) so your app can verify events are genuinely from Stripe.

| Secret                 | Starts with | Purpose                               |
| ---------------------- | ----------- | ------------------------------------- |
| Webhook signing secret | `whsec_`    | Verifies webhook payloads from Stripe |

#### Webhook events to subscribe to

Subscribe to these events for the core subscription lifecycle:

| Event                           | Used for                                            |
| ------------------------------- | --------------------------------------------------- |
| `checkout.session.completed`    | Customer paid—activate access                       |
| `invoice.payment_succeeded`     | Renewal succeeded—extend access                     |
| `invoice.payment_failed`        | Renewal failed—notify and gate access if needed     |
| `customer.subscription.updated` | Plan change or cancellation scheduled—update access |
| `customer.subscription.deleted` | Subscription ended—revoke premium access            |

You can add more events later, but these cover most apps.

#### Products and prices

Create your plans in **Stripe → Products**. Cody needs the **Price ID** (starts with `price_`) for each plan you want to sell (for example: monthly and annual).

### Setting it up

1. **Create your Stripe account and pricing**\
   Sign up, complete verification, and create your product(s) and price(s) in Stripe.
2. **Share your Stripe details with Cody**\
   Provide:
   * Publishable key (`pk_…`)
   * Secret key (`sk_…`)
   * Price ID(s) (`price_…`) for your plans
3. **Cody builds the integration in test mode**\
   Cody sets up:
   * Checkout flow
   * Subscription status handling
   * Billing portal
   * Webhook handler
4. **Add the webhook endpoint in Stripe**\
   In Stripe, create a webhook endpoint pointing to the URL Cody provides, subscribe to the events above, and share the `whsec_…` signing secret with Cody.
5. **Test end-to-end**\
   Use Stripe test cards (for example, `4242 4242 4242 4242`) to simulate:
   * Successful payments
   * Failed renewals
   * Cancellations\
     Confirm your app gates features correctly based on subscription state.
6. **Go live**\
   Replace test keys with live keys. Real payments start flowing immediately.

### The subscription lifecycle

A user starts on a free tier, then upgrades through Stripe Checkout. Subscriptions renew automatically each billing period. Users can update payment methods, view invoices, and manage billing through Stripe’s self-service portal.

If a user cancels, they typically keep access until the end of the current billing period. After that, they return to the free tier. If a renewal fails, Stripe notifies the customer and retries the charge over several days. You can decide how access changes if retries don’t succeed.

### Pricing strategies

* **Freemium** works well for most apps: let users experience value, then charge for high-value actions (exports, integrations, premium features).
* **Free trials** are best when the value is clearer after time (for example, after a week of use).
* **Simple pricing** (one plan) is easiest to sell early. Add tiers later when you learn what customers value.

### Security

Payment security is built into the Stripe model:

* Secret keys and webhook secrets stay server-side as backend environment variables.
* Only the publishable key is used in the browser.
* Card data is handled entirely by Stripe—your app never sees or stores it.
* Webhook signatures are verified before any billing event is processed.
* Everything runs over HTTPS.

### Quick reference: What Cody needs from you

| Item                   | Where to find it               | Example                   |
| ---------------------- | ------------------------------ | ------------------------- |
| Publishable key        | Stripe → Developers → API keys | `pk_test_…` / `pk_live_…` |
| Secret key             | Stripe → Developers → API keys | `sk_test_…` / `sk_live_…` |
| Webhook signing secret | Stripe → Developers → Webhooks | `whsec_…`                 |
| Price ID(s)            | Stripe → Products → Pricing    | `price_…`                 |
