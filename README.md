
Library Management System (Java + MySQL)
=======================================

A full-stack Java + MySQL application for managing library inventory, users, and transactions.

Features
--------
- Add, update, and delete books in the library inventory
- Register and manage library members
- Handle book borrowing and returns
- Track due dates and late returns
- Generate reports for transactions and inventory status

Tech Stack
----------
- Backend: Java (JDBC)
- Database: MySQL
- Build Tool: Gradle
- UI (optional): Swing / JavaFX

Project Structure
-----------------
LibraryManagementSystem/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── models/
│   │   │   ├── services/
│   │   │   ├── dao/
│   │   │   └── Main.java
├── resources/
│   └── schema.sql
├── build.gradle
└── README.txt

Database Schema
---------------
- Books: book_id, title, author, isbn, status
- Members: member_id, name, email, phone
- Transactions: transaction_id, book_id, member_id, borrow_date, return_date

Getting Started
---------------
1. Clone the repository:
   git clone https://github.com/yourusername/LibraryManagementSystem.git
   cd LibraryManagementSystem

2. Set up the MySQL database:
   - Run the schema.sql file to create tables
   - Update DB credentials in the Java code

3. Build the project:
   ./gradlew build

4. Run the application:
   java -jar build/libs/LibraryManagementSystem.jar

Sample SQL Schema
-----------------
CREATE TABLE books (
  book_id INT PRIMARY KEY AUTO_INCREMENT,
  title VARCHAR(255),
  author VARCHAR(255),
  isbn VARCHAR(20),
  status ENUM('available', 'borrowed') DEFAULT 'available'
);

CREATE TABLE members (
  member_id INT PRIMARY KEY AUTO_INCREMENT,
  name VARCHAR(255),
  email VARCHAR(255),
  phone VARCHAR(20)
);

CREATE TABLE transactions (
  transaction_id INT PRIMARY KEY AUTO_INCREMENT,
  book_id INT,
  member_id INT,
  borrow_date DATE,
  return_date DATE,
  FOREIGN KEY (book_id) REFERENCES books(book_id),
  FOREIGN KEY (member_id) REFERENCES members(member_id)
);

Contact
-------
Feel free to reach out via [your email] or open an issue if you have questions or feature requests.
