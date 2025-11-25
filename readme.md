⸻

BankBridge – Offline Banking Management System

A Java Swing + SQLite Banking Application using OOP, JDBC, Collections, Multithreading & DAO Architecture

⸻

📌 Overview

BankBridge is an offline banking management desktop application built using Java, featuring a modern Swing GUI, secure SQLite database, proper layered architecture, and robust OOP implementation.

It is designed for academic evaluation and real-world demonstration of key programming concepts:
	•	Object-Oriented Programming (Inheritance, Polymorphism, Abstraction, Interfaces)
	•	Collections & Generics
	•	JDBC Integration (PreparedStatement, ResultSet, Transactions)
	•	Multithreading & Synchronization
	•	Clean Code + Modular Architecture

The system enables secure account creation, deposits, withdrawals, transaction safety, and background auditing — even when offline.

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

This architecture separates duties cleanly into GUI, Model, DB, DAO, Exceptions, Threads, and Database, following the industry-standard Layered + DAO pattern.

⸻

🎯 Features

✅ Offline Banking System

Works entirely without internet using SQLite.

✅ Modern GUI (Java Swing)

Includes:
	•	Login Page
	•	Dashboard
	•	Create Account Page
	•	Transaction Page
	•	Admin Panel
	•	Table Views for Accounts & Transactions

✅ OOP-Driven System

Implements:
	•	Abstraction (Account, Transaction)
	•	Inheritance (SavingsAccount, CurrentAccount)
	•	Polymorphism (applyInterest() behavior differs)
	•	Encapsulation (secure private fields)
	•	Interfaces (Repository<T>)
	•	Constructor Overloading
	•	Method Overriding
	•	Use of super and this

✅ JDBC + SQLite Integration
	•	Secure connection handling
	•	PreparedStatement for SQL safety
	•	ResultSet processing
	•	Transactions with commit/rollback
	•	Exception-safe database operations

✅ DAO Architecture

Encapsulates database operations inside:
	•	AccountDAO
	•	DBConnection
	•	Repository<T>

✅ Multithreading & Synchronization
	•	TransactionEngine performs transactions in parallel
	•	AuditThread logs activities in background
	•	synchronized keyword prevents race conditions

⸻

🧠 OOP Concepts Implemented

1. Inheritance

SavingsAccount and CurrentAccount extend the abstract Account.

2. Polymorphism

Different accounts override applyInterest() uniquely.

3. Abstraction

Account and Transaction define behavior templates for subclasses.

4. Interfaces

Repository<T> defines database CRUD contract.

5. Encapsulation

Private fields with getters/setters protect sensitive state.

6. Exception Handling

Custom exceptions:
	•	InsufficientFundsException
	•	InvalidAccountException
	•	DatabaseConnectionException

7. Constructor Overloading

Multiple constructors for models and transactions.

⸻

🔧 Database Schema (SQLite)

Users Table

Column	Type	Description
user_id	INTEGER	Primary Key
username	TEXT	User login name
password	TEXT	Hashed password

Accounts Table

Column	Type	Description
account_id	INTEGER	Primary Key
user_id	INTEGER	Foreign Key
type	TEXT	Account type
balance	REAL	Current balance

Transactions Table

Column	Type	Description
transaction_id	INTEGER	Primary Key
account_id	INTEGER	Foreign Key
type	TEXT	Deposit / Withdraw / Transfer
amount	REAL	Amount
timestamp	DATETIME	Auto time


⸻

🚀 How to Run the Project

1. Prerequisites
	•	Java JDK 8+
	•	SQLite JDBC Driver
	•	Any IDE (IntelliJ recommended)

⸻

2. Setup the Database

Place the file:

database/bank.db

Run the SQL schema if needed.

⸻

3. Run the Project

Run in IDE
	•	Open project folder
	•	Run Main.java

Run in Terminal
Compile:

javac -cp ".:sqlite-jdbc.jar" $(find src -name "*.java") -d out

Run:

java -cp "out:sqlite-jdbc.jar" Main


⸻

🌍 Real-World Applications
	•	Offline banking in rural regions
	•	Co-operative banks
	•	Educational finance labs
	•	Research usage for concurrency & DB design
	•	Financial kiosks
	•	Lightweight banking client for SMEs

⸻

🔮 Future Scope
	•	Web version using Servlets / Spring Boot
	•	Mobile app integration
	•	Biometric / OTP login security
	•	Export statements as PDF
	•	Admin dashboard with analytics
	•	AI-powered fraud detection

⸻

👤 Authors

Shreyansh Misra
Shivam Singh

B.Tech CSE
Galgotias University

⸻

📜 License

This project is free for academic and educational use.

⸻