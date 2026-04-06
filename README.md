# 🛍️ Instagram Thrift & Handmade Store – ER Diagram

## 📌 Overview

This project represents the **Entity-Relationship (ER) diagram** for a small Instagram-based business that sells **thrifted fashion items** and **handmade products**.

Initially, orders are managed through Instagram DMs and WhatsApp, but as the business grows, a structured database system is required to efficiently manage products, customers, orders, payments, and shipping.

---

## 🎯 Objective

The goal of this database design is to:

* Manage both **thrifted (unique)** and **handmade (multiple quantity)** products
* Track **inventory availability**
* Store **customer information**
* Handle **orders with multiple items**
* Maintain **payment and shipping status**

---

## 🧱 Entities Included

### 👤 Customer

Stores customer details such as name, email, phone, and address.

### 📦 Product

Represents general product information. Each product is categorized as either:

* `thrifted` (single unique item)
* `handmade` (multiple units available)

### 🎨 ProductVariant

Stores specific variations of a product such as:

* size
* color
* condition

This allows flexible handling of both unique and multi-variant products.

### 📊 Inventory

Tracks the available quantity for each product variant.

### 🧾 Order

Represents a customer’s order and includes order date, total amount, and status.

### 🧺 OrderItem

A junction table that connects orders and product variants.
It enables:

* multiple products in one order
* the same product appearing in multiple orders

### 💳 Payment

Stores payment-related details such as method, status, and payment date.

### 🚚 Shipping

Manages delivery details including address, shipping status, and tracking information.

---

## 🔗 Relationships

* One **Customer** can place multiple **Orders**
* One **Order** can contain multiple **OrderItems**
* One **Product** can have multiple **ProductVariants**
* One **ProductVariant** has one **Inventory record**
* One **Order** is associated with one **Payment** and one **Shipping record**

The **many-to-many relationship** between Orders and Products is resolved using the **OrderItem** table.

---

## 🧠 Design Decisions

* A single **Product** table is used instead of separate thrift and handmade tables to avoid redundancy and improve scalability.
* **ProductVariant** is introduced to handle attributes like size, color, and condition without duplicating product data.
* **Inventory** is separated to manage stock efficiently and support future scalability.
* Payment and shipping are modeled as separate entities for better modularity and clarity.

---

## 💡 Key Features

* Supports both **unique thrift items** and **multi-quantity handmade items**
* Maintains **normalized structure** to reduce redundancy
* Scalable design for future expansion
* Clear handling of **order lifecycle (placement → payment → shipping)**

---

## 📷 Diagram

The ER diagram is included in this repository as an image/PDF for easy reference.

---

## 🚀 Conclusion

This database design provides a clean and scalable solution for managing a growing Instagram-based store. It ensures proper handling of inventory, orders, and customer data while keeping the schema normalized and efficient.
