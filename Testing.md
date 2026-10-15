# Testing

### Introduction to Testing:
Testing confirms that the Online Food Ordering Sy stem for QAU Huts works correctly and meets its requirements before deployment. This chapter covers three types of testing : Acceptance Testing, Unit Testing, and Functional Test Cases. The goal is to check that every part of the system works in both normal and unusual conditions , and that it meets the expectations of customers , hut admins , and delivery staff .

All tests are based on the use cases in Chapter 3 and the requirements in the document. Each test is linked to a specific use case or requirement.

### Acceptance Testing:
Acceptance testing validates complete work flows from the end user 's point of view , using realistic scenarios . Each scenario below restarts its step numbering at 1 .

#### AT-01: Student orders food successfully:
1. Student logs in with valid details.
2. Student browses the menu and selects 2 items.
3. Student adds the items to the cart and proceeds to checkout.
4. Student selects "Deliver to My Department" and enters the location.
5. Student pays via JazzCash or another supported method.
6. System generates an Order ID and sends a confirmation notification.

**Expected Result:** Order is saved with status "Order Received". Admin receives a new-order notification . Student receives an Order ID.  
**Outcome:** Pass

#### AT-02: Admin processes an order, end to end:
1. Admin receives a notification of a new order.
2. Admin reviews the order and clicks " Accept Order".
3. Status changes to " Being Prepared" and the customer is notified.
4. Admin marks the food as re ady and assigns a delivery staff member.
5. Delivery staff delivers the order and updates the status to "Delivered".
6. Customer receives a delivery notification .

**Expected Result:** Order status moves through all stages . Customer sees real-time updates . Delivery staff is notified and completes the delivery .  
**Outcome:** Pass

#### AT-03: Student cancels an order within the allowed window
1. Student places an order.
2. Within 3 minutes, student opens "My Orders".
3. Student clicks "Cancel Order" and confirms.
4. System sets the status to "Cancelled" and starts the refund.

**Expected Result:** Status is "Cancelled". Online refund is triggered. Admin is notified not to prepare the order.  
**Outcome:** [Fill in after running: Pass / Fail]

#### AT-04: Student submits feedback after delivery
1. Delivery staff updates the order status to "Delivered".
2. Student receives a "Rate your order" notification.
3. Student taps the notification, gives 4 stars, and writes a comment.
4. Student taps "Submit Feedback".

**Expected Result:** Feedback is saved. Average rating of the items is updated. Admin can view the feedback on the dashboard.  
**Outcome:** Pass

#### AT-05: Admin adds a food item to the menu:
1. Admin logs in to the admin dashboard.;
2. Admin opens Menu Managemeent and clicks "Add New Item".
3. Admin enters name , category , price, description, and uploads a photo .
4. Admin marks the item as available and clicks Save.

**Expected Result:** New item is saved to the database and appears immediately in the customer menu .  
**Outcome:** Pass

---

### Unit Testing
Unit testing checks that each method or class works correctly on its own , independent of the rest of the system . The following unit tests cover the core services and repository classes .

| ID | Method / Module | Test Description | Input | Expected Output | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| UT01 | UserRepository.save | Save a new valid user | User object with all required fields | User stored and userId assigned | Pass |
| UT02 | UserRepository.findByEmail | Find user by existing email | Registered email | Correct User object returned | Pass |
| UT03 | OTP.generateOTP | Generate a 6-digit OTP | No input | 6-digit numeric code | Pass |
| UT04 | OTP.verifyOTP | Verify correct OTP before expiry | Correct OTP code | Returns true; isVerified set to true | Pass |
| UT05 | OTP.verifyOTP | Verify OTP after expiry | Correct code, entered after expiry | Returns false | Pass |
| UT06 | AuthService.login | Login with correct details | Valid email and password | Returns true; session created | Pass |
| UT07 | AuthService.login | Login with wrong password | Valid email, wrong password | Returns false | Pass |
| UT08 | MenuService.searchMenu | Search for an existing item | keyword = "biryani" | List of matching MenuItem objects | Pass |
| UT09 | MenuService.searchMenu | Search with no matches | keyword = "xyz123" | Empty list returned | Pass |
| UT10 | MenuService.getMenuByCategory | Get items by category | categoryId = 2 | List of items in that category | Pass |
| UT11 | Order.calculateTotal | Calculate total for 2 items | Item1 = 150, Item2 = 250 | Returns 400.00 | Pass |
| UT12 | OrderService.createOrder | Create order with available items | userId, list of available items | Order created with status "Order Received" | Pass |
| UT13 | OrderService.processPayment | Process a valid payment | Valid orderId and payment method | Returns true; payment record saved | Pass |
| UT14 | OrderService.cancelOrder | Cancel order in "Order Received" status | orderId with status "Order Received" | Status set to "Cancelled"; refund initiated | Pass |
| UT15 | OrderService.cancelOrder | Cancel order in "Being Prepared" status | orderId with status "Being Prepared" | Cancellation blocked | Pass |
| UT16 | OrderStatusHistory.getHistory | Retrieve status history | Valid orderId | Ordered list of status history entries | Pass |
| UT17 | FeedbackService.submitFeedback | Submit valid feedback | orderId, rating = 5, comment = "Great food" | Feedback stored; average rating updated | Pass |
| UT18 | FeedbackService.submitFeedback | Submit feedback for an already reviewed order | orderId that already has feedback | Error returned; duplicate feedback rejected | Pass |
| UT19 | NotificationService.notifyOrderCancellation | Notify on order cancellation | Valid orderId | Push notification sent to user and admin | Pass |
| UT20 | MenuService.addMenuItem | Add item with all fields | Valid MenuItem object | Item saved and immediately available | Pass |

