# Test Cases - Cart & Checkout

Environment: desktop Chrome, 1280x720. Executed 2026-10-18 by Hafiz Hamdani.

| ID | Title | Steps | Expected result | standard_user | problem_user |
| --- | --- | --- | --- | --- | --- |
| TC-CART-001 | Add all products to cart | Click "Add to cart" on all 6 products | Cart badge shows 6; buttons switch to "Remove" | PASS (badge 6) | **FAIL -> BUG-002** (only 3 buttons respond; badge 3) |
| TC-CART-002 | Remove item from cart | Remove one product | Badge decrements; item leaves the cart page | PASS | PARTIAL (works on the 3 addable items) |
| TC-CART-003 | Cart persists across navigation | Add items, open a detail page, return | Cart contents unchanged | PASS | NOT RUN |
| TC-CART-004 | Cart page lists added items | Open cart | Every added item listed with price | NOT RUN | NOT RUN |
| TC-CHK-001 | Checkout information accepts valid input | Fill First Name, Last Name, Postal Code, Continue | All fields keep their values; advance to overview | PASS | **FAIL -> BUG-004** (Last Name input writes into First Name; "Error: Last Name is required") |
| TC-CHK-002 | Checkout requires First Name | Continue with empty form | Error "First Name is required" | NOT RUN | NOT RUN |
| TC-CHK-003 | Overview page after valid info | Complete info step | Advance to `/checkout-step-two.html` | PASS | BLOCKED by BUG-004 |
| TC-CHK-004 | Finish order | Click Finish on overview | Confirmation "Thank you for your order!" | PASS (verified 2026-10-18) | BLOCKED by BUG-004 |
| TC-CHK-005 | Cancel returns to inventory | Cancel from info step | Back to inventory; cart preserved | NOT RUN | NOT RUN |
| TC-CHK-006 | Order confirmation resets cart | Finish order, check badge | Cart badge cleared | NOT RUN | NOT RUN |
