# startup-ship

A Claude Code skill for taking a startup idea from zero to shipped — with real users, a working product, and a growth loop.

**Opinionated. Free stack only. No usage ceilings. Learns from every project.**

---

## What this skill does

Guides Claude through every phase of building and shipping a product:

| Phase | What happens |
|-------|-------------|
| 0 — Capture | Extract a clean one-sentence product thesis |
| 1 — Validate | Kill bad ideas before building: market signal, competitors, willingness |
| 2 — Scope | Define the core loop and the minimum feature set to prove it |
| 3 — Stack | Pick the right free/open-source tools per product type |
| 4 — Architecture | Design the data model, API surface, auth flow, and folder structure |
| 5 — Build | Scaffold and build feature by feature, loop by loop |
| 6 — Deploy | Pre-launch checklist, infra, App Store submission |
| 7 — Launch | Find the first 100 users across community, content, and direct channels |
| 8 — Iterate | Instrument the loop, measure retention, run experiments |

The skill also:
- **Auto-loads** 5 supporting engineering skills at the start of every project
- **Searches memory** for lessons from past projects before making decisions
- **Saves lessons** at each phase — stack decisions, build lessons, launch results — so every future project benefits from every past one

---

## Stack philosophy

All recommended tools are:
- Free and open-source
- Self-hostable (no SaaS ceilings)
- Actively maintained (verified GitHub stars + recent commits)

Two curated profiles are bundled:
- **Profile A — Flutter + Supabase** for mobile-first, real-time, geo products
- **Profile B — Next.js + Supabase** for web-first SaaS and dashboards

Full stack tables with GitHub stars and last-push dates: [`references/tech-stack.md`](references/tech-stack.md)

---

## Files

```
startup-ship/
├── SKILL.md                    # Main skill — phases, gates, memory hooks
└── references/
    ├── tech-stack.md           # Curated free stack per product type (with stars)
    ├── validation.md           # 4-check validation framework
    ├── architecture.md         # Data model, RLS, API, folder structure patterns
    ├── launch.md               # Deploy checklist + App Store submission
    └── marketing.md            # First 100 users + retention playbook
```

---

## Installation

### Option A — Claude Code (recommended)

1. Clone this repo into your Claude skills directory:
   ```bash
   git clone https://github.com/shivanshsaini/startup-ship ~/.claude/skills/startup-ship
   ```

2. Add to your Claude settings (`~/.claude/settings.json`):
   ```json
   {
     "skills": ["~/.claude/skills/startup-ship"]
   }
   ```

3. The skill auto-triggers on phrases like:
   - "I have an idea for..."
   - "Help me build and ship..."
   - "Validate my idea"
   - "I want to launch..."

### Option B — Manual invocation

```
/startup-ship
```

---

## Supporting skills

This skill auto-loads these supporting skills at bootstrap (they must be available in your Claude setup):

- `engineering:architecture`
- `engineering:system-design`
- `engineering:testing-strategy`
- `artifact-design`
- `claude-mem:build`

---

## Memory and learning

This skill uses [claude-mem](https://cmem.ai) to persist lessons across projects. At each phase it saves:
- Product thesis and validation verdict
- Stack decisions and rationale
- Build lessons
- Launch results and channel performance
- Growth experiments and outcomes

On the next project, it searches this memory before making decisions. The skill compounds — every project makes the next one faster.

If you don't use claude-mem, the skill still works — memory calls are gracefully skipped.

---

## Contributing

Issues and PRs welcome. If you've used this skill to ship a product, open a PR to add your stack decisions and lessons to the reference files.

---

## License

MIT
