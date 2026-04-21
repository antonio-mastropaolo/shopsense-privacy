# Shopsense Privacy Policy

*Last updated: 2026-04-21*

Shopsense is a Chrome extension that runs an AI-driven trust check on an online store when you click its toolbar icon. This document explains exactly what it reads, where that data goes, and what we do not do.

## What Shopsense reads

**Only when you click the Shopsense icon on a specific tab:**

- The URL and hostname of that tab
- The page's title and meta description
- The text content of the footer and the first ~4 KB of the page body
- Product titles and prices visible on the page
- Email addresses, phone numbers, and social-media links visible on the page
- Whether the page appears to be a Shopify store

Shopsense does **not** read any other tab. It does **not** monitor your browsing history. It does **not** run in the background on pages you haven't explicitly asked it to check.

## Where that data goes

When you click "Run trust check", the signals listed above are sent over HTTPS to the Shopsense backend. The backend:

1. Looks up the domain's public registration information (RDAP — a public domain-registry protocol, not a third-party service).
2. Sends the signals to Anthropic's Claude API for analysis (two "analyst" models plus one "judge" model).
3. Returns a score and explanation to your browser.

**No data is persisted on the backend.** Each request is processed and discarded. Anthropic's API data handling is governed by [Anthropic's commercial terms](https://www.anthropic.com/legal/commercial-terms), which prohibit using your data to train models.

## What stays on your device

Your recent-checks history (up to 20 entries) and cached verdicts (24-hour TTL) are stored in `chrome.storage.local` on your machine. This never leaves your browser. You can clear it at any time via the "Clear" button on the recent-checks list, or by uninstalling the extension.

## Payment

If you purchased Shopsense, payment is handled by [ExtensionPay](https://extensionpay.com/) on top of [Stripe](https://stripe.com/). Shopsense never sees or stores your payment-card information. Your email address is used only to restore your purchase across devices.

## Telemetry

If telemetry is enabled in your installed version, Shopsense may send:

- **Error reports** (via Sentry): the error message, stack trace, and a randomly generated install ID. Never the contents of the page you were checking.
- **Anonymous usage events** (via PostHog): which popup screen was opened, whether a check succeeded or failed, and the score band (e.g. "low"). Never the full verdict text, never the hostname of any store you checked.

The install ID is a random UUID generated on first launch, stored locally, and unlinked to any identity. You can reset it by clearing extension storage.

## What Shopsense does NOT do

- **No advertising.** No ad networks. No fingerprinting.
- **No data sale.** We do not and will not sell the data Shopsense collects.
- **No cross-site tracking.** The extension only activates when you click it.
- **No background scraping.** The extension has `activeTab` permission — it reads the page only in response to your click, and only the tab you're on.

## Your rights

- **Access / deletion:** Everything Shopsense stores about you lives in your browser's local storage or in an anonymous install ID. You can delete it all in one click by removing the extension.
- **Contact:** Questions about this policy? Open an issue at https://github.com/antonio-mastropaolo/shopsense-privacy/issues or email the address in the Chrome Web Store listing.

## Changes

If this policy materially changes, the change will be reflected in an extension update and noted at the top of this file with a new date.
