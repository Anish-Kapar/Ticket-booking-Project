<div align="center">

# 🚆 Ticket Booking System

### A Java-based Command Line Railway Ticket Booking Application

[![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.java.com/)
[![Gradle](https://img.shields.io/badge/Gradle-02303A?style=for-the-badge&logo=gradle&logoColor=white)](https://gradle.org/)
[![CLI](https://img.shields.io/badge/Interface-CLI-blue?style=for-the-badge&logo=windowsterminal&logoColor=white)]()
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)]()

<br/>

> A fully functional train ticket booking system built in Java using Gradle, featuring a JSON-based local database of trains and users, enabling passengers to search trains, book tickets, and manage reservations — all from the terminal.

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Getting Started](#-getting-started)
- [How to Run](#-how-to-run)
- [Local Database](#-local-database)
- [Architecture Overview](#-architecture-overview)
- [Contributing](#-contributing)
- [Author](#-author)

---

## 🧭 Overview

The **Ticket Booking System** is a Java CLI application that simulates a real-world railway ticket booking workflow. It is built using **Gradle** as the build tool and follows a clean layered architecture — separating entities, services, and utilities into distinct packages under `org.ticket.booking`.

Instead of a traditional external database, the project uses a **local JSON-based data store** (`localDb/`) containing `trains.json` and `users.json`. All train lookups, user management, and booking logic are handled in-memory via the service layer, making the project fully self-contained and easy to run on any machine.

---

## ✨ Features

- 🔍 **Search Trains** — Find available trains between stations
- 🎟️ **Book Tickets** — Reserve seats for registered users
- 👤 **User Management** — Handle user accounts and their associated bookings
- 🗄️ **JSON Local Database** — Pre-loaded train and user data stored in `.json` files — no external DB needed
- 🏗️ **Layered Architecture** — Clean separation of Entities, Services, and Utilities
- 💻 **Pure CLI Interface** — Runs entirely in the terminal

---

## 📁 Project Structure

```
Ticket-Booking-System/
│
├── .gradle/                             # Gradle wrapper cache
├── .idea/                               # IntelliJ IDEA project config
│
└── app/
    └── src/
        └── main/
            └── java/
                └── org/ticket/booking/
                    │
                    ├── entities/                    # Data model classes
                    │   ├── Ticket.java              # Ticket entity
                    │   ├── Train.java               # Train entity
                    │   └── User.java                # User entity
                    │
                    ├── localDb/                     # JSON-based local database
                    │   ├── trains.json              # Train data (routes, seats, schedules)
                    │   └── users.json               # User data and booking records
                    │
                    ├── services/                    # Business logic layer
                    │   ├── TrainService.java         # Train search and operations
                    │   └── UserBookingService.java   # Booking and user operations
                    │
                    ├── util/                        # Utility helpers
                    │   └── UserServiceUtil.java
                    │
                    └── App.java                     # Application entry point
│
├── build.gradle                         # Gradle build configuration
└── resources/                           # App resources
```

---

## ✅ Prerequisites

| Requirement | Version      | Download |
|-------------|--------------|----------|
| Java JDK    | 11 or higher | [Download JDK](https://www.oracle.com/java/technologies/downloads/) |
| Gradle      | 7+           | [Download Gradle](https://gradle.org/install/) *(or use the Gradle wrapper)* |
| Git         | Any          | [Download Git](https://git-scm.com/) |

Verify your setup:
```bash
java -version
gradle -version
```

> ✅ This project includes a **Gradle wrapper** (`gradlew`), so you don't need Gradle installed globally — the wrapper downloads the correct version automatically.

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Anish-Kapar/Ticket-booking-Project.git
cd Ticket-booking-Project
```

### 2. Build the Project

```bash
# macOS / Linux
./gradlew build

# Windows
gradlew.bat build
```

### 3. Run the Application

```bash
# macOS / Linux
./gradlew run

# Windows
gradlew.bat run
```

---

## ▶️ How to Run

```bash
# 1. Clone the repo
git clone https://github.com/Anish-Kapar/Ticket-booking-Project.git
cd Ticket-booking-Project

# 2. Build and run
./gradlew run
```

The application will launch in your terminal with an interactive menu for searching trains and booking tickets.

---

## 🗄️ Local Database

This project uses a **JSON file-based local data store** located at:

```
app/src/main/java/org/ticket/booking/localDb/
```

No external database (MySQL, MongoDB, etc.) is required.

| File | Description |
|------|-------------|
| `trains.json` | Contains train data — train names, numbers, routes, available seats, and schedules |
| `users.json` | Contains user account data and their associated ticket bookings |

These files are loaded and parsed at runtime by the service layer (`TrainService`, `UserBookingService`) to serve all application data.

> 💡 You can manually edit these JSON files to add new trains or users before running the app.

---

## 🏗️ Architecture Overview

```
App.java  (Entry Point)
    │
    ├── UserBookingService    ──►  User.java  /  Ticket.java
    │       └── UserServiceUtil.java
    │
    └── TrainService          ──►  Train.java
            └── localDb/trains.json
                localDb/users.json
```

| Layer | Classes | Responsibility |
|-------|---------|----------------|
| **Entities** | `Train`, `User`, `Ticket` | Core data models representing domain objects |
| **Services** | `TrainService`, `UserBookingService` | Business logic — search, book, manage |
| **Util** | `UserServiceUtil` | Reusable helper methods for the service layer |
| **LocalDb** | `trains.json`, `users.json` | Lightweight JSON-based persistent data store |

---

## 🤝 Contributing

Contributions and suggestions are welcome!

1. Fork the repository
2. Create a new branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "Add: your feature description"`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

---

## 👨‍💻 Author

**Anish Kapar**

[![GitHub](https://img.shields.io/badge/GitHub-Anish--Kapar-181717?style=for-the-badge&logo=github)](https://github.com/Anish-Kapar)

---

<div align="center">

Made with ❤️ and Java

⭐ *If you found this project useful, consider giving it a star!* ⭐

</div>
