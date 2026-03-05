# Zerqis

A production-ready **DevSecOps / CloudSecOps** platform that detects exposed secrets in logs, CI/CD pipelines, Git commits, and cloud infrastructure; alerts security teams; and supports automated secret rotation and **blast radius analysis**. Designed to **support 50+ tenants from day one** with multi-tenant isolation.

This repository contains the **marketing/landing website** for Zerqis. Founded by Dhanush S.

## What Zerqis Does

- **Runtime secret detection** – Regex and rule-based scanning (AWS keys, JWT, Stripe, DB URLs, passwords); logs streamed via Kafka
- **Secret exposure inventory** – Track Secret, SecretExposure, RotationEvent by tenant; firstSeen, lastSeen, exposure count
- **Automated secret rotation** – Pluggable SecretRotator (AWS IAM, Vault stub); trigger → disable old → create new → store event
- **Alerting engine** – Slack webhook, generic webhook, SIEM-style event forwarding; severity LOW/MEDIUM/HIGH/CRITICAL
- **Risk scoring engine** – Overall score and risk level from production exposures, secret sensitivity, frequency, unique secrets
- **Blast radius analysis** – For exposed secrets (e.g. AWS_ACCESS_KEY), answer *what can this secret access?* — IAM user, permissions, affected resource types (S3, DynamoDB, Lambda, etc.); dashboard and API
- **Dashboard** – Overview, Secret Inventory, Exposure Events, **Blast Radius** (per exposure), Rotations, Risk, Usage, API Keys, Onboarding, Integration Guide
- **Multi-tenant SaaS** – All data scoped by tenantId; JWT for dashboard, API key for ingestion; RBAC (ADMIN, SECURITY_ENGINEER, VIEWER)
- **Integrations** – POST /api/v1/logs; optional Fluent Bit, Logstash, Log Agent (Docker/Kubernetes); Git webhook (GitHub/GitLab); cloud discovery (AWS, K8s)

## Tech Stack (Platform)

| Layer | Technologies |
|-------|--------------|
| Backend | Java 21, Spring Boot 3, Spring Security, Spring Data JPA, Hibernate, Maven |
| Frontend | React, TypeScript, Vite, TailwindCSS, Axios, Recharts |
| Infrastructure | PostgreSQL, Redis, Docker, Kubernetes, Kafka |
| Auth | JWT, RBAC |
| Observability | Prometheus, Grafana (optional) |

## This Site

- Static landing page: HTML, CSS, JavaScript.
- Open `index.html` in a browser or serve the folder with any static server.

## Documentation (Main Repo)

- **CUSTOMER_ONBOARDING.md** – Sign up, API key, send logs, verify detection; optional Git and alerts
- **API.md** – Auth, logs, API keys, dashboard APIs, blast radius, rotations, Prometheus
- **DEPLOYMENT.md** – Environment variables, Docker Compose, Kubernetes, Helm
- **SECURITY.md** – RBAC, tenant isolation, headers, rate limiting, audit
- **ARCHITECTURE.md** – Component diagram, data flow, services
- **OPERATIONS.md** – Monitoring, failures, tenant usage, retry
- **ROTATION.md** – What’s supported, self-serve vs assisted
- **INTEGRATIONS.md** – Logging (Fluent Bit, Logstash, Vector), CI/CD, Git, cloud, K8s, secrets managers, alerting, SIEM
- **SCALING.md** – Scaling to 100–1000 customers; DB/Kafka/Redis; quotas

## License

All rights reserved.
