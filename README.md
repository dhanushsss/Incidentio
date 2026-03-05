# Zerqis

A production-ready **DevSecOps / CloudSecOps** platform that detects secrets exposed in logs, CI/CD pipelines, and cloud infrastructure—alerts teams and supports automatic secret rotation.

This repository contains the **marketing/landing website** for Zerqis. Founded by Dhanush S.

## What Zerqis Does

- **Detect secrets** — Application logs, CI/CD, optionally Git commits and cloud configs (AWS keys, JWT, passwords, DB URLs).
- **Track** — Central inventory with risk scoring; filter by service, environment; exposures and rotation events.
- **Alert** — Slack and generic webhook when exposures are found (Service, Environment, Secret Type, Severity).
- **Rotate** — Trigger rotation via API; pluggable rotators with AWS implementation.
- **Multi-tenant SaaS** — All data scoped by tenantId; JWT for dashboard, API key for log ingestion; RBAC (ADMIN, SECURITY_ENGINEER, VIEWER).

## Onboarding Flow (Summary)

1. **Sign up** — Email, password, display name, optional org name.
2. **Create API key** — Dashboard → API Keys; use in `X-API-Key` for `POST /api/v1/logs`.
3. **Send logs** — JSON: `serviceName`, `environment`, `logMessage`; 202 Accepted.
4. **Verify** — Overview, Secret Inventory, Exposure Events, Security Risk update after processing.
5. **(Optional)** Git webhook, Slack/webhook alerts.

See **Customer Onboarding** and **API** docs in the main Zerqis repo for full details.

## Tech (This Site)

- Static site: HTML, CSS, JavaScript.
- Open `index.html` in a browser or serve the folder with any static server.

## License

All rights reserved.
