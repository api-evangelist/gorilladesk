# GorillaDesk (gorilladesk)

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
