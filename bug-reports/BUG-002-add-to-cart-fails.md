# BUG-002 - Half the catalog cannot be added to the cart

| Field | Value |
| --- | --- |
| Severity | Critical |
| Priority | High |
| Environment | SauceDemo, desktop Chrome, 1280x720 |
| Account | `problem_user` (passes on `standard_user`) |
| Found | 2026-10-18; reproduced 2/2 times, including after Reset App State |

## Summary

For 3 of the 6 products, clicking "Add to cart" does nothing - the cart badge
does not increment and the item never reaches the cart.

## Affected / unaffected items

| Product | Add to cart |
| --- | --- |
| Sauce Labs Backpack | Works |
| Sauce Labs Bike Light | Works |
| Sauce Labs Onesie | Works |
| Sauce Labs Bolt T-Shirt | **No effect** |
| Sauce Labs Fleece Jacket | **No effect** |
| Test.allTheThings() T-Shirt (Red) | **No effect** |

## Steps to reproduce

1. Log in as `problem_user`.
2. Click "Add to cart" on each of the 6 products, one at a time.

## Expected

Every click adds the item: the cart badge increments and the button switches
to "Remove" (verified behavior on `standard_user`, where all 6 work).

## Actual

Clicking Bolt T-Shirt, Fleece Jacket or Test.allTheThings() T-Shirt (Red)
changes nothing: badge stays at its previous value, the button keeps saying
"Add to cart", and the item is absent from the cart page. The three working
items add correctly (badge reaches 3).

## Evidence

![inventory after clicking all six](../screenshots/problem-user-inventory-bugs.png)
(cart badge shows 3 after all six buttons were clicked)

## Notes

Blocks purchase of half the catalog for this account. Related test case:
TC-CART-001.
