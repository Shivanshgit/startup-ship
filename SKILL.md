---
name: startup-ship
description: |
  End-to-end startup execution skill — from raw idea to shipped product with users.
  Covers idea validation, MVP scoping, tech stack selection (free, no ceilings, open-source),
  system architecture, project scaffolding, build execution, testing, deployment, launch, and
  growth/marketing. Automatically loads all supporting engineering skills. Learns from every
  product built and applies those lessons to the next one via memory.
  Use this skill whenever the user has a product idea they want to build, a startup they want
  to launch, an MVP they want to ship, or a business they want to grow.
  Trigger on: "I have an idea", "help me build", "I want to launch", "how do I ship",
  "validate my idea", "build an MVP", "start a startup", "how do I market", "growth strategy",
  "find my first users", "what should I build first", "is my idea good", "e2e product",
  "how do I execute this", "ship this", "build and launch", or any description of an
  unbuilt product the user wants to make real.
---

# startup-ship

End-to-end playbook: raw idea → shipped product → first users → growth loop.
Opinionated. Free stack only. No ceilings. Learns from every project.

---

## Bootstrap (run once per project, first thing)

### 1. Load supporting skills
Invoke each of these skills before starting. They extend your capabilities for this project:

```
engineering:architecture    — folder structure, module design, monorepo layout
engineering:system-design   — DB schema, API contracts, data flow
engineering:testing-strategy — testing plan baked in from day one
artifact-design             — diagrams and visual artifacts
claude-mem:build            — build pipeline memory
```

Call each with the Skill tool. If any are unavailable, note it and continue — the skill degrades gracefully.

### 2. Search memory for past projects
Search claude-mem for any past work in this domain before starting:

```
search: "startup [product type]"
search: "stack [tech category]"  
search: "launch [target market]"
```

Surface any lessons, stack decisions, or patterns from previous projects. Present them to the user before proceeding — they are inputs to Phase 0, not overrides.

### 3. Read the stack definitions
Read `references/tech-stack.md` now. It contains the curated free/no-ceiling stack options per product type. You will reference it in Phase 3.

---

## Phase 0 — Capture the idea

Write a one-sentence thesis:

> **"[Specific user type] can [do specific thing] without [current painful alternative]."**

Extract:
- Primary user (specific — not "travelers", but "solo motorcycle riders planning multi-day routes")
- The one job they hire this product to do
- What they do today instead
- Why today's solution is painful or missing

**Save to memory:**
```
save_memory: product_thesis, project=[name], thesis=[sentence], user=[type], job=[job-to-be-done]
```

**Gate:** Thesis written → Phase 1.

---

## Phase 1 — Validate before building

Read `references/validation.md` now.

Kill bad ideas fast. Validation costs days; building costs months.

Run the validation checklist:
1. **Market signal** — active community complaining about this problem? (Reddit, X, App Store reviews)
2. **Competitor audit** — what exists, why did it fail or succeed, what gap remains?
3. **Willingness signal** — will someone pay, give email, or change behaviour?
4. **Founder fit** — unfair advantage in this space?

Deliver verdict: **build**, **pivot**, or **kill** with evidence.

**Save to memory:**
```
save_memory: validation, project=[name], verdict=[build/pivot/kill], 
  competitors=[list], gap=[one line], key_risk=[one line]
```

**Gate:** Verdict is "build" → Phase 2.

---

## Phase 2 — Scope the MVP

The MVP proves the core thesis with the minimum surface area.

1. Write the **core loop** — 5–8 steps, the sequence a user takes to get core value
2. List every feature required to complete that loop — nothing else
3. Cut anything that doesn't break the loop if removed
4. Define success: what does a working first run of the loop prove?

Produce:
- Core loop (numbered steps)
- MVP feature list (loop-only)
- Defer list (cut features + reason)
- Success definition

**Save to memory:**
```
save_memory: mvp_scope, project=[name], core_loop=[steps], 
  feature_count=[n], deferred=[list]
```

**Gate:** Core loop defined → Phase 3.

---

## Phase 3 — Choose the stack

Read `references/tech-stack.md` now. It contains the full curated stack per product type.

Answer four questions:
1. **Mobile, web, or both?** → frontend framework
2. **Real-time features?** → backend architecture  
3. **Geo/location data?** → database layer
4. **Solo or team?** → CI/CD complexity

Search memory for past stack decisions in this product category before choosing:
```
search: "stack [product type]"
```

Rules:
- Free, open-source, self-hostable only
- One language across the stack where possible
- >10k GitHub stars unless no alternative exists
- No SaaS ceilings

Deliver: named stack per layer with one-line justification.

