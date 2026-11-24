# Changelog

All notable changes to this project are documented in this file.
The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/) and the project uses
[Semantic Versioning](https://semver.org/).

## [1.0.2] — 2026-11-24

### Changed

- Contact address for questions and bug reports is now info@rrstudio.app (`SUPPORT_EMAIL` in `src/app/config/links.ts`).

### Fixed

- Demo data: in the three days before Black Friday the Discounts page had no scheduled code (and one unit test failed on those days). The Christmas campaign now looks 60 days ahead, so every status tab always has codes.
- The end-to-end test that creates a scheduled discount used fixed dates that are now in the past: it now uses dates relative to today.

## [1.0.1] — 2026-11-23

### Changed

- The live demo and the Getting started guide moved to https://rrstudio.app. The links in the README and in `docs/getting-started.md` point to the new address (the old one redirects). No change to the template code.

## [1.0.0] — 2026-11-15

First public release.

### Added

- Overview: KPI cards with the change against the previous period (revenue net of refunds, orders, average
  order value, returning customers, refunds), revenue over time, sales by channel, revenue by category,
  top products, orders to ship, low stock and most used discount codes, period selector and CSV export.
- Orders: status tabs with counts, search, channel and period filters, sorting, paging (all in the URL),
  bulk "Mark as fulfilled" and CSV export; order page with items, totals, customer, address and timeline,
  and Fulfill, Refund (full or partial, with restock) and Cancel dialogs.
- Products: list with status tabs, search by name or SKU, category and stock filters, bulk actions and CSV
  export; product form with options and variants, live margin, sales card and unsaved changes warning.
- Inventory: one row per variant with available, committed and incoming stock, adjustments with a reason
  (dialog, inline and in bulk), history per variant and CSV export.
- Customers: segments, search, country filter, tags, bulk actions, customer page with orders, notes and
  marketing consent, CSV export.
- Discounts: percentage, fixed amount and free shipping codes with conditions, limits, dates and usage
  statistics, create, edit, bulk actions and delete with confirmation.
- Store settings: store details, shipping zones and rates, taxes, payment methods and checkout options.
- Settings: profile, security, appearance (light, dark, system, 6 accent colors, density, Mock API
  switches), notifications, team with invitations and roles, API keys and webhooks.
- Auth: login, registration, forgot and reset password, onboarding wizard, guards and HTTP interceptor.
- Roles (`owner`, `admin`, `staff`, `viewer`) with one permission table, route guard, "Preview as role"
  and mock APIs that answer 403 like a server.
- Shared store state (`core/mock/store-state.ts`): refunds, cancellations and edits show everywhere and
  restock really puts units back.
- Command palette (Ctrl/⌘ K), notification feed, in-app 404 and no-access pages, loading, empty and error
  states with Retry on every page, responsive layout with cards on phones.
- Swappable API layer (mock data or HttpClient) with one switch in `app.config.ts`, and the full HTTP
  contract in `docs/openapi.yaml` (OpenAPI 3.1).
- Getting started guide (`docs/getting-started.md`), unit tests (Vitest) and end-to-end tests (Playwright).
- "Support rrstudio" button (Ko-fi), optional "Download" and guide links in `src/app/config/links.ts`.
