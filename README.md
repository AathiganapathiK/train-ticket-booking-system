# Train Ticket Booking System

A web-based application built using Java Servlets, JSP, and MySQL that enables users to register, log in, search trains, book tickets, and view booking details. Administrators can manage trains, view passengers, and monitor bookings through a dedicated dashboard.

## Features

### Admin
- Secure login using admin credentials.
- Add new train details including train number, name, date, time, origin, destination, price, and seat capacity.
- Edit or delete existing train details.
- View the list of all trains.
- View all booked passenger information.
- Logout functionality.

### User
- Create a new account by entering full name, age, gender, phone number, email, and password.
- Login using registered email and password.
- View available train list with details.
- Book train tickets by selecting seats.
- View all booked tickets and booking details.
- Logout securely.

## Technologies Used

- Java (JSP & Servlet)
- MySQL Database
- JDBC (Java Database Connectivity)
- Apache Tomcat v10
- HTML and CSS
- Eclipse IDE (Enterprise Edition)

## Project Structure
```
TrainTicketBookingSystem/
│
├── src/main/java/
│   └── (default package)
│ 	  └── AddNewTrainServlet.java
│ 	  └── AdminLoginServlet.java
│ 	  └── BookedPassengersServlet.java
│ 	  └── BookedTrainDetailsServlet.java
│ 	  └── BookSeatsServlet.java
│ 	  └── BookTicketServlet.java
│ 	  └── ChangePasswordServlet.java
│ 	  └── CreateAccountServlet.java
│ 	  └── DeleteTrainServlet.java
│ 	  └── DeleteUserServlet.java
│ 	  └── EditTrainServlet.java
│ 	  └── EditUserServlet.java
│ 	  └── UserLoginServlet.java
│   └── DBC
│ 	  └── DBConnection.java
│
├── WebContent
│	  └── images
│ 	      └── all images
│	  └── add-new-train.jsp
│	  └── admin-dashboard.jsp
│	  └── admin-login.jsp
│	  └── admin-logout.jsp
│	  └── booked-passengers.jsp
│	  └── booked-train-details.jsp
│	  └── book-ticket.jsp
│	  └── change-password.jsp
│	  └── confirm-logout.jsp
│	  └── confirm-logout-admin.jsp
│	  └── create-account.jsp
│	  └── delete-train.jsp
│	  └── delete-user.jsp
│	  └── edit-train.jsp
│	  └── edit-user.jsp
│	  └── error.jsp
│	  └── error1.jsp
│	  └── error2.jsp
│	  └── erroraccount.jsp
│	  └── erroradd-students.jsp
│	  └── erroradd1.jsp
│	  └── errorbook.jsp
│	  └── index.jsp
│	  └── list-trains.jsp
│	  └── list-trains-user.jsp
│	  └── user-dashboard.jsp
│	  └── user-details.jsp
└──   └── user-login.jsp
```

## Database Details (MySQL)

### Database Name: `train_ticket_booking`

### Tables Included

1. **`admin`**  
   Stores administrator credentials.

2. **`users`**  
   Stores user profile details.

3. **`user_login`**  
   Stores login authentication data for users.

4. **`trains`**  
   Stores all train information such as name, timing, route, price, and seat capacity.

5. **`available_seats`**  
   Tracks remaining seats for each train.

6. **`bookings`**  
   Stores booking details for each user including fare, seats booked, and timestamp.

### Table Relationships

- `train_number` links the following tables:
  - `trains`
  - `available_seats`
  - `bookings`

- `email` links:
  - `users`
  - ``user_login``
  - ``bookings``

### Key Database Operations

- Insert, update, and delete train records.
- Maintain user details and login credentials.
- Book ticket, update seat availability, and store booking details.
- Fetch bookings for admin and user dashboards.

## How to Run the Project

1. Install Apache Tomcat v10.
2. Install MySQL and create the database `train_ticket_booking`.
3. Import all required tables using provided SQL scripts.
4. Open Eclipse IDE for Enterprise Java Developers.
5. Import the project as an existing dynamic web project.
6. Add Apache Tomcat v10 to the server runtime environment.
7. Configure MySQL credentials in `DBConnection.java`.
8. Run the project on Tomcat server.

## GitHub Repository Structure

This repository contains:
- All servlets for backend logic.
- JSP pages for front-end UI.
- Database connection utilities.
- WebContent folder with images and UI screens.
- Complete CRUD operations for trains, users, and bookings.

