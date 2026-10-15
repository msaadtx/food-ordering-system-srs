### 1.9 Definitions , Acronyms , and Abbreviations

The followingg terms and abbreviations are used throughout this document .

| Term | Definition |
| :--- | :--- |
| SRS | Software Requirements Specification. |
| QAU | Quaid- I -Azam University, Islamabad. |
| Hut | A campus food outlet at QAU . The system serves multiple huts located across the campus . |
| IEEE | Institute of Electrical and Electronics Engineers . |
| ISO / IEC | International Organization for Standardization / International Electrotechnical Commission . |
| UI | User Interface: The screens and controls a user interacts with . |
| OTP | One -Time Password: a short code sent to verify identity during registration , login , or password reset . |
| FR | Functional Requirement: a feature or action system must perform. |
| NFR | Non-Functional Requirement: a quality the system must have , such as speed , security , or usability . |
| API | Application Programming Interface: a way for software components (e.g., payment gateways Maps etc) to communicate. |
| HTTPS | Hypertext Transfer Protocol Secure: encrypted communication between the user's device and the server. |
| COD | Cash on Delivery: payment made in cash when the order is handed over . |
| DFD | Data Flow Diagram: a diagram showing how data moves through the system . |
| UML | Unified Modeling Language: The notation used for use case , class , activity , and sequence diagrams . |
| Actor | Any person or external system that interacts with the system . |
| Use Case | A description of how an actor completes a specific task using the system . |
| Customer | A student , faculty member, or university employee who orders food through the system. |
| Hut Admin | Hut staff member who manages the menu, processes incoming orders, and assigns delivery staff. |
| Delivery Staff | Hut employee who delivers orders within the campus and updates delivery status . |
| System Admin | Technical user who manages user accounts , system settings, security, and flagged refund cases. |

### 1.10 References

ISO / IEC / IEEE 29148: 2018, Systems and software engineering: Life cycle processes: Requirements engineering, 2018.

IEEE Std 830-1998 , Recommended Practice for Software Requirements Specifications , IEEE Computer Society , 1998 (superseded by ISO / IEC/IEEE 29148).

Quaid-i-Azam University official website: www.qau.edu.pk

Field observations and informal student feedback collected at QAU huts, Islamabad, 2026.

Firebase Cloud Messaging documentation , for push notifications .

Easypaisa and JazzCash developer documentation , for online payment integration.

### 1.11 Project Overview

The Online Food Ordering System for QAU Huts is a web and mobile application that allows students ; faculty members, and university employees to browse hut menus , place food orders , pay online or in cash, and track their orders without visiting the hut in person .

The system addresses the main problems of the current manual process:  
long queues, limited seating , harsh weather in Islamabad , long distances between some departments and the huts , and the lack of order tracking and digital records . Customers can choose delivery to their department or pickup at the hut . Delivery is limited to the QAU campus.

The system has four user classes:

**Customers (students, faculty, employees):**  
search the menu, place and pay for orders , track status , cancel eligible orders and give feedback.

**Hut Admins:**  
manage the menu , accept and process incoming orders , and assign delivery staff.

**Delivery Staff:**  
deliver orders on campus and update the delivery status .

**System Admin:**  
manages user accounts , settings , and the overall security and health of the platform .