**Save to memory:**
```
save_memory: stack_decision, project=[name], 
  frontend=[tool], backend=[tool], db=[tool], auth=[tool],
  deploy=[tool], rationale=[one line per key pick]
```

**Gate:** Full stack named → Phase 4.

---

## Phase 4 — Design the architecture

Read `references/architecture.md` now.

Design before writing code:

1. **Data model** — entities, relationships, key fields
2. **API surface** — endpoints/subscriptions the frontend needs
3. **Auth flow** — sign up, verify, session, permissions
4. **Privacy/trust rules** — public vs authenticated vs mutual-consent data (critical for marketplace/social apps)
5. **Folder structure** — monorepo layout, package boundaries
6. **Scalability seams** — where this breaks at 10x users (acceptable for MVP?)

Deliver: data model table, API surface, auth flow, folder structure, key tradeoff.

**Gate:** Data model agreed → Phase 5.

---

## Phase 5 — Scaffold and build

Build in this order. Do not deviate:

1. Project scaffold (repo, CI, linting, test runner, pre-commit hooks)
2. Database schema and migrations
3. Auth (sign up, sign in, session, roles)
4. Core loop — minimum path through the product, end to end
5. Safety features (block, report, rate limiting) — **never defer on social/marketplace apps**
6. Polish (animations, empty states, errors, loading states)

**Per-feature discipline:**
- Schema change first
- Test case before implementation
- Implement
- Verify in the running app — type checks verify code, not features

**What not to do:**
- No features outside the loop until the loop runs end-to-end
- No abstraction for hypothetical future requirements
- No error handling for impossible states
- No safety features deferred to "post-MVP"

**Save lessons to memory as you build:**
```
save_memory: build_lesson, project=[name], 
  lesson=[what you learned], applies_to=[product type / tech]
```

**Gate:** Core loop runs end-to-end → Phase 6.

---

## Phase 6 — Deploy and operate

Read `references/launch.md` now (deploy checklist section).

### Deploy checklist
- [ ] Secrets out of version control, env vars set in production
- [ ] Migrations run cleanly on a fresh database
- [ ] Auth works end-to-end in production config
- [ ] Error tracking live (Sentry)
- [ ] Uptime monitoring live (Uptime Kuma)
- [ ] Rate limiting on auth and write endpoints
- [ ] Automated database backups scheduled
- [ ] Privacy policy and terms of service exist
- [ ] Core loop tested in production by a real person before any public URL shared

**Gate:** Checklist complete → Phase 7.

---

## Phase 7 — Launch and find users

Read `references/marketing.md` now.

### Sequence
1. 3–5 real users complete the core loop before any public launch
2. Launch to get first 100 users
3. Talk personally to every one of the first 100
4. Fix what breaks before scaling

### Launch channels (pick two)
- **Community-led** — post in communities where the target user already lives. Be useful, not promotional.
- **Content-led** — document the build publicly. The audience becomes users.
- **Direct outreach** — personalised DMs to exact-fit users. Not mass.
- **Product Hunt** — works for dev tools and consumer apps with a warm network.
- **Press** — requires an unusual story, not just a product.

### The only metric that matters at launch
**Completed core loops** — not signups, not downloads.

**Save to memory:**
```
save_memory: launch_result, project=[name], 
  channel=[what worked], users_week1=[n], 
  loops_completed=[n], key_learning=[one line]
```

**Gate:** 10 users complete the core loop → Phase 8.

---

## Phase 8 — Measure and iterate

### Instrument the loop
Every step in the core loop gets a PostHog event. Measure:
- Step completion rate (where do users drop off?)
- Time between steps (where do users stall?)
- 30-day return rate
- NPS after first completed loop

### Iteration loop
1. Find the biggest drop-off step
2. Form one hypothesis
3. Make one change
4. Measure
5. Repeat

One experiment at a time.

### When to expand beyond the core loop
Only when:
- 30-day retention on the core loop is >40%, OR
- The missing feature is the stated reason users churn

**Save to memory after each iteration:**
```
save_memory: growth_lesson, project=[name],
  experiment=[what], result=[what happened], 
  applies_to=[product type]
```

---

## Memory: how this skill learns over time

Every save_memory call above builds a knowledge base. On the next project:
- Past stack decisions inform new ones
- Build lessons prevent repeated mistakes
- Launch results show which channels work per product type
- Validation patterns surface faster

The skill gets smarter with every product shipped. The memory is per-user and persists across sessions via claude-mem.

---

## Reference files

| File | Read at |
|------|---------|
| `references/validation.md` | Phase 1 |
| `references/tech-stack.md` | Phase 3 bootstrap + Phase 3 |
| `references/architecture.md` | Phase 4 |
| `references/launch.md` | Phase 6 |
| `references/marketing.md` | Phase 7 |
