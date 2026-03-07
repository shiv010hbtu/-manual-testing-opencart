# Manual Testing Project – OpenCart

## About This Project

I chose OpenCart demo as my application under test because it covers real-world e-commerce functionality. The goal was to test the core user flows end-to-end — from login to adding items to cart — and document any bugs found along the way.

**Application Under Test:** https://demo.opencart.com  
**Testing Type:** Manual (Black Box)  
**Executed By:** Shivendra Pal  

---

## What I Tested

I divided the testing into 4 modules based on the user journey:

**1. Login Module** — 8 test cases  
Covered valid login, invalid credentials, empty fields, SQL injection, case sensitivity, forgot password, and edge cases like leading spaces in email.

**2. Registration Module** — 7 test cases  
Covered new user registration, duplicate email, password validation, privacy policy toggle, and empty field checks.

**3. Search Module** — 7 test cases  
Covered valid search, lowercase input, partial keywords, empty search, special characters, numeric input, and non-existent products.

**4. Cart Module** — 7 test cases  
Covered add to cart, view cart, update quantity, remove item, adding same product twice, cart persistence after refresh, and checkout flow.

---

## Test Results

| Module | Total TCs | Pass | Fail |
|--------|-----------|------|------|
| Login | 8 | 5 | 3 |
| Registration | 7 | 6 | 1 |
| Search | 7 | 6 | 1 |
| Cart | 7 | 6 | 1 |
| **Total** | **29** | **23** | **6** |

---

## Bugs I Found

| Bug ID | Module | Summary | Severity |
|--------|--------|---------|----------|
| BUG_001 | Login | Empty fields submission shows auth error instead of field validation | Major |
| BUG_002 | Login | Invalid email format accepted, no format validation on login | Major |
| BUG_003 | Login | Email with leading space fails silently — no error message | Minor |
| BUG_004 | Registration | No "Confirm Password" field — user can set wrong password without realizing | Critical |
| BUG_005 | Search | Empty search shows "no products found" instead of "please enter a keyword" | Minor |
| BUG_006 | Cart | Out-of-stock item gets added to cart but blocks checkout with no clear guidance | Major |

The most critical one I found was BUG_004 — there is no confirm password field during registration, which means a user could accidentally mistype their password and never know. This is a standard UX requirement that's missing.

---

## Files in This Repo

```
├── OpenCart_Login_TestCases.xlsx   → All test cases + bug report + summary
├── screenshots/                    → Evidence screenshots for each test
│   ├── login/
│   ├── registration/
│   ├── search/
│   └── cart/
└── README.md
```

The Excel file has 6 sheets — one per module, then bug report, then overall summary.

---

## Tools Used

- Chrome browser for test execution
- Excel for writing and tracking test cases
- Snipping Tool for capturing screenshots
- GitHub for version control

---

## What I Learned

Writing test cases from scratch made me think about both positive and negative scenarios. I initially missed edge cases like SQL injection and leading spaces — I added those after thinking about what could actually go wrong in a real application. Finding BUG_006 (OOS item blocking checkout) was interesting because the add-to-cart worked fine, but the failure happened later at checkout — this is a good example of why end-to-end testing matters.

---
SHIVENDRA PAL | FINAL BTECH IT | HBTU KANPUR 
