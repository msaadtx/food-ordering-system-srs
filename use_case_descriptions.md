# Use Case Descriptions

---

### Use case#01: 3.1 User Registration

| Field | Details |
| :--- | :--- |
| **Use Case Name** | User Registration (Sign up) |
| **Primary Actors** | New users (student, faculty, employee) |
| **Description** | A new user creates an account on the system so that they can log in and place food orders from HUTS. |
| **Preconditions** | • The user does not already have an account in the system.<br>• The user has a valid QAU email address or a registered phone number.<br>• The application or website is accessible through the internet connection. |
| **Main Flow** | 1. The user opens the application or website and selects the Register option(sign up).<br>2. The user enters their full name, QAU email address or phone number, department name, and a password.<br>3. The system sends a one-time verification OTP code to the provided email or message on phone number or message on whatsapp.<br>4. The user enters the OTP within five minutes of receiving it.<br>5. The system verify the OTP and creates the account.<br>6. The system displays a success confirmation message and allow the user to the login page. |
| **Postconditions** | • A new verified user account is saved in the system database.<br>• The user can now log in and access all available features. |
| **Alternate Flow** | • **1(a)** If the email or phone number is already registered, the system displays the message: Account already exists. Please log in.<br>• **3(a)** If the OTP expires before the user enters it, the system offers an option to request a new OTP.<br>• **4(a)** If the user enters an incorrect OTP three times, the registration attempt is blocked for ten minutes. |

---

### Use case#2: 3.2 User Login

| Field | Details |
| :--- | :--- |
| **Use Case Name** | User Login |
| **Primary Actors** | Registered User (Student, Faculty, Admin or Delivery Staff) |
| **Description** | A user who already has a registered account logs into the system using their email or phone number and password to access their personal dashboard. |
| **Preconditions** | • The user has an existing and verified account in the system.<br>• The user knows their registered email or phone number and their password.<br>• The system is running and accessible. |
| **Main Flow** | 1. The user opens the application and selects the Login option.<br>2. The user enters their email or phone number and password.<br>3. The system check the credential against the stored database records.<br>4. If the credential are correct, the system logs the user in and redirects them to their home dashboard.<br>5. The system displays a welcome message with the user name. |
| **Postconditions** | • The user is successfully logged in and a session is created.<br>• The user has access to all features according to their role. |
| **Alternate Flow** | • **2(a)** If the password enter is wrong, the system shows incorrect password. Please try again.<br>• **4(a)** After five consecutive failed attempt, the account is temporarily locked for fifteen minutes.<br>• **5(a)** The user may click Forgot Password to reset it via an OTP sent to their registered email or phone. |

---

### Use case #3: 3.3 Search Food Menu

| Field | Details |
| :--- | :--- |
| **Use Case Name** | Browse Food Menu |
| **Primary Actors** | Logged-in Student or Faculty Member |
| **Description** | The user views the huts food menu to explore available food categories, individual items and prices before decide what to order. |
| **Preconditions** | • The user is logged in to the system.<br>• The hut admin has added menu items to the system.<br>• The internet connection is active. |
| **Main Flow** | 1) The user navigates to the menu section from the main dashboard.<br>2) The system loads and displays all food categories such as breakfast, lunch, dinner, shakes, and fast food.<br>3) The user selects a category to see the items available under it.<br>4) Each item is displayed with its name, price and a photograph.<br>5) The user may use the search bar to look for a specific item by name.<br>6) The user may apply filters by category, price range, or availability. |
| **Postconditions** | • The user has viewed the available menu items and can proceed to place an order.<br>• No changes are made to the system database during this process. |
| **Alternate Flow** | • **3(a)** If a menu item is out of stock, it is displayed in a greyed-out state with the label Not Available.<br>• **5(a)** If the menu fails to load due to a network error, the system shows unable to load menu. Please check your internet connection and try again. |

---

### Use case #4: 3.4 Place Food Order

