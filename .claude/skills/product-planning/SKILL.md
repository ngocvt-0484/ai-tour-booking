---
name: product-planning
description: Analyze product requirements and create an implementation plan before coding. Use this skill when planning a new feature or modifying existing product behavior.
---

# Product Planning Skill

## Purpose

Convert product requirements into a clear implementation plan before code changes are made.

This skill is responsible for planning only.

It must not implement application code.

---

## Sources of Truth

Use the following sources in this order:

1. `product_spec.md`
2. Existing application code
3. Existing tests

Do not invent product requirements.

---

## Workflow

### Step 1 — Read Requirements

Read the relevant sections of `product_spec.md`.

Identify:

- User story
- Business rules
- Expected behavior
- Acceptance criteria

Only consider requirements relevant to the requested feature.

### Step 2 — Inspect Existing Code

Inspect the current Rails application.

Look at relevant:

- models
- migrations
- controllers
- routes
- views
- tests

Prefer existing Rails patterns.

### Step 3 — Identify Required Changes

Determine:

- files to create
- files to modify
- database changes
- model changes
- controller changes
- view changes
- route changes
- tests

### Step 4 — Identify Business Rules

Explicitly list business rules that need enforcement.

Pay particular attention to:

- validations
- authorization
- state changes
- transactions
- data consistency

### Step 5 — Identify Risks

Look for:

- ambiguous requirements
- missing validation
- data consistency problems
- race conditions
- security issues
- regressions

### Step 6 — Produce Plan

Return a concise implementation plan containing:

1. Objective
2. Relevant requirements
3. Existing code to reuse
4. Files to create
5. Files to modify
6. Database changes
7. Business logic
8. Tests
9. Acceptance criteria
10. Risks

---

## Constraints

- Do not modify files.
- Do not write application code.
- Do not change product requirements.
- Do not introduce unnecessary architecture.
- Keep the solution appropriate for a small demo project.

---

## Expected Output

The output should be implementation-ready.

Another agent should be able to implement the feature using the plan without rediscovering the requirements.