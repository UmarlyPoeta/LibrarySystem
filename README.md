
# 📚 Library Management System

A desktop application built with **JavaFX**, **FXML**, **MySQL**, and **Maven**, designed for managing a collection of books.

---

## 🧾 Features

* 🔍 Search books by title
* ➕ Insert new books into the database
* ✏️ Update selected book details
* ❌ Delete selected books
* 🔄 Refresh the book list
* 🅰️ Sort books alphabetically by title
* 📄 FXML-based UI switching (Primary ↔ Secondary views)

---

## 📁 Project Structure

```
librarysystem/
├── pom.xml
└── src/
    └── main/
        ├── java/
        │   ├── module-info.java
        │   └── com/
        │       └── mylibrary/
        │           ├── Book.java
        │           └── LibraryUI.java
        └── resources/
            └── com/
                └── mylibrary/
                    ├── primary.fxml
                    └── secondary.fxml
```

---

## 🧰 Technologies Used

* Java 22 (configured for Java 11 compatibility via `pom.xml`)
* JavaFX 22.0.2 (Controls & FXML)
* MySQL + JDBC
* Maven
* FXML for UI layout

---

## 🗃️ Database Setup

Run the following SQL script in MySQL to set up the required table:

```sql
CREATE DATABASE IF NOT EXISTS LibraryDB;
USE LibraryDB;

CREATE TABLE IF NOT EXISTS Books (
    book_id INT AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(255) NOT NULL,
    author VARCHAR(255) NOT NULL,
    available BOOLEAN NOT NULL
);
```

---

## ⚙️ Configuration

Edit your database credentials in `LibraryUI.java`:

```java
private Connection connect() throws SQLException {
    String url = "jdbc:mysql://localhost:3306/LibraryDB";
    String user = "root";         // ← change if needed
    String password = "password"; // ← change if needed
    return DriverManager.getConnection(url, user, password);
}
```

---

## 🚀 How to Run

1. Install Java 11+ and MySQL.
2. Set up the database (see above).
3. Clone this repository:

   ```bash
   git clone https://github.com/UmarlyPoeta/LibrarySystem.git
   cd LibrarySystem
   ```
4. Run the application with Maven:

   ```bash
   mvn clean javafx:run
   ```

💡 Ensure your IDE supports JavaFX and FXML (like IntelliJ IDEA with JavaFX plugin).

---

## 🔧 Maven Configuration Highlights

The `pom.xml` includes:

* JavaFX dependencies (`javafx-controls`, `javafx-fxml`)
* MySQL Connector/J
* JavaFX Maven Plugin for simplified running

---

## 📌 FXML Views

* `primary.fxml` and `secondary.fxml` exist for future expansion using FXML-based scene switching.
* Controllers (`PrimaryController`, `SecondaryController`) are referenced but not implemented yet in the provided code.

---

## 🧪 To Do

* ✅ Hook up FXML views to actual logic
* 🔐 Add user authentication
* 📦 Export book data (CSV/JSON)
* 🔍 Add filter by availability
* 🧪 Add JUnit tests

---

## 📜 License

This project is open source and available for educational use and contributions.

---
