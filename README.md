# 🚆 Train Ticket Booking System  
A complete web-based Train Ticket Booking Application built using **Java (JSP + Servlets)**, **MySQL**, and **Tomcat Server**.  
This system allows users to search trains, book tickets, manage bookings, and provides an admin panel to manage trains.

---

## 📌 Features

### 👤 User Module
- User Registration & Login  
- Search trains by route  
- Book tickets easily  
- Check available seats  
- View booking details  
- Cancel bookings  

### 🛠️ Admin Module
- Admin login  
- Add new trains  
- Edit train details  
- Manage seat availability  
- View all bookings  

### 💾 Database Features
- Secure login system  
- Seat availability management  
- Real-time seat updates after booking/cancellation  

---

## 🧰 Tech Stack Used

### **Frontend**
- HTML5  
- CSS3  
- JSP (Java Server Pages)  

### **Backend**
- Java  
- Servlets  
- JDBC  
- MVC Architecture  

### **Database**
- MySQL  
- SQL Queries for CRUD operations  

### **Server**
- Apache Tomcat v10  

### **Tools Used**
- Eclipse IDE  
- MySQL Workbench / phpMyAdmin  
- Git & GitHub  

---

## 🗄️ Database Structure (train_ticket_booking)

Below is the complete database schema required for the project.

### 🔐 **Admin Table**
```sql
CREATE TABLE admin (
    id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) UNIQUE NOT NULL,
    password VARCHAR(100) NOT NULL,
    role VARCHAR(20) NOT NULL DEFAULT 'admin'
);
```

### 👥 **Users Table**
```sql
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    full_name VARCHAR(100) NOT NULL,
    age INT NOT NULL,
    gender VARCHAR(10) NOT NULL,
    phone_number VARCHAR(15) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL
);
```

### 🔑 **User Login Table**
```sql
CREATE TABLE user_login (
    id INT PRIMARY KEY AUTO_INCREMENT,
    email VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(100) NOT NULL
);
```

### 🚆 **Trains Table**
```sql
CREATE TABLE trains (
    train_number VARCHAR(20) PRIMARY KEY,
    train_name VARCHAR(100) NOT NULL,
    departure_date DATE NOT NULL,
    departure_time TIME NOT NULL,
    from_station VARCHAR(100) NOT NULL,
    to_station VARCHAR(100) NOT NULL,
    price_per_seat DECIMAL(10,2) NOT NULL,
    max_seats INT NOT NULL
);
```

### 🎫 **Seat Availability Table**
```sql
CREATE TABLE available_seats (
    train_number VARCHAR(20),
    available_seats INT NOT NULL,
    FOREIGN KEY (train_number) REFERENCES trains(train_number)
);
```

### 📄 **Bookings Table**
```sql
CREATE TABLE bookings (
    id INT PRIMARY KEY AUTO_INCREMENT,
    full_name VARCHAR(100) NOT NULL,
    phone_number VARCHAR(20) NOT NULL,
    email VARCHAR(100) NOT NULL,
    train_name VARCHAR(100) NOT NULL,
    train_number VARCHAR(20) NOT NULL,
    departure_date DATE NOT NULL,
    departure_time TIME NOT NULL,
    from_station VARCHAR(100) NOT NULL,
    to_station VARCHAR(100) NOT NULL,
    price_per_seat DECIMAL(10,2) NOT NULL,
    seats_booked INT NOT NULL,
    total_price DECIMAL(10,2) NOT NULL,
    booking_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

## 🚀 How to Run the Project (Local Setup)

### 1️⃣ **Install Requirements**
- Java JDK 17 or above  
- Eclipse IDE for Enterprise Java  
- Apache Tomcat 10  
- MySQL Server  

### 2️⃣ **Import Project**
1. Open Eclipse  
2. File → Import → *Existing Projects into Workspace*  
3. Select the project folder  
4. Finish  

### 3️⃣ **Configure Tomcat**
1. Go to **Servers** tab  
2. Add **Apache Tomcat v10**  
3. Set the location of Tomcat  

### 4️⃣ **Setup Database**
- Create database:
```sql
CREATE DATABASE train_ticket_booking;
```
- Run all the table queries provided above  

### 5️⃣ **Update DB Credentials**  
File:  
`src/main/java/DBC/DBConnection.java`

Modify:
```java
private static final String URL = "jdbc:mysql://localhost:3306/train_ticket_booking";
private static final String USER = "root";
private static final String PASSWORD = "your_password";
```

### 6️⃣ **Run Project**
- Right-click on project → Run As → Run on Server  
- Select Tomcat  
- Start  

---

## 📸 Screenshots  
(Add your project screenshots here)

---

## 📂 Folder Structure

```
/src
/WebContent
/WEB-INF
   |-- web.xml
```

---

## 🧑‍💻 Author
**Aathiganapathi K**

---

## ⭐ Contribute
Feel free to fork, improve and create pull requests!

---

## 📜 License
This project is for educational and learning purposes.

