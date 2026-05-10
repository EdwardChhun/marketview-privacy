---
layout: default
title: MarketView Privacy Policy
---

# MarketView Privacy Policy

_Last updated: 2026-05-09_

MarketView is a personal multi-account retail dashboard. This policy
describes what data the MarketView browser extension and web app
collect, how it is stored, and how it is used.

## What we collect

When you sign in to MarketView and add a retailer account (currently
Target), the extension captures the session credentials your browser
already holds for that retailer:

- Cookies on the retailer's domains
- Auth tokens stored by the retailer in `localStorage` /
  `sessionStorage`
- Order history data fetched from the retailer's own API using your
  captured credentials

We also store the email address and password you use to sign in to
MarketView itself (handled by Supabase Auth).

We do not collect browsing history, data from non-retailer sites, or
analytics about your use of other websites.

## How your retailer data is stored

All retailer session data and order data is encrypted on your device
before it leaves your browser:

- Your MarketView passphrase is stretched with **Argon2id** into a
  key-encryption key (KEK).
- The KEK unwraps a per-user data-encryption key (DEK).
- The DEK encrypts every retailer session blob and order record using
  **XSalsa20-Poly1305** authenticated encryption.

The MarketView server stores only the resulting ciphertext. It cannot
read your retailer cookies, tokens, or orders, and neither can we.
This is sometimes called a "blind store" or "zero-knowledge" design.

## How your data is used

Captured retailer credentials are used only to:

- Log you in to that retailer in your own browser when you switch
  accounts in the dashboard.
- Fetch your own order data from that retailer's API on your behalf.

Order data is shown only to you, in your own dashboard.

## What we do NOT do

- We do not sell your data.
- We do not share your data with third parties for advertising or
  analytics.
- We do not transmit your retailer cookies, tokens, or orders to any
  server in a form we can read.
- We do not access any sites outside the retailers explicitly
  supported by the extension.

## Third-party services

- **Supabase** (database, authentication): stores your encrypted data
  and account email. See
  [supabase.com/privacy](https://supabase.com/privacy) for their
  policy.

## Data deletion

You can delete a retailer account, or your entire MarketView account,
at any time from the dashboard. Deleting your MarketView account
removes all associated encrypted data from our database.

## Contact

Questions about this policy: **your-email@example.com**

## Changes

If this policy changes, the "Last updated" date above will change and
material changes will be announced in the dashboard.
