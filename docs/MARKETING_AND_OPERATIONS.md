# ftnss marketing and operations

## Message hierarchy

Lead with a clear daily outcome: ftnss turns permitted Apple Health and user
context into understandable fitness, nutrition, sleep, and recovery guidance.
Then explain the dashboard, coach, logging/planning actions, configurable
widgets, provider choice, and user controls.

Never promise medical accuracy, guaranteed outcomes, complete compatibility,
continuous freshness, or unlimited offline/cloud functionality. Avoid language
that could amplify health anxiety or tell a user to ignore symptoms or
professional advice.

## High-risk claim review

Every health, privacy, AI, or integration claim requires verification against
the app source and a review of these questions:

1. Is the value measured by HealthKit, entered by the user, or derived by ftnss?
2. Is it current, historical, estimated, or potentially stale?
3. Does it require a permission, supported device/OS, Apple Watch, network,
   premium access, or a particular AI provider?
4. What data leaves the device, to which processor, for what purpose, and only
   after what consent?
5. Does the wording clearly remain general wellness rather than medical advice?

The homepage currently uses broad statements such as “your data stays private”
and says the app works offline, while the privacy page correctly describes
Gemini cloud processing and other external services. Qualify the homepage/FAQ
language so the visible summary cannot be read as contradicting the full policy.

## Claim inventory to keep synchronized

- App Store ID and product title
- Minimum supported iOS/device behavior
- Dashboard/card and widget counts
- HealthKit read/write categories
- Apple Watch and indirect third-party data flow through Apple Health
- Gemini and Apple Intelligence availability and consent
- Weather, location, calendar, photo, camera, barcode, and nutrition processing
- RevenueCat premium boundary and purchase restoration
- Local retention, chat history, deletion, and permission controls
- Testimonials, comparative claims, and any scientific/evidence wording

## SEO and accessibility

- Use a static absolute canonical URL. The homepage currently sets canonical
  and social URL from JavaScript; crawlers may see the initial empty value.
- Keep visible FAQ answers and FAQ JSON-LD identical in meaning.
- Keep `SoftwareApplication` data, metadata, sitemap, robots, social cards, and
  App Store links consistent.
- Review headings, landmarks, focus order/visibility, contrast, alternatives,
  reduced motion, responsive layout, and zoom.
- Avoid keyword-led repetition that makes a medical or integration claim sound
  stronger than the product evidence.

## Release checklist

Serve the site locally and verify:

- `/`, `/support/`, `/privacy/`, and `/download.html`;
- App Store ID `6742253667`, all downloads, contact links, and legal navigation;
- mobile/desktop layout, keyboard access, images, favicons, console, and network;
- canonical, metadata, JSON-LD, sitemap, robots, and social previews;
- the complete public claim inventory against the current app build;
- consent and off-device-processing language in both summary copy and policy;
- no real health/user data, credentials, internal prompts, unverified ratings,
  fake testimonials, or diagnostic promises.

Because no website deployment workflow is tracked here, confirm the actual
hosting source/branch before publishing. Verify custom domain, TLS, homepage,
deep routes, redirects, and caches after release. Roll back by restoring the last
known-good commit in the configured hosting system.

## Nexus

The Nexus workflow syncs documentation on pushes to main; it does not deploy the
website. Check publication and Nexus ingestion independently. Local uncommitted
docs cannot appear in Nexus.
