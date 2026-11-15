<div align="center">

# KC Chan

**Engineering Leadership · Product Engineering · Systems Architecture**

[![Portfolio](https://img.shields.io/badge/Portfolio-kalunchan.dev-1f2937?style=flat-square)](https://kalunchan.dev)
[![System Design Lab](https://img.shields.io/badge/System_Design_Lab-case_studies-0f766e?style=flat-square)](https://kchan1028.github.io/system-design-lab/)
[![FedPath](https://img.shields.io/badge/FedPath-gofedpath.com-2563eb?style=flat-square)](https://gofedpath.com)

</div>

### I build products and the engineering teams that scale them.

I'm an engineering leader who has worked across startups, enterprise organizations, SaaS, digital publishing, and government technology. My background spans software development, architecture, cloud infrastructure, cybersecurity, and carrier networks.

Technical decisions are business decisions. Architecture choices show up later as delivery speed, reliability, operating costs, and how easily the next team can maintain the system. I make those tradeoffs visible early, while they're still cheap to change, and I stay close enough to the code and the customers to know when a plan needs to shift.

## Featured engineering work

Each repository documents its decisions, test coverage and known limitations alongside the code.

### [Masters Cycling Lab](https://github.com/kchan1028/masters-cycling-lab)

**Problem:** AI answers about research are hard to trust when you can't see which passage they came from.

**What it does:** Upload research PDFs, search them, and ask questions. Every claim in an answer cites the exact passage and PDF page, and the server rejects citations to passages the model wasn't given.

**Decisions:** No RAG framework, so retrieval and citation checks stay inspectable. PostgreSQL doubles as a leased job queue. Exact pgvector search comes before approximate indexes. Answers work with any OpenAI-compatible model.

**Evidence:** 74 human-reviewed test questions across dev and held-out splits. Paper-level recall is close to target, and passage-level recall is the documented weakness.

**Stack:** Python, FastAPI, PostgreSQL + pgvector, React, TypeScript, Docker Compose · [Evaluation](https://github.com/kchan1028/masters-cycling-lab/blob/main/docs/evaluation.md) · [Decision records](https://github.com/kchan1028/masters-cycling-lab/tree/main/docs/decisions)

### [Sprint Progress Analyzer](https://github.com/kchan1028/sprint-progress-analyzer)

**Problem:** Sprint reviews drift into status reading when nobody can see how scope changed or where work is stuck.

**What it does:** Imports a Jira CSV in the browser and shows commitment versus current scope, blocked and aging work, and missing estimates, with explainable risk signals.

**Decisions:** Local-first, with no backend and no Jira credentials. Pure calculation functions are tested separately from the UI. Risk signals show their thresholds. It's a heuristic, not a forecast.

**Evidence:** Unit tests for parsing and scope accounting, Playwright and axe checks for the import journey, and a documented list of data limitations. The demo data is synthetic.

**Stack:** TypeScript, React, Vite, Vitest, Playwright · [Case study](https://github.com/kchan1028/sprint-progress-analyzer/blob/main/docs/product-case-study.md) · [User guide](https://github.com/kchan1028/sprint-progress-analyzer/blob/main/docs/user-guide.md)

### [System Design Lab](https://github.com/kchan1028/system-design-lab)

**Problem:** Most system design write-ups skip the failure modes, security boundaries and operating costs that decide whether a design works.

**What it does:** Six original case studies: a voice platform, document processing, event-driven orders, multi-tenant SaaS, a high-traffic API and RAG search. Each has requirements, trust boundaries, failure handling, cost reasoning and ADRs.

**Decisions:** Assumptions are labelled, and capacity arithmetic is never called a benchmark. The Document Processing study adds an interactive architecture explorer, a tradeoff analyzer and a deterministic failure simulation. These are design exercises, not production systems.

**Stack:** TypeScript, React, Mermaid, GitHub Pages · [Read the studies](https://kchan1028.github.io/system-design-lab/)

### More public projects

- **[SprintLab](https://github.com/kchan1028/sprintlab):** a backlog, board and sprint tracker for one developer, planned and built in its own sprints, with a written review and retro for each one and an [AI collaboration log](https://github.com/kchan1028/sprintlab/blob/main/docs/ai-collaboration-log.md). React, TypeScript, Vitest, Playwright.
- **[RideWind](https://github.com/kchan1028/ridewind):** forecast headwinds, crosswinds and tailwinds along a GPX route at the time you'll ride each section. Runs in the browser with no account, and the route file never leaves it. TypeScript, Vite, Leaflet · [Open RideWind](https://kchan1028.github.io/ridewind/)
- **[CycleReg](https://github.com/kchan1028/event-registration)** (in progress): a proposed registration and race-day platform for volunteer-run U.S. road races and criteriums. A local prototype covers category setup with shared field limits, rider checkout with a simulated payment, and check-in. Real payments, license checks and sign-in aren't built yet. TypeScript, React, Fastify, SQLite · [Product brief](https://github.com/kchan1028/event-registration/blob/main/product.md)

## Selected impact

| 400,000+ | 30+ | 3 continents |
|:---:|:---:|:---:|
| platform users | people across engineering and operations | platform footprint |

- Helped scale an international communications platform to 400,000+ users across three continents and supported its growth through acquisition.
- Built and led a 30+ person engineering and operations organization, owning architecture, delivery, vendors, and platform reliability.
- Delivered transaction processing and reconciliation capabilities supporting millions of dollars in financial activity.
- Built secure government-facing applications with identity, authorization, accessibility, and auditability requirements.

## Engineering Leadership in Practice

I approach engineering leadership by connecting technical decisions to delivery, reliability, cost, and business outcomes. I prefer clear tradeoffs, small reviewable changes, and evidence over assumptions.

Good delivery is a loop. What happens in production should change what the team builds next and how it builds it.

```mermaid
flowchart TD
    A[User problem + business goal] --> B[Product scope + priorities]
    B --> C[Architecture + tradeoffs]
    C --> D[Small changes + early QA]
    D --> E[Operate + measure]
    E -- User feedback --> B
    E -- Reliability, cost, security --> C
```

What that looks like in my own repositories:

| Practice | Where to see it |
|---|---|
| Write decisions down with the alternatives, risks and the conditions for revisiting them | [Masters Cycling Lab decisions](https://github.com/kchan1028/masters-cycling-lab/blob/main/docs/decisions/README.md) · [Sprint Progress Analyzer decisions](https://github.com/kchan1028/sprint-progress-analyzer/blob/main/docs/decisions/README.md) · [System Design Lab decisions](https://github.com/kchan1028/system-design-lab#key-decisions-and-alternatives) |
| Adopt a change only when the evidence holds up | Hybrid search and a reranker both helped on practice questions and were dropped because the gain didn't hold on held-out questions ([evaluation](https://github.com/kchan1028/masters-cycling-lab/blob/main/docs/evaluation.md#experiments-dev-only)) |
| Assess operational readiness honestly, risk by risk | Masters Cycling Lab [readiness](https://github.com/kchan1028/masters-cycling-lab/blob/main/docs/production-readiness.md) and [risks](https://github.com/kchan1028/masters-cycling-lab/blob/main/docs/risk-register.md) · Sprint Progress Analyzer [readiness](https://github.com/kchan1028/sprint-progress-analyzer/blob/main/docs/production-readiness.md) and [risks](https://github.com/kchan1028/sprint-progress-analyzer/blob/main/docs/risk-register.md) |
| Show users what the data can't tell them | CSV imports mark scope history "Unavailable" instead of guessing it ([case study](https://github.com/kchan1028/sprint-progress-analyzer/blob/main/docs/product-case-study.md#the-scope-decision)) |
| Treat security and cost as design inputs | A written [threat model](https://github.com/kchan1028/masters-cycling-lab/blob/main/SECURITY.md) for a local RAG app; trust boundaries and cost reasoning in every [System Design Lab](https://kchan1028.github.io/system-design-lab/) study |
| Ship small, reviewable changes with checks on every pull request | CI with pinned actions and dependency review in [Masters Cycling Lab](https://github.com/kchan1028/masters-cycling-lab/blob/main/docs/operations.md#continuous-integration) and [Sprint Progress Analyzer](https://github.com/kchan1028/sprint-progress-analyzer/blob/main/README.md#validation) |

## Technical capabilities

**Application engineering:** Python, Django, FastAPI, TypeScript, React, Next.js, Ruby on Rails

**Distributed systems and data:** PostgreSQL, Redis, Celery, Kafka, event-driven architecture, job queues and idempotent processing

**Cloud and infrastructure:** AWS, Terraform, Docker, GitHub Actions, carrier networks

**Security and reliability:** Identity and authorization, auditability, accessibility, threat modelling, failure recovery

**Applied AI and evaluation:** Retrieval-augmented generation, pgvector, retrieval evaluation, cited answers, human review of AI output

## Products

- [FedPath](https://gofedpath.com): helps small businesses discover government opportunities and work through bid decisions and proposal preparation.
- [Useful Little Tools](https://usefullittletools.app): practical tools for developers, engineering teams, and people learning technical concepts.
- [Berkeley Omnium](https://berkeleyomnium.com): a community cycling event website, built for clear information and mobile use.

## Beyond engineering

I ride bikes and help organize community bike racing, including the Berkeley Omnium.

## Contact

Work history, writing, and contact details are at **[kalunchan.dev](https://kalunchan.dev)**. You can also find my work through [Yippify](https://yippify.com).
