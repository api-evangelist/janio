# Janio

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Janio is a Singapore-headquartered **fourth-party logistics (4PL)** provider serving Southeast Asia
and Greater China. It does not own trucks or warehouses — it orchestrates a network of 500+ vetted
carriers and 3PLs on a customer's behalf under one contract, one invoice and one SLA, across land,
air and ocean freight plus warehousing.

- Website: https://www.janio.asia/
- Integrations & API: https://www.janio.asia/integrations
- Support: https://support.janio.asia/en/support/home
- Customer portal (login): https://app.janio.asia/

## What this profile found (2026-08-23)

**The API is real and live, but its contract is not published.**

- `https://api.janio.asia` is a production Django REST Framework host. Anonymous probes returned
  `403 {"detail":"Permission denied."}` on `/api/order/orders/` and `/api/order/order/create/`, and a
  plain `404` elsewhere — a live, credential-gated API, not a parked host.
- No machine-readable contract exists at any probed location. `/openapi.json`, `/openapi.yaml`,
  `/swagger.json`, `/v1/openapi.json`, `/api-docs`, `/docs`, `/redoc`, `/api/schema`, `/graphql`,
  `?wsdl` and the DRF schema paths all 404 on the API host; the docs host, the portal host and the
  marketing host miss the same way. No AsyncAPI, no GraphQL SDL, no `.proto`, no WSDL.
- The route to the reference is a sales form. The Integrations page's only call to action is
  **"Request API Documentation"**, which leads to `/contact`. Janio's own copy says
  *"API documentation is available upon request."*
- No MCP server, no A2A agent card, no `/.well-known` document on any host.
- **Janio does publish a real `llms.txt`** at https://www.janio.asia/llms.txt — saved verbatim to
  `llms/janio-llms.txt`. It is a well-formed, genuinely useful document, and it is currently the
  single best machine-readable thing Janio ships.

**Notable gaps between what the site claims and what is publicly obtainable:**

| Claimed on janio.asia | Publicly obtainable |
|---|---|
| "We provide SDKs for popular languages" | No first-party SDK in npm, PyPI, RubyGems, Packagist, crates.io, NuGet, Maven Central or pkg.go.dev |
| "Sandbox testing environment" | No sandbox host, test credential or test identifier published |
| Webhooks for status/delivery/exception events | No event catalog, payload schema, signing scheme or retry policy published |
| "99.9% uptime SLA" | No status page (`status.janio.asia` does not resolve), no SLA document |
| SOC 2 Type II and ISO 27001 | Janio itself states audits are *in progress*, not complete |

Two first-party platform connectors do exist and are recorded in `packages/`: the
[Shopify app](https://apps.shopify.com/janio-asia) and the
[WooCommerce plugin](https://wordpress.org/plugins/janio-store-connector/) — the latter still at
`1.0.0`, last published **2023-03-24**, tested only to WordPress 6.2. Both Janio GitHub
organizations (`janioasia`, `Janio-Asia`) exist and are empty (0 public repos).

## Artifacts in this repository

| Path | Type | Method |
|---|---|---|
| `llms/janio-llms.txt` | LLMsTxt | searched (verbatim) |
| `plans/janio-plans-pricing.yml` | Plans | searched |
| `rate-limits/janio-rate-limits.yml` | RateLimits | searched (`limit_count: 0`) |
| `conformance/janio-conformance.yml` | Conformance + Compliance | searched |
| `lifecycle/janio-lifecycle.yml` | Lifecycle | searched |
| `conventions/janio-conventions.yml` | Conventions | probed |
| `packages/janio-packages.yml` | Packages | searched |
| `security/janio-domain-security.yml` | DomainSecurity | probed |
| `well-known/janio-well-known.yml` | (absence record — no pointer) | probed |

No `Idempotency`, `SDKs`, `Sandbox`, `Webhooks`, `StatusPage`, `Deprecation`, `Security`,
`MCPServer`, `AgentCard`, `AgentSkill` or `WellKnown` pointer is emitted, because in every one of
those cases the probe recorded an absence. The artifacts document the absence; the pointers would
have asserted a presence.

## For Janio

Publishing the OpenAPI you already hand out on request — at a stable URL, alongside the webhook
event catalog and the sandbox details you already advertise — would move nearly every measurement
above at once, and would make the API reachable by the agents your customers are starting to build.
Open an issue here or email info@apievangelist.com and we will re-score.
