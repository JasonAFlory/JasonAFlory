# Jason Flory

**Enterprise IT Engineer & AI Automation Specialist** | 15 years regulated-scale Apple/Jamf endpoint · Governed AI-assisted development · Compliance

15+ years building secure, audit-ready Apple platforms in regulated environments — grew a global Mac estate from 1,500 to 8,000+ devices across 80+ sites (Hogarth Worldwide/WPP), including a Jamf Cloud migration and estate-wide SOC 2 compliance support. The same discipline — make the system honest about its own state, so nothing goes dark and nothing gets away with lying about its status — is what I now apply to building AI systems: shipped products, governed autonomous agents, and internal tools built with Cursor and Claude Code. Available now for contract or permanent work, UK-based or remote.

[LinkedIn](https://www.linkedin.com/in/jason-flory-6aa68389/)

## Selected work

- **[governed-autonomy](https://github.com/JasonAFlory/governed-autonomy)** — Reference architecture for running autonomous multi-agent systems under enforceable epistemic and safety governance.
- **Jarvis** — an autonomous evidence-investigation engine that runs bounded search passes on a schedule until it stops finding anything new, then states plainly where the evidence runs out. Public write-up coming.
- **CertAlert** — a compliance-renewal tracking product for UK care/healthcare providers: role-based requirement rules, a renewal pipeline, and an audit log built for inspection-readiness. Built solo, shipped, and live-deployed; shelved after launch for distribution/marketing reasons, not technical ones — not yet public, ask me to walk through it. Built in the same stretch as three other shipped SaaS products (a photographer licensing platform, a retail-investor research tool, an internal marketing-ops tool with a live LLM-drafted-reply feature) — real products that hit a go-to-market wall, not abandoned prototypes.

## How I build with AI

I don't prompt an AI and ship whatever comes back. Everything I build runs inside a structure designed the same way I'd design any managed system: state has to be visible, decisions have to be logged, and nothing gets to quietly happen with no record of why.

**Stack.** Obsidian holds the source of truth — separate vaults per domain (endpoint/IT/career work, an investigation engine, a cross-cutting reference layer), kept strictly apart so nothing bleeds across domains it doesn't belong in. Claude (Claude Code CLI, and Cowork for interactive sessions) reads and writes into these vaults through a live MCP connector, not copy-paste — planning and review happen here. Cursor and GitHub Copilot sit alongside it for hands-on coding work inside the editor. Recurring work — daily briefs, scheduled investigation passes — doesn't wait for me to be at the machine: the always-on pieces run unattended on a VPS (plain Ubuntu, nothing exotic), on a schedule, the same way I'd use a Jamf policy to run something unattended across a fleet.

**Verification.** I don't take a single AI answer as settled fact. Claims get cross-referenced against multiple independent sources before they're accepted. Contested conclusions get an adversarial pass — one line of reasoning argues for it, a second is deliberately set against it to try to break it. Higher-stakes decisions go through a structured multi-lens review: several distinct evaluation angles (market reality, execution risk, economics, and a dedicated skeptic/failure-modes lens) run over several mandatory sequential passes, with an elimination log after each one, before anything is accepted as a real conclusion. For open-ended questions I run parallel, swarm-style investigations rather than one linear thread, so a wrong turn early on doesn't quietly become the whole answer.

**Structure.** Each vault runs on two layers: a **wiki** layer for stable reference material, and an **engine** layer for active, operational work — tools, engagements, decisions in flight. Every vault carries three anchor files: `HANDOFF.md` (current state — what's true right now), `DECISIONS.md` (an append-only log of why things are the way they are — never edited, only added to), and `SOURCES.md` (a ledger of every raw source the vault draws on and how completely it's actually been read — a distilled summary is never allowed to stand in for "the source was fully read").

**Protocols.** Every session starts the same way: read `HANDOFF.md`, then `DECISIONS.md`, then check `SOURCES.md` for anything not yet fully captured, then ask directly whether anything discussed elsewhere needs writing down. Capture is automatic, not something I have to remember to trigger — durable facts, decisions, and corrections get written to the vault as they come up, not batched at the end of a session. Anything the tooling can't read gets flagged, never guessed at.

**This isn't just internal tooling — it goes into shipped products too.** One of my SaaS builds calls an LLM directly as a product feature (drafting suggested replies from pasted source text), with a primary provider and an automatic fallback to a second when the first hits a rate limit. Structured output in, a real failure mode handled, not just a prompt that usually works.

**Jarvis is the clearest picture of how I actually work with these systems day to day.** I write the question and lock in my own starting assumption before any research runs — a stated prior it isn't allowed to quietly bend just to agree with me later. From there it runs unattended on a schedule: it breaks the question into sub-claims, weighs sources by credibility, and works through bounded search passes with no prompting from me in between. Every pass appends its findings to a dossier I can't edit after the fact, only add to. I don't watch it search; I read a short plain-English brief once a day and open the full dossier when I want the detail. It stops on its own once new passes stop turning anything up, and it's built to say so loudly if the evidence contradicts what I assumed going in — not just confirm what I already believed. Two of its live investigations produced the actual AI-career-market findings behind this README's own positioning — it's not a demo, it's a tool I use to make real decisions.

**A second, still-private system runs the same discipline against financial-event research.** Hive is a scheduled pipeline that harvests market events and tests specific strategies against them in paper-trading only — hard invariants enforce no live capital and no autonomy to place a real trade — and a strategy only "graduates" once it clears a statistical evidence gate. Nothing is assumed to work until the data proves it. It was the actual answer the last time an employer asked what I've built with AI tools, not a hypothetical.

**The most disciplined of these systems splits planning and execution across two different AI tools entirely, and lets them talk only through a written contract** — a specified brief in, a written result out, one task per exchange, nothing implied or assumed. Hard session limits force a fresh start rather than let context sprawl and quietly rot. Every architectural decision gets its own permanent written record, never edited after the fact. The system itself runs on five separated layers — what to build, how to build it, how it's meant to perform, what was learned, and what's worth keeping as a standing principle — so a lesson learned in one corner doesn't get lost the next time something new gets built.

The point of all of this: AI accelerates the building, but I own the architecture, the governance, and the judgment calls. Implementation is AI-generated under direction I set and review — not autonomous, not vibe-coded, not a black box.

## Open-source endpoint tooling

| Tool | Language | What it does |
|---|---|---|
| [jamf-framework-watchdog](https://github.com/JasonAFlory/jamf-framework-watchdog) | Python (stdlib) | Diagnoses why a managed Mac has lost contact with Jamf and routes each failure to the cheapest correct fix, instead of blanket-reinstalling |
| [mac-diag-collector](https://github.com/JasonAFlory/mac-diag-collector) | Bash | Single-command diagnostic bundler for support tickets |
| [mac-selfservice-fixit](https://github.com/JasonAFlory/mac-selfservice-fixit) | Bash | Self Service remediation script pack, safe idempotent fixes for common Mac issues (MDM check-in, DNS, printing, caches, Spotlight) |
| [jamf-autoupdate-manager](https://github.com/JasonAFlory/jamf-autoupdate-manager) | Bash | Installomator-based auto-patch layer with Jamf Extension Attribute/Smart Group integration |
| [mac-decommission-app](https://github.com/JasonAFlory/mac-decommission-app) | Swift/SwiftUI | Native macOS app for device decommissioning, Jamf unenrollment, OneDrive offboarding, system cleanup |
