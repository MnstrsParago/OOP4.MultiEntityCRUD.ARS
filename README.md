# ✈️ Airline Reservation System (ARS) - Multi-Entity CRUD REST API

**Subject:** Object-Oriented Programming (OOP) / REST API / CRUD / JDBC  
**Name:** Abdanur

## 📌 Project Description
This repository is a Java **REST API** for an Airline Reservation System (ARS).  
It connects to a **PostgreSQL** database and provides full **CRUD** operations for multiple entities:

- `Passenger`
- `Flight`
- `Reservation`

This project continues the previous work from:
https://github.com/MnstrsParago/OOP3.PassengerCRUD.ARS

I used **Postman** to test all CRUD endpoints.

## 💡 Features
- REST API built with Java built-in `HttpServer` (no heavy frameworks)
- CRUD endpoints for **Passengers**, **Flights**, and **Reservations**
- JSON request and response bodies
- PostgreSQL database integration using **JDBC**
- Prepared statements for safer SQL queries
- Easy API testing with **Postman**

## 📦 Technologies
- **Java**
- **PostgreSQL**
- **JDBC**
- **com.sun.net.httpserver.HttpServer**
- **org.json** (JSON parsing)
- **Postman** (API testing)
- Git + GitHub

## 🚀 How to Run
1) Clone the repository:
```bash
git clone https://github.com/MnstrsParago/OOP4.MultiEntityCRUD.ARS.git
cd OOP4.MultiEntityCRUD.ARS
```

2) Create a PostgreSQL database (example name used in the project: `airressys`), then create tables:

```sql
CREATE TABLE Passenger (
  id SERIAL PRIMARY KEY,
  name TEXT,
  passport_number TEXT,
  nationality TEXT,
  date_of_birth DATE
);

CREATE TABLE Flight (
  id SERIAL PRIMARY KEY,
  flight_number TEXT,
  origin TEXT,
  destination TEXT,
  departure_time TEXT
);

CREATE TABLE Reservation (
  id SERIAL PRIMARY KEY,
  passenger_id INT REFERENCES Passenger(id),
  flight_id INT REFERENCES Flight(id),
  seat_number TEXT
);
```

3) Add required `.jar` libraries to `lib/` (if the project uses local libs):
- PostgreSQL JDBC driver
- JSON library

4) Update database connection settings in the code (URL / user / password).

5) Compile and run (example):
```bash
javac -cp "lib/*" PassengerAPI.java
java -cp ".:lib/*" PassengerAPI
```

Server example:
```
http://localhost:8080
```

## 📘 Reflection
This project helped me practice building a bigger REST API with more than one entity.  
I learned how to organize endpoints, keep database logic clear, and test the full CRUD flow using Postman with Bigget Dataset.
