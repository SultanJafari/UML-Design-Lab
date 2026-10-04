# Food Delivery Platform — Design Justification & UML Models

This repository contains the comprehensive design justification, UML models (Class Diagram and Sequence Diagrams), and architectural decisions for a **Food Delivery Platform**.

---

## Project Team
* **Abdullah Anas Almuqbali**
* **Mohammed Abdulaziz Alzouman**
* **Sultan Yahya Jaafari**

---

## Project Overview
The project focuses on modeling the core functionalities of a food delivery system with an emphasis on simplicity, clear responsibilities, and robust relationships. 

### Core Classes (`Class Diagram`)
The system design revolves around five primary classes:
1. **User**: Represents the customer who uses the platform and creates orders.
2. **Restaurant**: Provides the menu and receives orders (an order is strictly associated with a single restaurant).
3. **MenuItem**: Represents items available in a restaurant's menu.
4. **Order**: Manages order items, status (`created`, `confirmed`, `prepared`, `delivered`), and calculates totals.
5. **OrderItem**: Represents a specific menu item within an order, tracking quantity and historical unit price.

---

## Sequence Diagrams
The project models three core interactions using Sequence Diagrams:
1. **Place an Order**: Customer initializes an order, adds items, calculates prices, and confirms the order.
2. **Add an Item to an Order**: Validates that the order is in `created` status and verifies that the menu item belongs to the same restaurant as the order.
3. **Remove an Item from an Order**: Allows item removal securely while the order is still in the initial `created` state.

---

## Key Design Decisions & Trade-offs
* **Separation of Concerns:** Each class has a distinct and clear responsibility, making the system easy to understand and maintain.
* **Avoiding Over-engineering:** Complex systems such as Online Payment, Driver GPS Tracking, or Notification microservices were intentionally excluded to focus strictly on the core scenario requirements.
* **Composition Relationship:** Used strongly between `Order` and `OrderItem` since order items cannot exist independently outside an order.
* **Future Scalability:** The modular design allows seamless extension (e.g., adding `Payment`, `Driver`, or `Location` classes) without altering the core architecture.

---

## Presentation Q&A Highlights
* **Why did you create `OrderItem`?** To store order-specific attributes like quantity and historical unit price safely without altering the original menu item.
* **Why does an Order belong to a single restaurant?** To enforce the business constraint preventing mixed-restaurant orders.

---

## Getting Started
You can view the interactive presentation interface by opening the provided `index.html` file in any modern web browser.
