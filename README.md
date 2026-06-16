# ProductApp

A **Java Web Application** for managing products using **Servlet, JSP, JDBC, and MySQL**. The application provides complete **CRUD (Create, Read, Update, Delete)** functionality with a responsive user interface built using **Bootstrap 5**. It is developed in **Eclipse IDE** and deployed on **Apache Tomcat 9**.

---

## 🚀 Features

* ➕ Add new products
* 📋 View all products in a tabular format
* ✏️ Update existing product details
* 🗑️ Delete products from the database
* 📱 Responsive user interface using Bootstrap 5
* 💾 Persistent data storage with MySQL and JDBC

---

## 🛠️ Technology Stack

| Layer        | Technology                  |
| ------------ | --------------------------- |
| Frontend     | JSP, HTML, CSS, Bootstrap 5 |
| Backend      | Java Servlet (Jakarta EE)   |
| Database     | MySQL                       |
| Connectivity | JDBC                        |
| JDBC Driver  | MySQL Connector/J 9.x       |
| Web Server   | Apache Tomcat 9             |
| IDE          | Eclipse                     |

---

## 📂 Project Structure

```
productapp/
├── src/main/java/com/productapp/
│   ├── controller/
│   │   └── ProductServlet.java
│   │
│   ├── dao/
│   │   └── ProductDAO.java
│   │
│   ├── model/
│   │   └── Product.java
│   │
│   ├── service/
│   │   └── ProductService.java
│   │
│   └── util/
│       └── DBConnection.java
│
└── src/main/webapp/
    ├── index.jsp
    └── WEB-INF/
        └── web.xml
```

### Layer Responsibilities

* **ProductServlet** – Handles HTTP requests for listing, adding, updating, and deleting products.
* **ProductDAO** – Performs CRUD operations using JDBC and MySQL.
* **ProductService** – Contains business logic and communicates with the DAO layer.
* **Product** – Java Bean representing product details (`productId`, `productName`, `price`).
* **DBConnection** – Manages database connectivity.
* **index.jsp** – User interface for displaying and managing products.

---

## 🗄️ Database Setup

Execute the following SQL commands:

```sql
CREATE DATABASE product;

USE product;

CREATE TABLE product (
    product_id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    product_name VARCHAR(100) NOT NULL,
    price DECIMAL(10,2) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## ⚙️ Database Configuration

Update your database credentials in `DBConnection.java`:

```java
private static final String URL = "jdbc:mysql://localhost:3306/product";
private static final String USER = "root";
private static final String PASSWORD = "your_password";
```

---

## ▶️ How to Run the Project

1. Clone the repository:

```bash
git clone https://github.com/Sanidhyavyas/ProductApp.git
```

2. Import the project into Eclipse as an **Existing Project**.

3. Add the **MySQL Connector/J** JAR file to the project's Build Path.

4. Configure **Apache Tomcat 9** in Eclipse.

5. Right-click the project and select:

```
Run As → Run on Server
```

6. Open the application in your browser:

```
http://localhost:8080/productapp/product
```

---

## 🔄 CRUD Workflow

### Add Product

Users can enter the product name and price to insert a new record into the database.

### View Products

All products stored in the database are displayed dynamically in a Bootstrap table.

### Edit Product

Selecting **Edit** sends:

```
GET /product?action=edit&id={productId}
```

The servlet retrieves the selected product, pre-fills the form, and includes a hidden `productId` field. Upon submission, the record is updated instead of inserted.

### Delete Product

Selecting **Delete** sends:

```
GET /product?action=delete&id={productId}
```

The servlet removes the corresponding record from the database and redirects the user back to the updated product list.

---

## 📌 Key Concepts Used

* MVC Architecture
* Java Servlets
* JSP
* JDBC Connectivity
* MySQL Database
* Layered Architecture (Controller → Service → DAO)
* Bootstrap 5 Responsive Design
* CRUD Operations
* HTTP GET and POST Methods

---

## 🎯 Future Enhancements

* Product search functionality
* Pagination and sorting
* User authentication and authorization
* Form validation with JavaScript
* REST API integration
* Image upload for products
* Session management
* JSTL and Expression Language support

---

## 👨‍💻 Author

**Sanidhya Vyas**

A simple and efficient Product Management System demonstrating Java Web Development using Servlets, JSP, JDBC, and MySQL with a clean layered architecture.
