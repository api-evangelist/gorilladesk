# GorillaDesk (gorilladesk)

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

GorillaDesk is field service management software for pest control, lawn care, pool service, and other home-service businesses, covering scheduling, routing, invoicing, payments, customer records, and technician management.

GorillaDesk exposes a **real, self-serve public REST API** - the GorillaDesk v1 API at `https://api.gorilladesk.com/v1` - documented with a public **OpenAPI 3.0.3** specification (served at `https://api.gorilladesk.com/v1/specs` and rendered via Redoc at [https://api.gorilladesk.com/](https://api.gorilladesk.com/)).

## API Access Model

- **Authentication:** Token (Bearer) authentication. API keys are **per-company** and are generated and deleted on the in-app Addons page (`https://beta.gorilladesk.com/addons/api`).
- **No separate developer program or API pricing tier.** Any paying GorillaDesk account can mint an API key; there is no metered API cost on top of the subscription.
- **Narrow documented surface.** The public v1 OpenAPI spec intentionally documents a small set of resources - **Company, Users, Customers, Customer Notes, and Phone Types**. Broader automation such as invoices, jobs/appointments, work orders, and payments is delivered through **Zapier connectors** and out-of-the-box integrations (QuickBooks Online, Square, Stripe, Google Calendar/Maps, Mailchimp) rather than through the public v1 REST spec.
- **v2 (undocumented).** A newer v2 API surface exists at `apiv2.gdesk.io` (referenced by third-party tooling and an MCP server that expose invoice/job operations), but its documentation is auth-gated and not public, so it is not modeled here.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/gorilladesk/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/gorilladesk/refs/heads/main/apis.yml)

## Tags

- Field Service Management
- Pest Control
- Lawn Care
- Scheduling
- Invoicing
- Customers
- SaaS

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## APIs

All APIs share base URL `https://api.gorilladesk.com/v1`, Bearer authentication, and the single public OpenAPI spec. The logical APIs below group the documented endpoints by resource.

### GorillaDesk Customers API

List, create, retrieve, and update customer records - including contacts, phone numbers, and service locations. Endpoints: `GET/POST /customers` and `GET/PUT /customers/{customerId}`. This is the core CRM surface of the public v1 API.

- **Human URL:** [https://api.gorilladesk.com/](https://api.gorilladesk.com/)
- **Base URL:** `https://api.gorilladesk.com/v1`

### GorillaDesk Customer Notes API

Append notes to a customer's file to record communication history and context. Endpoint: `POST /customers/{customerId}/notes`.

- **Human URL:** [https://api.gorilladesk.com/](https://api.gorilladesk.com/)
- **Base URL:** `https://api.gorilladesk.com/v1`

### GorillaDesk Users API

List and retrieve the users on a GorillaDesk company account - administrators, managers, and technicians. Endpoints: `GET /users` and `GET /users/{userId}`.

- **Human URL:** [https://api.gorilladesk.com/](https://api.gorilladesk.com/)
- **Base URL:** `https://api.gorilladesk.com/v1`

### GorillaDesk Company API

Retrieve the account/company details tied to the authenticating API key. Endpoint: `GET /company`.

- **Human URL:** [https://api.gorilladesk.com/](https://api.gorilladesk.com/)
- **Base URL:** `https://api.gorilladesk.com/v1`

### GorillaDesk Phone Types API

List the phone-type reference values (mobile, home, work, fax) used when attaching phone numbers to customer contacts. Endpoint: `GET /phone-types`.

- **Human URL:** [https://api.gorilladesk.com/](https://api.gorilladesk.com/)
- **Base URL:** `https://api.gorilladesk.com/v1`

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/gorilladesk)
- [Website](https://gorilladesk.com/)
- [Documentation](https://api.gorilladesk.com/)
- [Sign Up / API Keys](https://beta.gorilladesk.com/addons/api)
- [Integrations Library](https://gorilladesk.com/integrations-library/)
- [Plans](plans/gorilladesk-plans-pricing.yml)
- [Rate Limits](rate-limits/gorilladesk-rate-limits.yml)
- [Fin Ops](finops/gorilladesk-finops.yml)

## Pricing

GorillaDesk is priced **per route** (a technician's schedule), not per user - unlimited office staff, admins, and mobile devices are included. Published plans (2026): Basic $49/route/month, Pro $99/route/month, Growth $149/route/month, with a 14-day free trial and no setup fees. See `plans/gorilladesk-plans-pricing.yml`.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
