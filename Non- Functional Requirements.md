# Non-Functional Requirements

Non-functional requirements  describe the qualitiees the system must have beyond its  basic features : how it should perform , how secure it must be , and how easy it must be to use and maintain . Each requirement below is written so that it can be tested.

### Performance

NFR-01: Every page or screen must load within 3 seconds on a tiypical internet connection available on the QAU campus.

NFR-02: The system must support at least 500 simiultaneous users placing orders, with an average response time under 3 seconds.

### Availability and Reliability

NFR-03: The system must be available at least 99% of the time overall, and at least 99.9% of the time during operating hours (7:00 AM to 10:00 PM). Planned maintenance must be scheduled outside operating hours.

NFR-04: If a  payment is processed successfully but the order confirmation  fails because of a system error , the customer must be refunded autoimatically, without manual interveention.

### Security

NFR-05: User passwords must be stored only as salted hashes using a strong algorithm (e.g., bcrypt). Passwords must never be stored as plain text.

NFR-06: All data transmitted between the user's device and the server must be protected with HTTPS.

NFR-07: After five consecutive incorrect password attempts, the system must lock the account for fifteen minutes before allowing further attempts.

### Usability

NFR-08: At least 90% of first-time users in usability testing must be able to register, browse the menu, and place an order without training or assistance.

NFR-09: The interface must be available in English. Urdu must be available as an optional display setting. 

### Scalability and Maintainability

NFR-10: The architecture must allow the system to grow as the number of users and orders increases, without a redesign.

NFR-11: The source code must be clean, modular, and commented so that future students can update or fix it easily.