---
description: All the latest CodeWords updates.
hidden: true
---

# Changelog

### August 2025

#### Spotlight

* Big infra leap → EKS migration, stability & reliability hardened
* End-to-end Sharing shipped
* Cancel runs anywhere
* Run history clarity
* Wallet top-ups live

#### Product Updates

**New**

* Sharing end-to-end: workflows can now be shared, with the full flow from Cody through to UI + Code (view-only) tab.
* Cancel runs available everywhere: Run page, Run History, Home, and sidebar.
* Run history upgrades: workflows vs Cody separated, badges for Cody runs, sidebar polish for clarity.
* Curated templates: more templates on Home, with a “view all” option.
* Wallet top-ups added to product.

#### **Improvements**

* Cody journeys: graph revamp exploration, node-by-node journey, breakout from Q\&A, attach files support.
* Triggers: stability fixes across production, safeguarded scheduling, connection issues resolved.
* Templates & Home: homepage polish and curated template sets.
* Docs & Content: changelog process defined, clearer Pipedream docs, new style guides, briefs, and improved content pipelines.

#### **Fixes**

* Recent Run sidebar status/actions now accurate and reliable.
* Conversation UX: scrolling fixed, editing no longer duplicates, response issues after questions resolved.
* Run page scheduling reliable again, rerenders prevented.
* Proxy tool call issues fixed; long Vercel build timeouts addressed.

#### Platform Updates

**Infrastructure & Behind the Scenes**

* EKS Migration: production workloads now run on EKS for improved reliability, scaling, and ops consistency.
* External “always-on” services wired into the platform for triggers and background processes.
* Kubernetes Hardening:
  * Improved cluster visibility & autoscaling with metrics-server across staging & production
  * Higher reliability under load through enforced pod distribution (anti-affinity)
  * Safer, cleaner deploys with automatic image freshness and limited rollout history
  * Consistent environment parity across staging and production
* Logging & Observability:
  * Loki re-architected to S3 with schema tuning
  * Grafana storage tuned & dashboards updated
* Local Dev Setup: smoother developer experience with consistent manifests and environment parity.
* Deployment Hygiene: prod/stg environment flags standardized; improved ArgoCD + debugging docs.
* Scaling & CI/CD: project planning for CI/CD pipeline and scaling finalized.



***

### July 2025&#x20;

#### Spotlight

* Cancel runs from anywhere
* Land straight in Cody after sign-in
* In-app support chat now available throughout the platform&#x20;
* Smoother, clearer UX

#### Product Updates

**New**

* Cancel runs from the Run page, Run History, Home, and the sidebar.
* After sign-in, users go straight to Cody; chat is also accessible from Home.
* In-app support chat added and easier to find.
* Template Gallery controls: show/hide templates + fresh additions.

**Improvements**

* Schedules & Triggers from chat with safeguards (no nested scheduling; per-user limits).
* Clearer errors: better “Out of credits” message with CTA; improved request-validation errors.
* Smoother chat UX: input “jumping” fixed and message ordering more consistent.
* Whiteboard only shows when a graph is available (less clutter).

**Fixes**

* Run page auto-refresh is reliable again.
* Recent Run sidebar status/actions are accurate and stable.
* Eliminated occasional invalid tool call errors after the question tool.

#### Platform Updates

**Web & Extension**

* Web agent & Chrome extension: stability and reliability upgrades.

**Infrastructure**

* Longer timeout for code runs to reduce premature failures.
* Model routing & connectivity (incl. Anthropic) improved and environment-aware.
* Infra upgrades (autoscaling, DNS/cluster, security hardening) for better uptime & speed.
