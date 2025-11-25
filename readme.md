BankBridge – Offline Banking Management System

A Java Swing + SQLite Banking Application using OOP, JDBC, Collections, Multithreading & DAO Architecture

⸻

📌 Overview

BankBridge is an offline-capable banking management system built using Java, featuring a clean Swing GUI, SQLite database, properly layered design, and complete implementation of OOP, JDBC, Collections, Multithreading, and DAO architecture.

It is designed for both academic evaluation and real-world demonstration, showcasing:
	•	Object-Oriented Programming & Clean Architecture
	•	Robust JDBC Integration
	•	Multi-threaded Transaction Handling
	•	Secure Data Storage using SQLite
	•	Enterprise-style GUI Application Structure

This application enables account creation, deposits, withdrawals, transaction logging, admin operations, and background auditing — all while functioning fully offline.

⸻

🏗 Project Architecture

BankBridge/
│
├── src/
│   ├── Main.java
│   ├── gui/
│   │   ├── LoginFrame.java
│   │   ├── Dashboard.java
│   │   ├── CreateAccountForm.java
│   │   ├── TransactionForm.java
│   │   └── AdminPanel.java
│   ├── model/
│   │   ├── BankEntity.java
│   │   ├── Account.java (abstract)
│   │   ├── SavingsAccount.java
│   │   ├── CurrentAccount.java
│   │   ├── Transaction.java (abstract)
│   │   ├── Deposit.java
│   │   ├── Withdraw.java
│   │   └── Transfer.java
│   ├── db/
│   │   ├── DBConnection.java
│   │   ├── Repository.java (Generic Interface)
│   │   └── AccountDAO.java
│   ├── exceptions/
│   │   ├── InsufficientFundsException.java
│   │   ├── InvalidAccountException.java
│   │   └── DatabaseConnectionException.java
│   └── threads/
│       ├── TransactionEngine.java (implements Runnable)
│       └── AuditThread.java (extends Thread)
│
└── database/
    └── bank.db (SQLite)

This layered structure ensures high maintainability, separation of concerns, and scalable code evolution.

⸻

🎯 Features

✔ Fully Offline Banking System

Powered by SQLite (embedded database).

✔ Modern, Responsive GUI

Using Java Swing:
	•	Login
	•	Create Account
	•	Dashboard
	•	Deposit/Withdraw
	•	Admin Panel
	•	Account & transactions table views

✔ Strong OOP Implementation

Covers:
	•	Inheritance
	•	Polymorphism
	•	Abstraction
	•	Interfaces
	•	Method Overloading
	•	Method Overriding
	•	Constructor Chaining
	•	Encapsulation

✔ JDBC-Based DB Layer
	•	Database operations via DAO
	•	PreparedStatement for security
	•	ResultSet for query handling
	•	Commit/Rollback for consistency

✔ Multithreading
	•	Transaction Engine (Runnable)
	•	Background Audit Thread
	•	Thread synchronization for safe balance updates

⸻

🧠 OOP Concepts Implemented

Concept	How It Is Implemented
Abstraction	Account and Transaction abstract classes
Inheritance	SavingsAccount & CurrentAccount extend Account
Polymorphism	applyInterest() behaves differently per account
Interfaces	Repository<T> interface for DAO
Encapsulation	Private fields + getters/setters everywhere
Exception Handling	Custom exceptions + try/catch in DAO
Method Overriding	Deposit/Withdraw logic overrides base
Constructor Overloading	Multiple constructors in model classes


⸻

🛢 Database Schema (SQLite)

users

Column	Type	Description
user_id	INTEGER	Primary Key
username	TEXT	User login
password	TEXT	Encrypted password

accounts

Column	Type	Description
account_id	INTEGER	Primary Key
user_id	INTEGER	Foreign Key
type	TEXT	Savings / Current
balance	REAL	Money

transactions

Column	Type	Description
transaction_id	INTEGER	Primary Key
account_id	INTEGER	Foreign Key
type	TEXT	Deposit / Withdraw / Transfer
amount	REAL	Value
timestamp	DATETIME	Auto-stamp


⸻

🔧 JDBC Implementation

This project uses:
	•	DriverManager to connect SQLite
	•	PreparedStatement to securely execute SQL
	•	ResultSet to retrieve data
	•	Manual Transaction Handling using:

conn.setAutoCommit(false);
conn.commit();
conn.rollback();



DAO Layer ensures all business logic stays modular and reusable.

⸻

🖥 HOW TO RUN THE PROJECT (FULL SETUP GUIDE)

This section teaches beginners and advanced users exactly how to run BankBridge on any PC.

⸻

✅ 1. Prerequisites

Make sure you have:

Tool	Required
Java JDK	8 or above
IDE	IntelliJ / Eclipse / VS Code
SQLite DB Browser	optional (for viewing DB)
SQLite JDBC Driver	Required

Download SQLite JDBC driver (sqlite-jdbc-3.46.x.jar) from Maven repository.

⸻

✅ 2. Project Setup

Option A — Using IntelliJ IDEA (Recommended)
	1.	Open IntelliJ → Import Project → select your BankBridge folder
	2.	Mark src/ as Sources Root
	3.	Add SQLite JDBC driver:
	•	File → Project Structure → Modules → Dependencies → (+) Add JAR
	4.	Place bank.db inside the /database folder
	5.	Run Main.java

⸻

Option B — Running via Terminal (Manual)

Navigate into your project folder:

cd BankBridge

Compile all Java files:

javac -cp ".:sqlite-jdbc.jar" $(find src -name "*.java") -d out

Run:

java -cp "out:sqlite-jdbc.jar" Main


⸻

✅ 3. Database Setup

SQLite requires no installation.

Make sure:

database/bank.db

exists.
If missing, create a new empty DB:
	1.	Download DB Browser for SQLite
	2.	Create new database → Save as bank.db
	3.	Create tables using the included schema or automatically via DAO logic.

⸻

🌍 Real-World Applications
	•	Offline banking in rural regions
	•	Co-operative credit societies
	•	Training labs in universities
	•	Small finance solution for SMEs
	•	Standalone kiosk systems
	•	Banking research & teaching tool

⸻

🔮 Future Scope
	•	Spring Boot web upgrade
	•	Android / iOS client app
	•	PDF bank statements
	•	Advanced role-based authentication
	•	AES encryption for sensitive data
	•	Logging + Analytics Module

⸻

👤 Authors

Shreyansh Misra

Shivam

B.Tech CSE
Galgotias University

⸻

📜 License

Open-source for academic and educational usage.

⸻

