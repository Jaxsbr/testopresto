# Testopresto

## Purpose
A sandbox project for testing the build-loop and SABS workflows.

## Structure

```
testopresto/
├── index.html          # Main page — Synergy Ops Center comedy dashboard
│                        # Embedded <style> block (CSS), embedded <script> block (JS)
│                        # No external dependencies — everything is self-contained
├── AGENTS.md            # This file — project rules and structure
├── README.md            # Project overview
├── .gitignore           # Secrets and build-loop lock exclusions
├── .github/             # GitHub workflows
└── docs/
    ├── product/         # Product specs and PRD
    │   ├── PRD.md
    │   └── phases/      # Per-phase spec files
    ├── plan/            # Build loop state
    │   ├── progress.yaml
    │   ├── phase-goal.md
    │   ├── log/         # Phase execution logs
    │   └── archive/     # Completed phase logs
    ├── briefs/          # Design briefs
    └── concepts/        # Concept explorations
```

## Key files

- **`index.html`** — Static HTML page with embedded CSS and JS. Contains:
  - 4 humor sections: Core Metrics Dashboard (table), Incident Report, Team Morale Index, System Alerts
  - Interactive "Generate Synergy Report" button with 12 randomized outcomes
  - Dark theme with neon green/teal/amber/red color scheme
  - Georgia serif headings, Courier New monospace body
  - CSS animations (pulse glow, blink, slide-in, flash transition)

## Behavior rules

- No external dependencies — all CSS and JS are embedded in `index.html`
- Button outcomes use `textContent` (never `innerHTML`) for safety
- Event handlers use `addEventListener` (no inline `onclick` attributes)

## Quality checks

- no-silent-pass
- no-bare-except
- error-path-coverage
- agents-consistency