---

### 7.4 Functional Test Cases
The table below lists the functional test cases. Each is linked to a use case in Chapter 3 and checks normal and alternate flows.

| ID | Use Case | Test Description | Input | Expected Output | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| TC01 | User Registration | Valid registration | Full name, QAU email, department, strong password | OTP sent; account created | Pass |
| TC02 | User Registration | Email already registered | Existing email | Error: "Account already exists. Please log in." | Pass |
| TC03 | User Registration | OTP entered after 5-minute expiry | Expired OTP | System offers to request a new OTP | Pass |
| TC04 | User Registration | Incorrect OTP three times | Wrong OTP x3 | Registration blocked for 10 minutes | Pass |
| TC05 | User Registration | Empty required field | Password field missing | Empty field highlighted; submission prevented | Pass |
| TC06 | User Login | Correct credentials | Valid email, correct password | User logged in and sent to dashboard | Pass |
| TC07 | User Login | Wrong password | Valid email, wrong password | Error: "Incorrect password. Please try again." | Pass |
| TC08 | User Login | Lockout after 5 failed attempts | Wrong password x5 | Account locked for 15 minutes | Pass |
| TC09 | User Login | Forgot password flow | Registered email | OTP sent; password reset successful | Pass |
| TC10 | Search Food Menu | Browse all categories | User opens menu section | All categories shown (breakfast, lunch, dinner, etc.) | Pass |
| TC11 | Search Food Menu | Search by item name | Keyword "Biryani" | Matching items shown with name, price, photo | Pass |
| TC12 | Search Food Menu | Filter by availability | Filter: Available only | Only in-stock items shown; unavailable items greyed out | Pass |
| TC13 | Search Food Menu | Menu fails to load | No internet connection | Error: "Unable to load menu. Please check your connection." | Pass |
| TC14 | Place Food Order | Add items and place order | 2 items, delivery, Easypaisa payment | Order confirmed; unique Order ID generated; admin notified | Pass |
| TC15 | Place Food Order | Payment fails | Invalid payment details | Error shown; user offered retry or another method | Pass |
| TC16 | Place Food Order | Item unavailable before checkout | Item goes out of stock after being added to cart | User notified and asked to remove or replace it | Pass |
| TC17 | Place Food Order | Delivery location outside campus | Off-campus address | Error shown; user asked to correct location | Pass |
| TC18 | Track Order Status | Track an active order | User opens My Orders and selects an active order | Step-by-step status displayed | Pass |
| TC19 | Track Order Status | Push notification on status change | Admin sets status to Out for Delivery | User receives push notification | Pass |
| TC20 | Track Order Status | Cancelled order display | Order cancelled by user | Status shows "Order Cancelled" with reason | Pass |
| TC21 | Cancel Order | Cancel within 3 minutes | Order in "Order Received" status; Cancel clicked | Order cancelled; refund initiated; admin notified | Pass |
| TC22 | Cancel Order | Cancel an order already being prepared | Status "Being Prepared" | Cancel button disabled; message shown | Pass |
| TC23 | Cancel Order | Refund error during cancellation | Automatic refund fails | Order flagged for manual review by System Admin | Pass |
| TC24 | Admin Manages Menu | Add item with all details | Name, category, price, description, photo | Item saved and visible to customers immediately | Pass |
| TC25 | Admin Manages Menu | Add item with missing price | Price left empty | Missing field highlighted; saving prevented | Pass |
| TC26 | Admin Manages Menu | Update item price | Select item; change price; save | Updated price saved and shown in menu | Pass |
| TC27 | Admin Manages Menu | Delete a menu item | Select item; click Delete; confirm | Item removed and no longer visible to customers | Pass |
| TC28 | Admin Processes Order | Accept order and update status | New order notification; admin clicks Accept | Status "Being Prepared"; customer notified | Pass |
| TC29 | Admin Processes Order | Assign order to delivery staff | Food ready; admin selects available staff | Delivery staff notified; status updated | Pass |
| TC30 | Admin Processes Order | Item out of stock after order | Item found unavailable after accepting | Admin contacts customer in app to replace or cancel | Pass |
| TC31 | Submit Feedback | Rating and comment after delivery | 5 stars plus comment | Feedback saved; thank-you message; average rating updated | Pass |
| TC32 | Submit Feedback | Feedback after 24-hour window | Attempt 25 hours after delivery | Feedback option no longer available for that order | Pass |

---

### 7.5 Testing Summary
The table below summarizes the results of all three types of testing.

| Testing Type | Total Tests | Passed | Failed |
| :--- | :--- | :--- | :--- |
| Acceptance Testing | 5 | 4 (AT-03 pending) | 0 |
| Unit Testing | 20 | 20 | 0 |
| Functional Test Cases | 32 | 32 | 0 |
| **Total** | **57** | **56 (+1 pending)** | **0** |

Once AT-03 is run and its outcome recorded , update the table. When all tests pass, the results confirm that :
* All nine use cases work as described in this SRS.
* Core service and repository methods work correctly in isolation.
* End-to-end flows from registration and ordering to deli very and feedback work without errors.
* Error handling , input validation , and notifications work as expected .
* Security features such as account lock out and OTP verification work correctly .