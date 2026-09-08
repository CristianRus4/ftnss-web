# ftnss site blueprint

## Site jobs

The site explains ftnss, sends users to the App Store, answers support questions,
and discloses health, AI, permission, and purchase behavior. It must present the
product as a general-wellness tool, never as diagnosis, treatment, emergency
support, or a substitute for a clinician.

## Technical shape

The site is committed HTML and CSS with local imagery, favicons, a `CNAME`,
robots file, sitemap, and a small amount of page JavaScript. There is no package
manifest or build step. Preview with a local HTTP server:

```bash
npx serve .
```

The inspected repository has a Nexus documentation workflow but no website
deployment workflow. `CNAME` points at `ftnss.app`, consistent with a GitHub
Pages-style domain, but confirm the actual publishing branch and hosting
configuration before relying on automatic deployment.

## Page topology

- `/`: product landing page, features, comparisons, testimonials, FAQ, and App
  Store calls to action
- `/support/`: public support surface
- `/privacy/`: detailed data, permission, AI-provider, purchase, retention, and
  contact disclosures
- `/download.html`: App Store redirect
- `/robots.txt` and `/sitemap.xml`: crawler discovery
- `/images/`: product screenshots and marketing imagery

There is no tracked public terms page in the inspected site. Do not add a Terms
link that resolves nowhere; make legal-surface ownership an explicit release
decision.

## Product boundary

The app reads selected Apple Health data, writes selected nutrition data after
user interaction, stores profile/preferences and recent chat locally, uses an
App Group for widget projections, and lets widgets query HealthKit. It can add
WeatherKit, location, calendar, photo, camera, and barcode context. RevenueCat
owns premium entitlement state.

AI behavior is provider-dependent:

- Apple Intelligence is conditional on system/device availability and Apple's
  processing model.
- Gemini is cloud processing and may receive the relevant prompt, permitted
  profile, health, photo, barcode, weather, calendar, or other context for the
  active feature after consent.

The website must not simplify this into an unconditional “all data stays on
device” promise. Core local data and HealthKit access may remain on device, while
cloud features necessarily transmit a subset. Similarly, the app is not fully
functional offline when a flow depends on cloud AI, weather, nutrition lookup,
or purchases.

## Integration language

Strava, Garmin, Fitbit, Runna, MyFitnessPal, and similar services may contribute
data to Apple Health when users configure those services. That is indirect
interoperability through HealthKit, not evidence of direct ftnss integrations or
endorsement. Public copy must retain that distinction.

## Trust boundaries

- Never put real Health data, chat text, photos, barcodes, calendar titles,
  profile notes, or location traces in marketing assets or docs.
- Never publish service credentials. The current app embeds AI and nutrition
  service credentials in client source; rotate and move protected calls behind
  a trusted service before describing those integrations as production-secure.
- Claims about scores, recovery, fitness age, sleep, nutrition, or training are
  estimates/general guidance and need uncertainty and medical guardrails.
- Testimonials, ratings, health outcomes, and “evidence based” statements need
  documented substantiation and appropriate context.
