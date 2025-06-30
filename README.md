# ✈️ Airline Ticket Booking System (Backend)

A robust and scalable **Airline Ticket Booking System** built with **Node.js**, **Express**, and a **Microservice Architecture**. This backend project handles all core airline operations including **user management**, **flight scheduling**, **ticket booking**, **payment processing**, and **notification services**.

---

## 🧱 Architecture Overview

This system follows a **Microservices Architecture** to ensure modularity, scalability, and maintainability. The application consists of multiple independent services, each handling a specific domain responsibility and communicating via REST APIs and queues (for async operations).

---

## 📦 Microservices Breakdown

### 1. **User Service**

Handles **user onboarding**, **authentication**, and **authorization**.
Key features:

* **User Registration & Login** (JWT-based authentication)
* **Role-based Authorization** (`User`, `Admin`)
* Admin functionalities to manage users and view system activity

---

### 2. **Flight Service**

Manages all operations related to **flights** and **boarding cities**.
Key features:

* **CRUD operations** on flight records
* Manage **city-wise boarding points**
* **Search functionality** based on:

  * **Source** & **Destination**
  * **Price**
  * **Flight Date**
  * **Boarding City**

---

### 3. **Booking & Payment Service**

Handles **ticket booking** with transactional consistency.
Key features:

* **Two-step transaction** model:

  * Commit flight booking
  * Separate **payment service** for finalizing booking
* **Transaction Rollback** in case of failures
* **Auto-cancellation** for:

  * User-initiated cancellations
  * **Timeout-based expiry** (unpaid tickets)
* Maintains **booking history** and status tracking

---

### 4. **Notification Service**

Manages **user notifications** via **email**.
Key features:

* Sends **ticket confirmation** emails
* **Queue-based email processing** to ensure smooth and non-blocking operations
* Utilizes message queue to decouple from other services

---

### 5. **Reminder Service**

Sends **boarding reminders** to users.
Key features:

* Uses **cron jobs** to schedule **pre-boarding email notifications**
* Reminds users **a few days before the flight date**
* Integrated with the Notification Service for email dispatch

---

## ⚙️ Tech Stack

* **Node.js**
* **Express.js**
* **JWT** for Authentication
* **MySql** 
* **Nodemailer** for Emails
* **Cron Jobs** using `node-cron`
* **Docker** for containerization
* **Postman** Collection for API testing

---

## 🔐 Security & Performance

* **JWT-based secure authentication**
* **Role-based access control**
* **Queue-based async processing** for email notifications
* **Proper error handling** and **transaction rollback mechanisms** ensure data consistency
* **Timeout-based ticket expiry logic**

---

## 📁 Project Structure (Simplified)

```
/airline-booking-backend/
│
├── user-service/
├── flight-service/
├── booking-service/
├── notification-service/
├── reminder-service/
│
├── docker-compose.yml (if applicable)
└── README.md
```

---

## 🚀 Getting Started

1. Clone the repository:

   ```bash
   git clone https://github.com/Suvendu-Sekhar-Patra/Airline-Ticket-Booking-System.git
   cd Airline-Ticket-Booking-System
   ```

2. Set up `.env` for each service with required configurations

3. Install dependencies:

   ```bash
   npm install
   ```

4. Start each service (manually or via Docker Compose)

---

## 🧪 Testing

* Use **Postman** or any API client to test individual services
* Ensure services are up on different ports

---

## 📬 Contact & Contribution

Have suggestions or want to contribute?

* **Fork** the repository
* Create a feature branch
* Open a **Pull Request**