| Field | Details |
| :--- | :--- |
| **Use Case Name** | Place Food Order |
| **Primary Actors** | Logged-in Student or Faculty Member |
| **Description** | The user selects one or more food items from the menu, adds them to a cart, chooses between delievery to their department or pickup at huts, and confirms the order with payment. |
| **Preconditions** | • The user is logged in.<br>• At least one menu item is currently marked as available.<br>• The user has reviewed their cart and is ready to place the order. |
| **Main Flow** | 1. The user searches the menu and clicks add to cart on the items they want to buy.<br>2. The user navigates to the cart section and reviews the list of selected items and the total price.<br>3. The user select a delivery option deliever to My Department or Pick Up at huts.<br>4. If delivery is selected, the user confirms or enters their department name and building location.<br>5. The user proceeds to the payment screen and selects a payment method such as Easypaisa, JazzCash, bank app, or Cash on Delivery.<br>6. The user reviews the final order receipt and clicks confirm order.<br>7. The system process the payment, generates a unique order ID, and displays a confirmation screen message with the estimated preparation time. |
| **Postconditions** | • The order is saved in the database with the status order received.<br>• The hut admin receives a notification of the new incoming order.<br>• The user receives a confirmation notification with the order ID. |
| **Alternate Flow** | • **5(a)** If the payment transaction fails, the system notifies the user and offers the option to retry or select a different payment method.<br>• **6(a)** If an item becomes unavailable after being added to the cart, the user is notified before checkout and asked to remove or replace it.<br>• **7(a)** If the entered delivery location is outside the campus boundary, the system shows an error and asks the user to correct it. |

---

### Use case #5: 3.5 Track Order Status

| Field | Details |
| :--- | :--- |
| **Use Case Name** | Track Order Status |
| **Primary Actors** | Logged-in Student or Faculty Member |
| **Description** | After placing an order, the user monitors its current status in real time to know when the food will be ready or delivered. |
| **Preconditions** | • The user is logged in.<br>• The user has placed at least one order that is currently active.<br>• The hut admin or delivery staff is updating the order status. |
| **Main Flow** | 1. The user navigates to the My order section.<br>2. The system displays a list of recent orders along with their current status.<br>3. The user taps on a specific order to view its details.<br>4. The system shows a step-by-step progress with the following stages: order Received, being Prepared, ready for Pickup or out for Delivery and delivered.<br>5. The status updates automatically as the hut admin or delivery staff advances it through the stages.<br>6. The user receives a push notification each time the status changes. |
| **Postconditions** | • The user is kept informed about the progress of their order.<br>• No changes are made to the order data in the database. |
| **Alternate Flow** | • **3(a)** If a delay occurs, the system shows an updated estimated delivery time.<br>• **6(a)** If the order is cancelled, the status displays as order cancelled with the reason for cancellation. |

---

### Use case #6: 3.6 Cancel Order

| Field | Details |
| :--- | :--- |
| **Use Case Name** | Cancel Order |
| **Primary Actors** | Logged-in Student or Faculty Member |
| **Description** | The user cancels an order that has been placed but has not yet started being prepared by the kitchen. |
| **Preconditions** | • The user is logged in.<br>• The order status is still order received, meaning preparation has not yet begun.<br>• The cancellation request is made within three minutes of placing the order. |
| **Main Flow** | 1. The user goes to the My Orders section.<br>2. The user selects the order they wish to cancel.<br>3. The user clicks the cancel order button.<br>4. The system asks for confirmation that are you sure you want to cancel this order?<br>5. The user confirms the cancellation.<br>6. The system changes the order status to cancelled and initiates a refund if the payment was made online.<br>7. Both the user and the hut admin receive a cancellation notification. |
| **Postconditions** | • The order is marked as cancelled in the database.<br>• If an online payment was made, the refund process is started automatically.<br>• The hut admin is notified so the order is not prepared. |
| **Alternate Flow** | • **4(a)** If the order has already moved to the being prepared status, the cancel order button is disabled and the system displays that your order is already being prepared and cannot be cancelled.<br>• **6(a)** If the automatic refund process encounters an error, the system flags the order for manual review by the system admin. |

