

## MVP Team Structure

### Number of Teams

**3 teams** are sufficient to build the MVP efficiently.


### Team 1 — Backend Core Team

**Developers:** 3–4

**Responsibilities:**

* API Gateway
* Auth Service & Account Service
* Lesson Service
* Assignment Service
* RBAC and authorization rules
* PostgreSQL schema and migrations
* Service-to-service authentication


### Team 2 — Real-Time & Integrations Team

**Developers:** 2–3

**Responsibilities:**

* Real-Time Communication Service (WebSockets)
* Message queue / event publishing
* Integration with external Video Call API
* Notification Service (email / push)

### Team 3 — Frontend Team

**Developers:** 2–3

**Responsibilities:**

* Student Web App
* Teacher Web App
* Authentication flows (login, signup)
* Assignment submission UI
* Real-time UI updates (progress bars, presence)
* API integration with Gateway



## Phase I Team Structure Changes


#### 1. Backend Core Team (Expanded)

**Developers:** 4–5

**New Responsibilities:**

* Audit logging
* Admin APIs
* Rate limiting & WAF integration
* Data migrations at scale


#### 2. Frontend Team (Split by Surface)

**Developers:** 4–5 total

**Sub-teams:**

* Learning Experience (Student-facing UI)
* Teaching & Admin Experience (Teacher + Admin dashboards)

