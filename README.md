# S2.03 – MongoDB Structure (Level 1 & Level 2)

## 📄 Description
This project contains the solution for **S2.03 – MongoDB Structure**, focusing on the design and implementation of **NoSQL databases** using **MongoDB**.  
It includes two complete case studies:
- 🕶️ **Level 1:** Optical Store ("Cul d’Ampolla")  
- 🍕 **Level 2:** Pizzeria Online Ordering System  

Both levels demonstrate how to model, structure, and relate collections in a non-relational environment.

---

## 🕶️ Level 1 – Optical Store (“Cul d’Ampolla”)

### 🧩 Objective
Model a MongoDB database for an optical store that sells glasses and manages customers, employees, suppliers, and sales.

### 🧠 Main Requirements
- **Suppliers:** store supplier information such as name, full address, phone, fax, and tax ID (NIF).  
- **Glasses:** store details including brand, lens graduations (left/right), frame type (floating, plastic, metallic), frame and lens colors, and price.  
- **Customers:** store name, address, contact details, registration date, and optionally who referred them.  
- **Employees:** store name, contact details, and hire date.  
- **Sales:** store customer, employee, date/time, sold glasses, and price.

### 🔗 Relationships
- **Suppliers → (1:N) → Glasses**  
- **Customers → (1:N) → Sales**  
- **Employees → (1:N) → Sales**  
- **Glasses → (N:1) → Suppliers**

### 💡 Design Summary
Each sale record references the customer, employee, and glass sold. The relationship between **sales** and **glasses** is handled via reference fields and embedded subdocuments, allowing quick access to purchase details.

The database facilitates two key perspectives:
1. **Customer View:** all details of a customer and their purchases.  
2. **Glasses View:** all details of each glass model, its supplier, and the customers who purchased it.


---

## 🍕 Level 2 – Pizzeria Database

### 🧩 Objective
Design a MongoDB database for an online food ordering system that manages **customers**, **orders**, **products**, **stores**, and **employees**.

### 🧠 Main Requirements
- **Customers:** name, surname, address, postal code, city, province, and phone number.  
- **Orders:** linked to one customer and one store, can include multiple products (quantity + unit price), may be for delivery or pickup, and include optional notes.  
- **Products:** divided into categories (pizzas, burgers, drinks) with description, image, and price.  
- **Stores:** handle multiple orders, each including address and location details.  
- **Employees:** work in a single store and can be **cooks** or **delivery drivers**.  
- For **delivery orders**, the database stores the assigned delivery employee and the delivery date/time.

### 🔗 Relationships
- **Customers → (1:N) → Orders**  
- **Stores → (1:N) → Orders**  
- **Orders → (N:M) → Products** (handled through embedded `details[]`)  
- **Stores → (1:N) → Employees**

### 💡 Design Summary
Each order includes embedded product details (quantity and price), referencing product IDs.  
Delivery orders also embed a subdocument with the delivery date and the responsible employee.


---

## 💻 Tools Used
- **MongoDB 6.0**
- **Docker & Docker Compose**  
- **JSON** (for data modeling and structure)  
- **Moon Modeler** (for conceptual diagrams)  
- **Git & GitHub** (for version control and submission)

---

## 🎯 Learning Outcomes
Through this project, the following skills were developed:
- Understanding of **NoSQL modeling principles**.  
- Implementation of **document-based relationships** in MongoDB.  
- Creation of **embedded and referenced structures** for complex data.  
- Design of **conceptual and logical diagrams** for real-world scenarios.

---

## ✍️ Author
**Christopher Alves.**  
📁 [GitHub Repository](https://github.com/christo256/S2.03---Estructura-de-dades---MongoDB)


