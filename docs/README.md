# ftnss website documentation

This directory documents the public `ftnss.app` marketing, support, and privacy
site. Health and AI copy is release-critical: it must describe what the app
actually reads, writes, derives, stores, and sends off-device.

## Start here

| Work | Read |
| --- | --- |
| Site structure and system boundaries | [Site blueprint](SITE_BLUEPRINT.md) |
| Claims, SEO, privacy, release, or incidents | [Marketing and operations](MARKETING_AND_OPERATIONS.md) |
| App targets, HealthKit, widgets, AI, data, and purchases | [ftnss app blueprint](../../../Apps/ftnss-app/docs/APP_BLUEPRINT.md) |
| Product positioning and guardrails | [ftnss product strategy](../../../Apps/ftnss-app/docs/PRODUCT_STRATEGY.md) |
| Nexus ownership | [Nexus project](nexus/PROJECT.md) and [website operations](nexus/WEBSITE.md) |

## Identity

- Product: **ftnss**
- Canonical domain: `https://ftnss.app`
- App Store ID: `6742253667`
- iOS bundle identifier: `cr.ftnss`
- Public-site source: this repository
- App source: `Apps/ftnss-app`

This repository is authoritative for public marketing, support, privacy,
download, crawler metadata, and media. The app repository is authoritative for
shipped behavior. The Nexus manifest includes `docs/**/*.md`; committed docs
sync after a push to main.
