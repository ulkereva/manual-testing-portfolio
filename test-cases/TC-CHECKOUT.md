# Test Cases — Checkout Module

**Site:** https://www.saucedemo.com  
**Module:** Checkout  
**Tester:** Ulker Aliyeva  
**Date:** 2024-06-18  
**Browser:** Chrome 124 / Windows 11  

---

## TC-012 — Successful checkout flow

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-012 |
| **Module** | Checkout |
| **Priority** | High |
| **Precondition** | 1 item in cart, user on Cart page |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Click **Checkout** | Checkout Step 1 page opens (Your Information) |
| 2 | Enter First Name: `Name` | Accepted |
| 3 | Enter Last Name: `Surname` | Accepted |
| 4 | Enter Zip Code: `AZ1234` | Accepted |
| 5 | Click **Continue** | Checkout Step 2 (Overview) opens |
| 6 | Verify item, subtotal, tax, total | Correct values shown |
| 7 | Click **Finish** | Order confirmation page shown |
| 8 | Check confirmation message | "Thank you for your order!" displayed |

**Expected Result:** Full checkout completes successfully.  
**Actual Result:** ✅ PASS

---

## TC-013 — Checkout with empty First Name

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-013 |
| **Module** | Checkout |
| **Priority** | High |
| **Precondition** | 1 item in cart, user on Checkout Step 1 |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Leave First Name empty | — |
| 2 | Enter Last Name: `Surname` | Accepted |
| 3 | Enter Zip: `AZ1234` | Accepted |
| 4 | Click **Continue** | Validation error shown for First Name |

**Expected Result:** Error: *"First Name is required"*  
**Actual Result:** ❌ FAIL — See [BUG-003](../bug-reports/BUG-003.md)

---

## TC-014 — Checkout with empty Zip Code

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-014 |
| **Module** | Checkout |
| **Priority** | Medium |
| **Precondition** | User on Checkout Step 1 |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Enter First Name: `Name` | Accepted |
| 2 | Enter Last Name: `Surname` | Accepted |
| 3 | Leave Zip Code empty | — |
| 4 | Click **Continue** | Validation error for Zip Code |

**Expected Result:** Error: *"Postal Code is required"*  
**Actual Result:** ✅ PASS

---

## TC-015 — Price total verification on Overview page

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-015 |
| **Module** | Checkout |
| **Priority** | High |
| **Precondition** | "Sauce Labs Backpack" ($29.99) in cart, user on Overview page |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Check Item total | $29.99 |
| 2 | Check Tax (8%) | $2.40 |
| 3 | Check Total | $32.39 |

**Expected Result:** Total = Item price + Tax, calculated correctly.  
**Actual Result:** ✅ PASS — Math verified manually.
