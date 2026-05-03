# Test Cases — Shopping Cart Module

**Site:** https://www.saucedemo.com  
**Module:** Shopping Cart  
**Tester:** Ulker Aliyeva  
**Date:** 2024-06-17  
**Browser:** Chrome 124 / Windows 11  

---

## TC-007 — Add single item to cart

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-007 |
| **Module** | Cart |
| **Priority** | High |
| **Precondition** | Logged in as `standardemail@gmail.com`, on Products page |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Click **Add to cart** on "Sauce Labs Backpack" | Button changes to "Remove" |
| 2 | Check the cart icon (top right) | Badge shows number **1** |
| 3 | Click the cart icon | Cart page opens |
| 4 | Verify item is listed | "Sauce Labs Backpack" appears with correct price $29.99 |

**Expected Result:** Item added, cart badge = 1, item visible in cart.  
**Actual Result:** ✅ PASS

---

## TC-008 — Add multiple items to cart

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-008 |
| **Module** | Cart |
| **Priority** | High |
| **Precondition** | Logged in, on Products page, cart is empty |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Click **Add to cart** on "Sauce Labs Backpack" | Badge = 1 |
| 2 | Click **Add to cart** on "Sauce Labs Bike Light" | Badge = 2 |
| 3 | Click **Add to cart** on "Sauce Labs Bolt T-Shirt" | Badge = 3 |
| 4 | Open cart | All 3 items listed with correct names and prices |

**Expected Result:** Cart contains 3 items, badge = 3.  
**Actual Result:** ✅ PASS

---

## TC-009 — Remove item from cart (product page)

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-009 |
| **Module** | Cart |
| **Priority** | High |
| **Precondition** | 1 item already added to cart |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Find the item on Products page (button shows "Remove") | — |
| 2 | Click **Remove** | Button changes back to "Add to cart" |
| 3 | Check cart badge | Badge disappears (cart is empty) |

**Expected Result:** Item removed, badge gone.  
**Actual Result:** ❌ FAIL — See [BUG-002](../bug-reports/BUG-002.md)

---

## TC-010 — Remove item from cart page

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-010 |
| **Module** | Cart |
| **Priority** | Medium |
| **Precondition** | 2 items in cart, user is on Cart page |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Click **Remove** next to first item | Item disappears from cart list |
| 2 | Check remaining items | 1 item remains |
| 3 | Check cart badge | Badge shows **1** |

**Expected Result:** Correct item removed, 1 item remains.  
**Actual Result:** ✅ PASS

---

## TC-011 — Continue shopping from cart

| Field | Detail |
|-------|--------|
| **Test Case ID** | TC-011 |
| **Module** | Cart |
| **Priority** | Low |
| **Precondition** | User is on Cart page with 1 item |

**Steps:**

| # | Action | Expected Result |
|---|--------|-----------------|
| 1 | Click **Continue Shopping** button | User is returned to Products page |
| 2 | Check cart badge | Badge still shows previous count |

**Expected Result:** Navigation works, cart state preserved.  
**Actual Result:** ✅ PASS
