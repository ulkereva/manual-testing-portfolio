# Test Cases — Login Module

**Site:** https://www.saucedemo.com  
**Module:** Login  
**Tester:** Ulker Aliyeva  
**Date:** 2024-06-15  
**Browser:** Chrome 124 / Windows 11  

---

## TC-001 — Valid user login

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-001 |
| **Module** | Login |
| **Priority** | High |
| **Precondition** | User is on https://www.saucedemo.com, not logged in |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Open https://www.saucedemo.com | Login page is displayed with username, password fields and Login button |
| 2 | Enter email: `standardemail@gmail.com` | Email field accepts input |
| 3 | Enter password: `secret_sauce` | Password is masked with dots |
| 4 | Click **Login** button | User is redirected to the Products page |
| 5 | Check page title | "Products" heading is visible |

**Expected Result:** User successfully logs in and sees the Products page.  
**Actual Result:** ✅ PASS — Products page displayed correctly.

---

## TC-002 — Login with invalid password

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-002 |
| **Module** | Login |
| **Priority** | High |
| **Precondition** | User is on login page |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Enter email: `standardemail@gmail.com` | Accepted |
| 2 | Enter password: `wrongpassword` | Masked input accepted |
| 3 | Click **Login** | Error message is shown |

**Expected Result:** Error message: *"Username and password do not match any user in this service"*  
**Actual Result:** ✅ PASS — Correct error message displayed.

---

## TC-003 — Login with empty username

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-003 |
| **Module** | Login |
| **Priority** | Medium |
| **Precondition** | User is on login page |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Leave username field empty | — |
| 2 | Enter password: `secret_sauce` | Accepted |
| 3 | Click **Login** | Validation error shown |

**Expected Result:** Error: *"Username is required"*  
**Actual Result:** ✅ PASS

---

## TC-004 — Login with empty password

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-004 |
| **Module** | Login |
| **Priority** | Medium |
| **Precondition** | User is on login page |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Enter email: `standardemail@gmail.com` | Accepted |
| 2 | Leave password field empty | — |
| 3 | Click **Login** | Validation error shown |

**Expected Result:** Error: *"Password is required"*  
**Actual Result:** ✅ PASS

---

## TC-005 — Locked out user login

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-005 |
| **Module** | Login |
| **Priority** | High |
| **Precondition** | User is on login page |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Enter email: `lockedoutuseremail@gmail.com` | Accepted |
| 2 | Enter password: `secret_sauce` | Accepted |
| 3 | Click **Login** | Clear error message shown explaining account is locked |

**Expected Result:** Error message explains the account is locked.  
**Actual Result:** ❌ FAIL — See [BUG-001](../bug-reports/BUG-001.md)

---

## TC-006 — Logout functionality

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-006 |
| **Module** | Login |
| **Priority** | Medium |
| **Precondition** | User is logged in as `standard_user` |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Click the hamburger menu (top left) | Sidebar opens |
| 2 | Click **Logout** | User is redirected to login page |
| 3 | Try to go back (browser back button) | User is NOT returned to Products page — stays on login |

**Expected Result:** Session is fully cleared after logout.  
**Actual Result:** ✅ PASS
