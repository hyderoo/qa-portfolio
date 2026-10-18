# Test Plan - SauceDemo Web Shop

| Field | Value |
| --- | --- |
| Project | SauceDemo (https://www.saucedemo.com/) - practice target |
| Author | Hafiz Hamdani |
| Date | 2026-10-18 |
| Status | Executed (first pass complete) |

## 1. Objectives

Verify the core shopping flow - login, product browsing, sorting, cart and
checkout - behaves correctly for the standard demo account, and characterize
the behavior of the intentionally faulty accounts shipped with the app.

## 2. Scope

**In scope**

- Login (valid, locked-out, empty-field validation)
- Product list: content, images, prices
- Sorting (name A-Z/Z-A, price low-high/high-low)
- Cart: add, remove, badge counter, item persistence
- Checkout: information form validation, overview, completion

**Out of scope**

- Performance/load testing, security testing, accessibility audit
- Mobile native apps, browser-compatibility matrix beyond desktop Chrome
- Any non-public system

## 3. Test items and environment

- Application: https://www.saucedemo.com/ (public training app)
- Accounts under test: `standard_user` (reference), `problem_user`,
  `locked_out_user` (credentials published on the login page)
- Environment: desktop Chrome, 1280x720 viewport, executed 2026-10-18 (WIB)

## 4. Approach

- Scripted functional cases derived from the visible requirements (the app's
  own labels, prices and flow), each with preconditions, steps and expected
  results - see `test-cases/`.
- Exploratory charter on the faulty accounts, time-boxed, findings filed as
  bug reports with screenshots - see `exploratory/`.
- Defects are reported with severity (impact) and priority (fix order) as
  separate fields, per ISTQB practice.

## 5. Entry / exit criteria

- Entry: app reachable, demo credentials available on the login page.
- Exit: all planned cases executed; every failure has a filed bug report with
  reproduction steps and evidence.

## 6. Risks

| Risk | Mitigation |
| --- | --- |
| Demo app content can change without notice | Record execution date and evidence for every result |
| Faulty accounts behave inconsistently by design | Reproduce each finding at least twice before filing |

## 7. Deliverables

Test cases with execution results, bug reports with evidence, exploratory
session notes - all in this repository.
