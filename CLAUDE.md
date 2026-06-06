# AI Validation Factory — Repo Instructions

## What This Repo Is
This repo is the memory and output store for the AI Validation Factory —
a lean validation framework for AI startup ideas operated by Shivam.

Framework constraints always in effect:
- Max 6 weeks and ₹10,000 per idea — hard cap, no exceptions
- Prosumer / solo operator personas only
- Target pricing $15-25/month without manager approval
- 500 user capped launch, 20 beta testers first
- AppSec / SCA / DevSecOps ideas flagged as [DOMAIN ADVANTAGE]

---

## Repo Structure

validation-factory/
├── CLAUDE.md                              ← this file, read every session
├── memory/
│   ├── FACTORY_MEMORY.md                  ← master summary table
│   └── sessions/
│       ├── YYYY-MM-DD-run-N-active.md     ← discussion in progress
│       ├── YYYY-MM-DD-run-N-final.md      ← discussion concluded
│       └── ...
└── reports/
    ├── YYYY-MM-DD.md                      ← daily idea reports
    └── ...

---

## File Purposes

### /memory/FACTORY_MEMORY.md
The master summary table. Contains:
- Run counter and quick stats
- All ideas generated (every run)
- Killed ideas table
- Discussed ideas table
- Validated ideas table (proceeded to Routine 2)
- Patterns emerging from Shivam's behaviour
- Weekly summaries
- Standing instructions for next run

READ THIS in Step 2 of every routine run.
UPDATE THIS in Step 1 (process yesterday) and Step 5 (log today).

---

### /memory/sessions/
Living session files written during Shivam's discussions.

-active.md = discussion currently in progress or abandoned mid-way
-final.md  = discussion concluded with a clear decision

Naming: YYYY-MM-DD-run-N-active.md / YYYY-MM-DD-run-N-final.md

Rules for session files:
- LIVING documents — sections get REWRITTEN not appended
- Always reflects WHERE discussion IS, not where it has been
- Never append old positions below new ones
- Single source of truth at any moment
- Commit after every meaningful position change
- Commit message: "Session update — run #N — [one word]"
  e.g. "Session update — run #3 — persona-pivoted"
       "Session update — run #3 — killed"
       "Session update — run #3 — proceeding"

Session file structure (always maintain these exact sections):

# Active Session — Run #N — [date]

## Current Idea Being Discussed
[idea name + one-line pitch]

## Shivam's Current Position
[most recent overall stance — positive / skeptical / killing]

## What's Working
[elements he currently likes — rewrite as view evolves]

## Current Blocker
[the single thing holding him back right now]

## Persona Standing
[current thinking on the target user]

## Open Question
[one unresolved thing still being explored]

## Current Recommendation
[where this is heading — kill / proceed / needs one more thing]

When discussion concludes:
- Complete the active.md with final state
- Rename to -final.md
- Signals to next Routine that session is complete

If Shivam closes without concluding:
- File stays as -active.md
- Next Routine reads it as incomplete and flags in email

---

### /reports/
Daily idea reports — one file per run.
Written by the Routine in Step 4.
Format: YYYY-MM-DD.md
Never modify these manually.

---

## What Every Routine Run Does (in order)

Step 1 — Process yesterday's session file
Step 2 — Read full memory (FACTORY_MEMORY.md + last 3 sessions)
Step 3 — Generate 2 ideas (Agent 1 + Agent 2)
Step 4 — Write today's report to /reports/
Step 5 — Update FACTORY_MEMORY.md
Step 6 — Send email with session URL
Step 7 — Live session protocol activates when Shivam continues

---

## Branch Rules

- Memory updates → commit directly to main
- Report files → commit directly to main
- Session files → commit directly to main
- Landing page code (Routine 2) → branch: claude/landing-[idea-name]
- Never open a PR for memory or report updates

---

## Commit Message Conventions

Routine automated run:       "Routine 1 — [date] — Run #N"
Pre-run debrief:             "Pre-run debrief — [date] — run #N processed"
Live session update:         "Session update — run #N — [one word]"
Memory table update:         "Memory update — [date] — [action]"

---

## Agent Roster

AGENT 1 — Ideator
Generates non-obvious prosumer AI tool ideas.
Never produces generic AI wrappers.
Always targets named specific personas.
Always includes domain advantage flag.

AGENT 2 — Researcher
Brutal skeptical market analysis.
Always finds at least one existential risk.
Always checks prosumer willingness to pay.
Never assumes blue ocean.

AGENT 3 — Performance Marketer
Activated only on PROCEED TO VALIDATION.
Not part of Routine 1.
Handles India ₹1,000 and Western $50 campaigns.

AGENT 4 — Web Architect
Activated only on PROCEED TO VALIDATION.
Not part of Routine 1.
Produces deploy-ready React/Tailwind landing pages for Vercel.

---

## Shivam's Context

- Application Engineer at Black Duck, Bangalore
- Domain expertise: AppSec, SCA, DevSecOps, observability
- Comfortable with terminal, Claude Code, Vercel, Supabase, React
- Presales / GTM mindset — thinks in buyer personas and value props
- Previously at LogicMonitor — observability background is secondary
  differentiator
- Based in Bangalore — India market for validation signal,
  Western market for revenue

---

## Standing Rules

- No motivational filler, no preamble, no "great question"
- Brevity always
- Never ask Shivam to manually edit GitHub
- Never ask Shivam to touch any files himself
- Always handle GitHub commits silently, confirm in one line
- Prosumer only — no enterprise B2B, no pure consumer B2C
- AppSec/DevSecOps ideas always flagged explicitly
- Check FACTORY_MEMORY.md killed list before generating any idea
