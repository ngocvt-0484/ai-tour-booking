# AI Tour Booking — Claude Instructions

## Project

This is a small Ruby on Rails tour booking demo.

The primary purpose of this project is to demonstrate AI-driven software development using Claude Code, Agent Skills, specialized agents, and harness engineering.

The product requirements are defined in:

`product_spec.md`

`product_spec.md` is the source of truth for product behavior.

---

## Technology

- Ruby
- Ruby on Rails 8.1
- SQLite
- Hotwire
- ERB
- Minitest

Prefer Rails conventions and simple solutions.

---

## AI Development Rules

Before implementing a feature:

1. Read `product_spec.md`.
2. Inspect the existing codebase.
3. Identify the relevant Agent Skill.
4. Create an implementation plan.
5. Implement only the required scope.
6. Add automated tests.
7. Run verification.
8. Review the final git diff.

---

## Product Rules

Do not invent product requirements.

If requirements are ambiguous, identify the ambiguity before implementation.

Do not silently change the product specification.

---

## Engineering Rules

Prefer:

- Rails conventions
- Simple code
- Small changes
- Explicit business rules
- Automated tests

Avoid unnecessary:

- abstractions
- service objects
- repositories
- design patterns
- dependencies

unless there is a clear reason.

---

## Git Rules

Do not modify unrelated files.

Before completing a feature:

- inspect `git diff`
- run tests
- run quality checks
- summarize the changes

Do not create commits unless explicitly requested.

---

## Agent Skill Rules

Use Agent Skills when a relevant skill exists.

Skills are stored under:

`.claude/skills/`

Do not duplicate detailed skill instructions inside this file.

`CLAUDE.md` defines global project rules.

Agent Skills define specialized workflows.