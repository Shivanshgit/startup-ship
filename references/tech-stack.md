# Tech Stack Reference

All tools: free, open-source, self-hostable, no usage ceilings.
Stars verified November 2026.

---

## Stack selector

Answer four questions → get a stack recommendation.

| Q1: Platform | Q2: Real-time | Q3: Geo data | Q4: Team size | → Recommended profile |
|---|---|---|---|---|
| Mobile (iOS+Android) | Yes | Yes | Solo/small | Flutter + Supabase |
| Mobile | Yes | No | Solo/small | Flutter + Supabase |
| Web only | No | No | Solo/small | Next.js + Supabase |
| Web only | Yes | No | Solo/small | Next.js + Supabase |
| Web + Mobile | No | No | Team | Next.js + Flutter + Supabase |
| API/backend only | — | — | Any | Go or Node.js + Postgres |

---

## Profile A — Flutter + Supabase (mobile-first, real-time, geo)

**Best for:** social apps, marketplace apps, companion finders, location-aware mobile products

| Layer | Tool | Repo | Stars |
|-------|------|------|-------|
| Mobile UI | Flutter | [flutter/flutter](https://github.com/flutter/flutter) | ⭐ 181k |
| State mgmt | Riverpod | [rrousselGit/riverpod](https://github.com/rrousselGit/riverpod) | ⭐ 7.4k |
| Animations | Rive | [rive-app/rive-flutter](https://github.com/rive-app/rive-flutter) | ⭐ 1.5k |
| Backend | Supabase | [supabase/supabase](https://github.com/supabase/supabase) | ⭐ 114k |
| Flutter SDK | supabase-flutter | [supabase/supabase-flutter](https://github.com/supabase/supabase-flutter) | ⭐ 1k |
| Database | Postgres + PostGIS | (included in Supabase) | — |
| Auth | Supabase Auth | (included) | — |
| Realtime | Supabase Realtime | (included) | — |
| Storage | Supabase Storage | (included) | — |
| Maps | MapLibre | [maplibre/maplibre-flutter-gl](https://github.com/maplibre/maplibre-flutter-gl) | active |
| Map tiles | OpenStreetMap | free, no key | — |
| Local cache | Hive | [hivedb/hive](https://github.com/hivedb/hive) | ⭐ 4.4k |
| Push notifs | ntfy | [binwiederhier/ntfy](https://github.com/binwiederhier/ntfy) | ⭐ 35k |
| Search | Meilisearch | [meilisearch/meilisearch](https://github.com/meilisearch/meilisearch) | ⭐ 60k |
| Admin panel | Directus | [directus/directus](https://github.com/directus/directus) | ⭐ 39k |
| Analytics | PostHog | [PostHog/posthog](https://github.com/PostHog/posthog) | ⭐ 41k |
| Error tracking | Sentry | [getsentry/sentry](https://github.com/getsentry/sentry) | ⭐ 46k |
| Deploy | Coolify | [coollabsio/coolify](https://github.com/coollabsio/coolify) | ⭐ 66k |
| CI/CD | GitHub Actions + Fastlane | [fastlane/fastlane](https://github.com/fastlane/fastlane) | ⭐ 42k |
| Monorepo | Melos | [invertase/melos](https://github.com/invertase/melos) | ⭐ 1.5k |
| Uptime | Uptime Kuma | [louislam/uptime-kuma](https://github.com/louislam/uptime-kuma) | ⭐ 93k |
| Metrics | Grafana + Prometheus | — | ⭐ 78k / 67k |

---

## Profile B — Next.js + Supabase (web-first)

**Best for:** SaaS tools, dashboards, content platforms, B2B products

| Layer | Tool | Repo | Stars |
|-------|------|------|-------|
| Frontend | Next.js | [vercel/next.js](https://github.com/vercel/next.js) | ⭐ 143k |
| UI components | shadcn/ui | [shadcn-ui/ui](https://github.com/shadcn-ui/ui) | ⭐ 127k |
| Styling | Tailwind CSS | [tailwindlabs/tailwindcss](https://github.com/tailwindlabs/tailwindcss) | ⭐ 98k |
| Forms | React Hook Form | [react-hook-form/react-hook-form](https://github.com/react-hook-form/react-hook-form) | ⭐ 45k |
| Validation | Zod | [colinhacks/zod](https://github.com/colinhacks/zod) | ⭐ 44k |
| Data fetching | TanStack Query | [TanStack/query](https://github.com/TanStack/query) | ⭐ 51k |
| Backend | Supabase | [supabase/supabase](https://github.com/supabase/supabase) | ⭐ 114k |
| ORM | Drizzle | [drizzle-team/drizzle-orm](https://github.com/drizzle-team/drizzle-orm) | ⭐ 36k |
| Auth | Supabase Auth or NextAuth | [nextauthjs/next-auth](https://github.com/nextauthjs/next-auth) | ⭐ 28k |
| Search | Meilisearch | [meilisearch/meilisearch](https://github.com/meilisearch/meilisearch) | ⭐ 60k |
| Email | Stalwart | [stalwartlabs/mail-server](https://github.com/stalwartlabs/mail-server) | ⭐ 16k |
| Analytics | PostHog | [PostHog/posthog](https://github.com/PostHog/posthog) | ⭐ 41k |
| Testing | Vitest + Playwright | [vitest-dev/vitest](https://github.com/vitest-dev/vitest) / [microsoft/playwright](https://github.com/microsoft/playwright) | ⭐ 17k / 99k |
| Deploy | Coolify | [coollabsio/coolify](https://github.com/coollabsio/coolify) | ⭐ 66k |
| Error tracking | Sentry | [getsentry/sentry](https://github.com/getsentry/sentry) | ⭐ 46k |
| Uptime | Uptime Kuma | [louislam/uptime-kuma](https://github.com/louislam/uptime-kuma) | ⭐ 93k |

---

## Always-on tools (every project, every stack)

| Tool | Repo | Stars | Role |
|------|------|-------|------|
| Git | — | — | Version control |
| GitHub Actions | — | — | CI/CD |
| Trivy | [aquasecurity/trivy](https://github.com/aquasecurity/trivy) | ⭐ 39k | Container + IaC security |
| Gitleaks | [gitleaks/gitleaks](https://github.com/gitleaks/gitleaks) | ⭐ 31k | Secret scanning |
| TruffleHog | [trufflesecurity/trufflehog](https://github.com/trufflesecurity/trufflehog) | ⭐ 29k | Secret detection in history |
| Plane | [makeplane/plane](https://github.com/makeplane/plane) | ⭐ 62k | Project management |
| Penpot | [penpot/penpot](https://github.com/penpot/penpot) | ⭐ 62k | UI design |
| Excalidraw | [excalidraw/excalidraw](https://github.com/excalidraw/excalidraw) | ⭐ 135k | Diagrams + whiteboarding |

---

## AI coding assistant (local, no API cost)

| Tool | Repo | Stars | Role |
|------|------|-------|------|
| Ollama | [ollama/ollama](https://github.com/ollama/ollama) | ⭐ 186k | Run LLMs locally |
| Continue | [continuedev/continue](https://github.com/continuedev/continue) | ⭐ 36k | IDE Copilot pointing at Ollama |
| Aider | [Aider-AI/aider](https://github.com/Aider-AI/aider) | ⭐ 50k | CLI AI pair programmer |

Recommended local model: `qwen2.5-coder:14b` via Ollama. Free, no token limit.

---

## Stack rules

1. **Never add a tool without a clear, current job** — every tool in the stack should own a specific layer
2. **Self-host before using a managed service** — managed services have ceilings; self-hosted doesn't
3. **One database** — don't split Postgres and a separate NoSQL unless you've proven you need it
4. **Supabase replaces 6 tools** — DB + auth + storage + realtime + edge functions + PostGIS. Use all of it before adding anything else
5. **PostHog replaces 3 tools** — analytics + session replay + feature flags. One self-hosted instance covers all of it
6. **Coolify replaces 4 tools** — Heroku + Netlify + Vercel + container registry. One VPS, all services
