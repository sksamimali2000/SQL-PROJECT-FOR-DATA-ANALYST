# 📚 Online Bookstore – SQL Database Project


## 📌 Project Overview
The **Online Bookstore Database Project** is designed to simulate a real-world e-commerce bookstore's backend database.  
It includes:
- **Books** inventory management
- **Customer** records
- **Orders** and sales tracking  
Built using **PostgreSQL**, this project demonstrates **database creation, data import, and analytical queries** for both operational and business intelligence purposes.

---

## 🛠 Tech Stack
- **Database:** PostgreSQL
- **Data Import:** CSV via `COPY` command
- **Language:** SQL
- **Environment:** pgAdmin / psql

---

## 📂 Database Schema

### 1️⃣ Books Table
| Column         | Type            | Description                     |
|----------------|----------------|---------------------------------|
| Book_ID        | SERIAL (PK)    | Unique ID for each book         |
| Title          | VARCHAR(100)   | Book title                      |
| Author         | VARCHAR(100)   | Author's name                   |
| Genre          | VARCHAR(50)    | Genre (Fiction, Fantasy, etc.)  |
| Published_Year | INT            | Year of publication             |
| Price          | NUMERIC(10,2)  | Price of the book               |
| Stock          | INT            | Available quantity              |

### 2️⃣ Customers Table
| Column       | Type           | Description             |
|--------------|---------------|-------------------------|
| Customer_ID  | SERIAL (PK)   | Unique ID for customer   |
| Name         | VARCHAR(100)  | Full name               |
| Email        | VARCHAR(100)  | Contact email           |
| Phone        | VARCHAR(15)   | Contact number          |
| City         | VARCHAR(50)   | Customer's city         |
| Country      | VARCHAR(150)  | Customer's country      |

### 3️⃣ Orders Table
| Column       | Type           | Description                   |
|--------------|---------------|--------------------------------|
| Order_ID     | SERIAL (PK)   | Unique ID for the order        |
| Customer_ID  | INT (FK)      | Links to Customers table       |
| Book_ID      | INT (FK)      | Links to Books table           |
| Order_Date   | DATE          | Date of purchase               |
| Quantity     | INT           | Number of books ordered        |
| Total_Amount | NUMERIC(10,2) | Total price of the order       |

---

## 📥 Data Import
Sample data for `Books`, `Customers`, and `Orders` is loaded via:

```sql
COPY Books(Book_ID, Title, Author, Genre, Published_Year, Price, Stock) 
FROM 'path/to/Books.csv' CSV HEADER;

COPY Customers(Customer_ID, Name, Email, Phone, City, Country) 
FROM 'path/to/Customers.csv' CSV HEADER;

COPY Orders(Order_ID, Customer_ID, Book_ID, Order_Date, Quantity, Total_Amount) 
FROM 'path/to/Orders.csv' CSV HEADER;



📈 Key Business Use Cases
Inventory Management → Track stock, restock low-quantity books.

Sales Tracking → Monitor high-revenue books & peak sales months.

Customer Insights → Identify loyal customers & their preferences.

Genre Analysis → Understand market demand per book genre.

Author Performance → Measure sales per author for contract renewals.


🚀 Future Enhancements
Add stored procedures for automated stock updates.

Create views for monthly sales dashboards.

Integrate with Power BI for visual analytics.

Implement triggers for automatic inventory alerts.

👨‍💻 Author
SK Samim Ali
M.Sc. Computational Science and Application (Data Science)
📧 Email: [roy871858@gmail.com]
