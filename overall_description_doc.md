# 2. Overall Description

## 2.1 Product Perspective
The Online Food ordering system for university Huts will be a web-based and mobile-based application that operates within the university network environment. The system will act as a centralized platform connecting students, hut vendors, and delivery personnel. The system is designed as a replacement for the traditional manual food ordering process where students must physically visit huts and place orders in person. By making digital system process, the system reduce physical interaction and improves efficiency. The application will be accessible through:

- Web browsers for laptops or desktops
- Mobile devices Android/iOS apps or responsive web interface)

The system will interact with multiple components:

- **User Interface (UI):** For students and staff to interact with the system
- **Backend Server:** To process orders, manage data, and handle business logic
- **Database:** To store user data, menu items, orders, and transaction records

It will integrate with:

- University authentication system (optional)
- Payment gateways (if online payment is implemented)

Overall the system acts as a bridge between customers such as students and other users and service providers (huts), ensuring smooth communication, faster service, and improved accessibility.

## 2.2 Product Functions
The system will provide these main functions given below:

- User registration and authentication
- Viewing the menu organized by category with prices and photos
- System support searching and filtering menu items
- Adding items to a shopping cart and placing food orders
- Online payment through these apps like Easypaise, Jazzcash, any bank app or cash
- Real-time order tracking from placement through delivery
- Order cancellation with automatic refund when applicable
- Huts admin tools for managing the menu and process incoming orders
- Delivery staff assignment and tracking
- Post-delivery feedback and star ratings

## 2.3 User Classes and Characteristics
The system is designed for four types of users, each with different roles and levels of technical experience.

- **Students, Employee and Staff** are the primary users of this system. They have a basic to moderate level of technical experience with smartphones and web applications. They will use the system to search the menu, place orders, make payments, track orders, and submit feedback after delivery.
- **Huts Admin** is a member of the Huts management team with moderate technical experience. The admin is responsible for managing the menu adding, updating, and removing items, reviewing and accepting incoming orders, updating order status, and assigning delivery staff.
- **Delivery Staff** are Huts employees assigned to carry food to different Hostels and departments on campus. They have basic technical experience. Their role in the system is to deliver items and updating the delivery status once an order is handed to the customer.
- **The System Administrator** is a technically advanced user responsible for managing all system settings, user accounts, and ensuring the overall health and security of the platform.

## 2.4 Operating Environment
The system will operate as a web application accessible from any browser including Google Chrome, Mozilla Firefox and Safari and as well as for mobile application for android version and iOS version. The backend server will be hosted on a cloud or on university managed server. All data will be stored in a secured relational database. An active internet connection (WiFi or mobile data) is required to use the system. The system is designed to function acceptably even on the relatively slow internet connections common across the QAU campus.

## 2.5 Design and Implementation Constraints
- The system must remain functional on slow or unstable campus internet connections.
- Payment is restricted to Pakistani platforms such as Easypaisa, JazzCash, and domestic debit or credit cards
- Delivery is available only within the boundaries of the QAU Islamabad campus.
- The system must support the Urdu language as an optional display setting for accessibility.
- The first version of the system must be completed within the current 4th semester academic timeline.

---

# 3. Specification requirements and Use Cases
This section describes all major features of the system in the form of use cases. Each use case follows a standard format that includes the actors involved, description of these features, which are the preconditions that must be satisfied before the use case begins, the step-by-step flow of the interaction, the postconditions that are true after the use case completes successfully, and the alternate flows that handle exceptions and error conditions.