---

### Use case #7: 3.7 Admin Manages Food Menu

| Field | Details |
| :--- | :--- |
| **Use Case Name** | Admin Manages Food Menu |
| **Primary Actor** | Huts Admin |
| **Description** | The huts administrator adds new food items to the menu, updates existing items, or removes items that are no longer available. |
| **Preconditions** | • The admin is logged in with administrator credentials.<br>• The admin has access to the admin dashboard. |
| **Main Flow** | 1. The admin navigates to the menu management section of the admin dashboard.<br>2. To add a new item, the admin clicks add new Item, then fills in the item name, category, price, description, and uploads a photo.<br>3. The admin marks the item as available or Not available.<br>4. The admin clicks save and the item is immediately visible to customers in the menu.<br>5. To update an existing item, the admin selects the item, edits the relevant details, and saves the changes.<br>6. To delete an item, the admin selects the item and clicks Delete, then confirms the action in the confirmation dialog. |
| **Postconditions** | • The menu in the database is updated quickly.<br>• Customers see the updated menu the next time they search it. |
| **Alternate Flow** | • **2(a)** If the photo upload fails, the system asks the admin to try uploading again.<br>• **3(a)** If a required field such as price or name is left empty, the system highlights the missing field and prevents saving |

---

### Use case #8: 3.8 Admin Processes Incoming Order

| Field | Details |
| :--- | :--- |
| **Use Case Name** | Admin Processes Incoming Order |
| **Primary Actors** | Huts Admin |
| **Description** | The admin receives a notification of a new order, reviews its contents, accepts it, and advances the order status as it is prepared. |
| **Preconditions** | • The admin is logged in to the Admin Dashboard.<br>• At least one new order has been submitted by a customer.<br>• Kitchen staff are available to begin preparation. |
| **Main Flow** | 1. The admin receives a push notification of a new incoming order.<br>2. The admin opens the order in the Orders section of the dashboard.<br>3. The admin reviews the list of items and any delivery instructions.<br>4. The admin clicks accept order and the status is updated to being prepared.<br>5. When the food is ready, the admin clicks mark as ready.<br>6. For delivery orders, the admin selects and assigns the order to an available delivery staff member.<br>7. The system updates the order status and sends a notification to the customer. |
| **Postconditions** | • The order status progresses step by step and is seen in the customer facing tracking screen.<br>• The assigned delivery staff member receives a notification with the delivery details.<br>• The customer is notified at each stage. |
| **Alternate Flow** | • **7(a)** If an ordered item is found to be out of stock after the order is received, the admin contacts the customer through the app messaging feature to offer a replacement item or to initiate a cancellation. |

---

### Use case #9: 3.9 Submit Feedback and Rating

| Field | Details |
| :--- | :--- |
| **Use Case Name** | Submit Feedback and Rating |
| **Primary Actors** | Logged in Student or Faculty Member |
| **Description** | After receiving their order, the user rates the food quality and the delivery service and optionally leaves a written comment. |
| **Preconditions** | • The user is logged in.<br>• The order has been delivered and its status has been updated to delievered.<br>• The user has not already submitted feedback for this specific order. |
| **Main Flow** | 1. After an order is marked as delivered, the system sends a notification that how was your order? Tap to rate.<br>2. The user opens the notification or search to the order in my orders.<br>3. The user selects a star rating from one to five stars.<br>4. The user optionally writes a short comment about the food or service.<br>5. The user taps Submit Feedback.<br>6. The system saves the feedback and displays a thank you message. |
| **Postconditions** | • The feedback is saved in the database and linked to the specific order.<br>• The average rating for the relevant food items is updated.<br>• The hut admin can view all feedback from the admin dashboard. |
| **Alternate Flow** | • **5(a)** If the user dismisses the initial notification, they can still submit feedback from the my orders section within 24 hours of delivery. |