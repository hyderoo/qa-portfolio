# Test Cases - Login

Environment: desktop Chrome, 1280x720. Executed 2026-10-18 by Hafiz Hamdani.

| ID | Title | Preconditions | Steps | Expected result | Result |
| --- | --- | --- | --- | --- | --- |
| TC-LOG-001 | Login with valid credentials | On login page | 1. Enter `standard_user` 2. Enter `secret_sauce` 3. Click Login | Redirected to `/inventory.html`; 6 products shown | PASS |
| TC-LOG-002 | Locked-out account is rejected | On login page | 1. Enter `locked_out_user` 2. Enter `secret_sauce` 3. Click Login | Stays on login page; error "Epic sadface: Sorry, this user has been locked out." | PASS (error verified: "Epic sadface: Sorry, this user has been locked out.") |
| TC-LOG-003 | Empty username rejected | On login page | 1. Leave username empty 2. Enter password 3. Click Login | Error "Username is required" | PASS (verified: "Epic sadface: Username is required") |
| TC-LOG-004 | Empty password rejected | On login page | 1. Enter username 2. Leave password empty 3. Click Login | Error "Password is required" | PASS (verified: "Epic sadface: Password is required") |
| TC-LOG-005 | Wrong password rejected | On login page | 1. Enter `standard_user` 2. Enter wrong password 3. Click Login | Error about credentials not matching any user | PASS (verified: "Epic sadface: Username and password do not match any user in this service") |
| TC-LOG-006 | Logout returns to login page | Logged in | 1. Open menu 2. Click Logout | Back on login page; session cleared | PASS |
