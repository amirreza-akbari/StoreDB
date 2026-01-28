# 🛒 StoreDB - Sample Store Database

![StoreDB Banner](https://img.icons8.com/fluency/96/shopping-cart.png)

**StoreDB** is a sample relational database project for a store, including customer management, products, orders, and payments.  
This project is perfect for learning SQL, practicing relational database design, and testing queries.

---

## 📌 Features

- Manage **Customers**
- Manage and categorize **Products** (**Categories**)
- Track **Orders** and **Order Details**
- Record and manage **Payments**
- Proper **foreign key relationships** between tables
- **Clean and scalable** database design

---

## 🗂 Database Schema

### Customers
| Column      | Type           | Notes            |
|------------|----------------|-----------------|
| CustomerID | INT IDENTITY PK| Primary key     |
| FirstName  | NVARCHAR(50)   |                 |
| LastName   | NVARCHAR(50)   |                 |
| Email      | NVARCHAR(100)  |                 |
| Phone      | NVARCHAR(20)   |                 |
| Address    | NVARCHAR(200)  |                 |

### Categories
| Column       | Type           | Notes        |
|-------------|----------------|-------------|
| CategoryID  | INT IDENTITY PK| Primary key |
| CategoryName| NVARCHAR(50)   |             |
| Description | NVARCHAR(200)  |             |

### Products
| Column       | Type           | Notes                      |
|-------------|----------------|---------------------------|
| ProductID   | INT IDENTITY PK| Primary key               |
| ProductName | NVARCHAR(100)  |                           |
| Price       | DECIMAL(10,2)  |                           |
| StockQuantity| INT           |                           |
| CategoryID  | INT            | Foreign key → Categories |

### Orders
| Column      | Type           | Notes                    |
|------------|----------------|-------------------------|
| OrderID    | INT IDENTITY PK| Primary key             |
| CustomerID | INT            | Foreign key → Customers |
| OrderDate  | DATETIME       |                         |
| TotalAmount| DECIMAL(10,2)  |                         |

### OrderDetails
| Column        | Type           | Notes                     |
|---------------|----------------|--------------------------|
| OrderDetailID | INT IDENTITY PK| Primary key              |
| OrderID       | INT            | Foreign key → Orders     |
| ProductID     | INT            | Foreign key → Products   |
| Quantity      | INT            |                          |

### Payments
| Column       | Type           | Notes                  |
|-------------|----------------|-----------------------|
| PaymentID   | INT IDENTITY PK| Primary key           |
| OrderID     | INT            | Foreign key → Orders  |
| PaymentDate | DATETIME       |                       |
| Amount      | DECIMAL(10,2)  |                       |
| PaymentMethod| NVARCHAR(50)  |                       |

---

## ⚡ SQL Scripts

You can create the database and tables using the following scripts:

```sql
CREATE DATABASE StoreDB;
GO
USE StoreDB;
GO

-- Create tables here (Customers, Categories, Products, Orders, OrderDetails, Payments)
