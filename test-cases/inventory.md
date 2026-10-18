# Test Cases - Product Inventory & Sorting

Environment: desktop Chrome, 1280x720. Executed 2026-10-18 by Hafiz Hamdani.
Reference account: `standard_user`. Comparison account: `problem_user`.

| ID | Title | Steps | Expected result | standard_user | problem_user |
| --- | --- | --- | --- | --- | --- |
| TC-INV-001 | All products listed | Log in, open inventory | 6 products, each with name, description, price, image | PASS (6 items) | PASS (6 items) |
| TC-INV-002 | Product images are distinct and load | Inspect the 6 product images | Each product shows its own, non-broken image | PASS (6 distinct images) | **FAIL -> BUG-001** (all 6 show the same placeholder) |
| TC-INV-003 | Sort by price, high to low | Select "Price (high to low)" | First product is the most expensive ($49.99) | PASS | **FAIL -> BUG-003** (first price stays $29.99) |
| TC-INV-004 | Sort by price, low to high | Select "Price (low to high)" | First product is the cheapest ($7.99) | PASS | **FAIL -> BUG-003** (first price stays $29.99) |
| TC-INV-005 | Sort by name Z to A | Select "Name (Z to A)" | Alphabetically reversed order | PASS (first: "Test.allTheThings() T-Shirt (Red)") | **FAIL -> BUG-003** (order unchanged, first stays "Sauce Labs Backpack") |
| TC-INV-006 | Product detail page | Click a product name | Detail page with matching name, price, image | PASS (verified on "Sauce Labs Onesie") | NOT RUN |
