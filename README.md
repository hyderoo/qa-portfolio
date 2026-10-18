# QA Portfolio - Manual Testing Practice

Sample manual-QA deliverables (test plan, test cases, bug reports, exploratory
notes) produced against the **public** training app
[SauceDemo](https://www.saucedemo.com/). Every finding here was reproduced live
on **18 October 2026** and links to its evidence screenshot.

Why a demo app: real work products from my day job (banking QA) are
confidential, so this repo shows how I plan, document and report testing on a
target anyone can open.

> Practice portfolio by Hafiz Hamdani. Templates follow the structure taught in
> the ISTQB CTFL v4.0 syllabus. SauceDemo is a deliberately buggy training app;
> the bug reports document its real, reproduced behavior.

## Contents

| Area | File(s) |
| --- | --- |
| Test plan | [test-plan/test-plan-saucedemo.md](test-plan/test-plan-saucedemo.md) |
| Test cases | [test-cases/](test-cases/) (login, inventory, cart & checkout - 24 cases, 20 executed, 4 not run) |
| Bug reports | [bug-reports/](bug-reports/) (4 defects, all reproduced live) |
| Exploratory notes | [exploratory/session-2026-10-18.md](exploratory/session-2026-10-18.md) |
| Evidence | [screenshots/](screenshots/) |

## Findings summary (all reproduced 2026-10-18)

| ID | Summary | Severity | User |
| --- | --- | --- | --- |
| BUG-001 | All product images render as the same placeholder | Major | problem_user |
| BUG-002 | 3 of 6 products cannot be added to the cart | Critical | problem_user |
| BUG-003 | Price sorting has no effect on product order | Major | problem_user |
| BUG-004 | Last Name input writes into First Name, checkout blocked | Critical | problem_user |

The same scenarios pass on the `standard_user` account - see the execution
evidence in the test cases.
