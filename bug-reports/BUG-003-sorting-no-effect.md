# BUG-003 - Product sorting has no effect

| Field | Value |
| --- | --- |
| Severity | Major |
| Priority | Medium |
| Environment | SauceDemo, desktop Chrome, 1280x720 |
| Account | `problem_user` (passes on `standard_user`) |
| Found | 2026-10-18; reproduced for all 4 sort options, each from a fresh page load |

## Summary

The sort control accepts a selection but the product order never changes.

## Steps to reproduce

1. Log in as `problem_user`.
2. Select each option of the sort dropdown in turn: Name (Z to A),
   Price (low to high), Price (high to low).

## Expected

Order changes per selection. Reference (`standard_user`, verified same day):
- Price (high to low): first product $49.99 (Fleece Jacket)
- Price (low to high): first product $7.99 (Onesie)
- Name (Z to A): first product "Test.allTheThings() T-Shirt (Red)"

## Actual

For `problem_user` every option leaves the list in the default order
(first product "Sauce Labs Backpack", $29.99). Measured on fresh page loads
per option to rule out UI-state artifacts.

| Option selected | First product shown | Correct? |
| --- | --- | --- |
| Name (A to Z) | Sauce Labs Backpack | yes |
| Name (Z to A) | Sauce Labs Backpack | no |
| Price (low to high) | Sauce Labs Backpack ($29.99) | no |
| Price (high to low) | Sauce Labs Backpack ($29.99) | no |

## Notes

Also blocks TC-INV-005 (name sorting). Related test cases: TC-INV-003,
TC-INV-004, TC-INV-005.
