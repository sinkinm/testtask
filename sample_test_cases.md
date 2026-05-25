# Smoke E2E Test Suite (Happy Path Integration Flow)

This is a happy path integration flow UI test suite, usable as a smoke E2E set.

---

## TC-01: User Authentication

**Linked Requirement:** The system must authenticate valid user credentials and establish a secure session.

**Preconditions:**
- The user possesses valid, active account credentials for testing (not to be disclosed publicly).
- The user is currently logged out.

**Steps:**
1. Navigate to the /login page.
2. Provide the valid username and password.
3. Execute the "Login" action.

**Expected Results:**
The system authenticates the user, giving them access to restricted pages (/catalog, /cart, /profile), and redirects the user to the /catalog page.

---

## TC-02: Adding items to the Cart

**Linked Requirement:** The system must accurately register a selected asset into the user's cart without requiring a state refresh.

**Preconditions:**
- The user is logged in.
- The cart is completely empty.

**Steps:**
1. Navigate to the /catalog page.
2. Using search by name, choose three VM plans (Ultra-4, Ultra-2, Ultra-1) with corresponding values: $11.50/hr, $5.90/hr, $3.00/hr.
3. Click the "Add to Cart" button against each VM plan.

**Expected Results:**
- The UI cart counter increments each time the user presses “Add to Cart”.
- The cart contains three chosen VM plans.

---

## TC-03: Cart Total Value calculation

**Linked Requirement:** The system must calculate the correct total value for the Cart entries.

**Preconditions:**
- The user is logged in.
- TC-02 is successfully executed.
- Cart contains three VM plans with values: $11.50/hr, $5.90/hr, $3.00/hr.

**Steps:**
1. Go to the /cart page.
2. Check the 'Total per hour' caption.

**Expected Results:**
The "Total per hour" value equals the exact arithmetic sum of all items’ values ($20.40 total).

---

## TC-04: Payment Execution via Credit Card

**Linked Requirement:** The system must process a transaction and generate a valid order ID when provided with structurally valid payment data.

**Preconditions:**
- The user is logged in.
- TC-03 is successfully executed.
- The cart contains several items with a total value $20.40 per hour.

**Steps:**
1. Go to the /cart page.
2. Click “Pay Now” button.
3. Provide valid payment card data (not to be disclosed publicly).
4. Click the “Confirm Payment” button.

**Expected Results:**
- UI shows a message that payment is successful.
- The backend returns a 200 OK status.
- A success message is generated containing a non-empty order_id.
- The amount is equal to the amount shown in the UI ($20.40).

---

## TC-05: Post-Transaction Cart Flush

**Linked Requirement:** The system must automatically empty the cart after a successful transaction.

**Preconditions:**
- User has successfully executed TC-04 (order placed successfully).
- The user remains in the post-checkout state.

**Steps:**
1. Check the cart contents and the UI state.

**Expected Results:**
- The cart is emptied.
- The message "The cart is empty" is shown.

---

## TC-06: Asset Provisioning on Profile

**Linked Requirement:** The system must accurately increment the "Owned Assets" counter on the user's profile immediately after a completed order.

**Preconditions:**
- User has successfully executed TC-04, acquiring three VM plans.
- The user had no owned assets prior to executing TC-04.

**Steps:**
1. Go to the /profile page.
2. Check “Owned Assets” table on the /profile page.
3. Check the "Owned Assets" counter for the current user.

**Expected Results:**
- The "Owned Assets" counter on the /profile is equal to 3.
- There are three acquired assets in the table which the user has purchased: $11.50/hr, $5.90/hr, $3.00/hr per hour.