# Project State

## Project Reference

See: .planning/PROJECT.md (updated 2026-02-06)

**Core value:** Every WordPress developer using Claude Code gets comprehensive, expert-level code review and development guidance across all major WordPress domains.
**Current focus:** Phase 2 complete — ready for Phase 3

## Current Position

Phase: 3 of 5 (Gutenberg Blocks) — IN PROGRESS
Plan: 2 of 3 in current phase
Status: In progress
Last activity: 2026-02-06 — Completed 03-02-PLAN.md

Progress: [█████████░] 53% (8/15 plans complete)

## Performance Metrics

**Velocity:**
- Total plans completed: 8
- Average duration: 10 minutes
- Total execution time: 1.40 hours

**By Phase:**

| Phase | Plans | Total | Avg/Plan |
|-------|-------|-------|----------|
| 01 Security Review | 3/3 | 15m | 5m |
| 02 Plugin Dev | 3/3 | 53m | 18m |
| 03 Gutenberg | 2/3 | 15m | 8m |
| 04 Theme Dev | 0/3 | - | - |
| 05 WooCommerce | 0/3 | - | - |

**Recent Trend:**
- Last 5 plans: 02-02 (28m), 02-03 (~1m), 03-01 (5m), 03-02 (10m)
- Trend: Slash command plans complete in ~1 minute; SKILL.md plans complete in 5 minutes; reference doc plans complete in 10-28 minutes

*Updated after each plan completion*

## Accumulated Context

### Decisions

Decisions are logged in PROJECT.md Key Decisions table.
Recent decisions affecting current work:

- Code-level security only (no server hardening) — keeps skill focused on what Claude can review
- Full-stack Gutenberg coverage (PHP + React/JSX) — WP 6.x+ block development requires both patterns
- Same slash command pattern per skill (full + quick) — consistent UX proven by performance skill
- All 5 skills at same depth — consistent quality, no half-built skills
- WP 6.x+ target only — modern APIs without legacy compatibility burden
- Dependency-driven build order — Security → Plugin → Gutenberg → Theme → WooCommerce
- CWE references in security findings (01-01) — industry-standard vulnerability classification
- Context-aware severity (01-01) — admin vs public code gets different risk levels
- Three-pillar security model (01-01) — sanitize, authorize, escape framework
- Late escaping emphasis (01-01) — escape at output, not storage
- Cookbook format for references (01-02) — quick lookup + detailed patterns proven by performance skill
- BAD/GOOD code pairs throughout (01-02) — side-by-side comparison most effective for learning
- False positive documentation (01-02) — explicitly document when security measures aren't needed
- Security crossover pattern (02-01) — cross-reference wp-security-review instead of duplicating security patterns
- Context-aware plugin detection (02-01) — WordPress.org vs private vs mu-plugin vs drop-in contexts adjust severity
- WordPress PHP Coding Standards in all examples (02-01) — spaces in parens, array() not [], Yoda conditions
- Cookbook format for plugin references (02-02) — quick reference table + patterns + edge cases + WP nuances, proven effective
- Cross-references between reference docs (02-02) — architecture → hooks → OOP → API creates navigation paths
- Security cross-references in APIs (02-02) — permission_callback, nonces, capabilities point to wp-security-review skill
- dbDelta quirks documented (02-02) — two spaces after PRIMARY KEY critical for WordPress custom table creation
- Slash command delegation pattern (02-03) — /wp-plugin-review and /wp-plugin mirror security command structure exactly
- First dual-language skill (03-01) — wp-block-development covers both PHP and JavaScript/React with separate BAD/GOOD patterns
- Source vs build review (03-01) — review src/ files for code patterns, flag missing/stale build/, don't review build/ for quality
- Grep patterns differ by language (03-01) — JS patterns need different regex than PHP, documented with --include flags
- Interactivity API scoping (03-01) — WP 6.5+ frontend-only, editor still React, version markers throughout
- apiVersion 3 className injection (03-02) — NOT auto-injected in save, must use useBlockProps.save() explicitly, migration guide critical
- InnerBlocks dynamic block gotcha (03-02) — MUST return InnerBlocks.Content in save even if dynamic, $content contains saved inner blocks
- DO NOT escape $content (03-02) — wp_kses_post() breaks core/embed blocks, inner blocks already sanitized
- viewScriptModule required (03-02) — Interactivity API needs ES modules, viewScript doesn't support imports

### Pending Todos

None yet.

### Blockers/Concerns

None yet.

## Session Continuity

Last session: 2026-02-06
Stopped at: Completed 03-02-PLAN.md (Block Development Reference Docs)
Resume file: None
Next action: Continue Phase 3 with 03-03-PLAN.md (Slash Commands) to complete Gutenberg phase
