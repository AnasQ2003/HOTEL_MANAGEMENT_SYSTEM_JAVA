# 🏨 Hotel Management System — Java

<div align="center">

![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white)
![Swing](https://img.shields.io/badge/Swing-GUI-blue?style=for-the-badge)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![NetBeans](https://img.shields.io/badge/NetBeans-IDE-1B6AC6?style=for-the-badge&logo=apache-netbeans-ide&logoColor=white)
![OOP](https://img.shields.io/badge/OOP-Project-success?style=for-the-badge)

A fully featured **desktop Hotel Management System** built with **Java Swing** and **MySQL**, developed as a Object-Oriented Programming (OOP) project. The system supports dual-role access (Admin & Customer), real-time room booking, food ordering, payment processing, and full CRUD operations — all through a polished, interactive GUI.

</div>

---

## 📸 Screenshots

<table>
  <tr>
    <td align="center"><img src="screenshots/home.jpg" width="300"/><br/><b>Home Screen</b></td>
    <td align="center"><img src="screenshots/login.jpg" width="300"/><br/><b>Login</b></td>
    <td align="center"><img src="screenshots/sign up.jpg" width="300"/><br/><b>Sign Up</b></td>
  </tr>
  <tr>
    <td align="center"><img src="screenshots/forgot password.jpg" width="300"/><br/><b>Forgot Password</b></td>
    <td align="center"><img src="screenshots/admin home.png" width="300"/><br/><b>Admin Dashboard</b></td>
    <td align="center"><img src="screenshots/manage room.jpg" width="300"/><br/><b>Manage Rooms</b></td>
  </tr>
  <tr>
    <td align="center"><img src="screenshots/customer registration and check in.png" width="300"/><br/><b>Customer Check-In</b></td>
    <td align="center"><img src="screenshots/customer check out.png" width="300"/><br/><b>Customer Check-Out</b></td>
    <td align="center"><img src="screenshots/customer detail bill.png" width="300"/><br/><b>Detailed Bill</b></td>
  </tr>
  <tr>
    <td align="center"><img src="screenshots/log out.png" width="300"/><br/><b>Logout</b></td>
  </tr>
</table>

---

## ✨ Features

### 👤 Customer Role
- **Registration & Login** — Secure sign-up and authentication with password recovery
- **Room Browsing** — View available rooms with type, capacity, and pricing
- **Room Booking** — Book rooms with check-in and check-out date selection
- **Food Ordering** — Order food items from the in-house menu during stay
- **Bill Viewing** — View an itemized breakdown of room charges and extra orders
- **Check-Out** — Complete checkout with full bill settlement

### 🔑 Admin Role
- **Admin Dashboard** — Full control panel to manage all hotel operations
- **Room Management** — Add, update, or remove room listings and availability
- **Customer Management** — View all registered customers and their booking status
- **Order Management** — Track and manage food and extra service orders
- **Payment Management** — Oversee payments and billing records
- **Food & Item Catalog** — Manage the food menu and available hotel items

---

## 🏗️ Architecture & Project Structure

The project follows a clean **3-tier layered architecture** using core OOP principles:

```
Hotel-Management-System-Java/
│
├── 📦 Model (Entity Classes)
│   ├── Booking.java          — Room booking entity
│   ├── Room.java             — Room details & availability
│   ├── RoomFare.java         — Room pricing model
│   ├── UserInfo.java         — Customer/user profile
│   ├── Food.java             — Food item entity
│   ├── Item.java             — Hotel service item
│   ├── Order.java            — Order entity
│   ├── ExtraOrders.java      — Extra services ordered
│   └── Payment.java          — Payment record entity
│
├── 📦 Database (DAO / DB Layer)
│   ├── DataBaseConnection.java   — MySQL JDBC connection setup
│   ├── DatabaseOperation.java    — Generic DB operations
│   ├── BookingDb.java            — Booking CRUD operations
│   ├── CustomerDb.java           — Customer CRUD operations
│   ├── RoomDb.java               — Room CRUD operations
│   ├── FoodDb.java               — Food catalog operations
│   ├── ItemDb.java               — Item management operations
│   └── OrderDb.java              — Order CRUD operations
│
├── 📦 UI (Swing Panels / Frames)
│   ├── ControlPanel.java         — Main admin control panel
│   ├── CustomerPanel.java        — Customer management view
│   ├── RoomPanel.java            — Room listing & management
│   ├── FoodPanel.java            — Food catalog panel
│   ├── ItemPanel.java            — Items panel
│   ├── OrderPanel.java           — Order management view
│   ├── PaymentPanel.java         — Payment processing view
│   ├── BookingTableModel.java    — Custom JTable model for bookings
│   └── CustomCellRenderer.java   — Custom table cell rendering
│
└── 📦 Entry Point
    └── testing.java              — Main class (application entry point)
```

---

## 🧠 OOP Concepts Applied

| Concept | Application |
|---|---|
| **Encapsulation** | All entity fields are `private` with public getters/setters |
| **Inheritance** | Panel classes extend `JPanel`; DB classes share base operations |
| **Polymorphism** | Overridden methods for DB operations across different entity types |
| **Abstraction** | Database layer abstracts all raw SQL away from the UI layer |
| **MVC Pattern** | Models (`*.java`), Views (Panels), Controllers (DB + logic classes) |
| **DAO Pattern** | Separate `*Db.java` classes for each entity's database operations |
| **JDBC** | `DataBaseConnection.java` manages MySQL connectivity via JDBC |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Language** | Java (JDK 8+) |
| **GUI Framework** | Java Swing |
| **IDE** | Apache NetBeans |
| **Database** | MySQL |
| **Connectivity** | JDBC (MySQL Connector/J) |
| **Build** | NetBeans Project (`.form` + `.java`) |

---

## 🚀 Getting Started

### Prerequisites

- Java JDK 8 or higher
- Apache NetBeans IDE (recommended) or any Java IDE
- MySQL Server (running locally)
- MySQL Connector/J (JDBC driver)

### 1. Clone the Repository

```bash
git clone https://github.com/AnasQ2003/HOTEL_MANAGEMENT_SYSTEM_JAVA.git
cd HOTEL_MANAGEMENT_SYSTEM_JAVA
```

### 2. Set Up the Database

Open MySQL Workbench or your preferred MySQL client and create the database:

```sql
CREATE DATABASE hotel_management;
USE hotel_management;
```

Then import the provided SQL schema (if available in `oop.zip`) or manually create tables as defined in the `*Db.java` files.

### 3. Configure the Database Connection

Open `DataBaseConnection.java` and update your credentials:

```java
String url = "jdbc:mysql://localhost:3306/hotel_management";
String username = "root";
String password = "your_password";
```

### 4. Add JDBC Driver

Download the [MySQL Connector/J](https://dev.mysql.com/downloads/connector/j/) and add the `.jar` to your project's classpath in NetBeans.

### 5. Build & Run

- Open the project in **Apache NetBeans**
- Right-click the project → **Clean and Build**
- Run `testing.java` as the main entry point

---

## 📚 Course Context

| Detail | Info |
|---|---|
| **Course** | Object-Oriented Programming (OOP) |
| **Semester** | 2nd Semester |
| **Lab Project** | Hotel Management System |
| **Key Concepts** | Encapsulation, Inheritance, Polymorphism, Abstraction, JDBC, MVC |

---

## 📄 License

```
MIT License

Copyright (c) Hotel Management System Java ---2026 AnasQ2003

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

---

## 👨‍💻 Author

**Anas Ahmed Qureshi.** — [@AnasQ2003](https://github.com/AnasQ2003)

---

<div align="center">
  <p>Built with ❤️ by <strong>Anas</strong></p>
  
 <div align="center">

Made with 🔥 and a lot of ☕

**⭐ If you found this useful, please star the repository!**

</div>
