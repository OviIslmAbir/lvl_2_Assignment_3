# 🏟️ Football Ticket Booking System
### Database Design & SQL Queries Assignment

## 📌 Overview

This project is a **Football Ticket Booking System** built as a university database assignment. The system simulates a real-world ticket purchasing platform where football fans can browse upcoming matches and book seats for their favorite games.

The goal of this assignment is to design a normalized relational database, define proper entity relationships, and write intermediate-to-advanced SQL queries to extract meaningful insights from the data.

---

## 🗃️ Database Schema

The system is built around **3 core tables**:

### 👤 Users
Stores all registered users of the platform — both administrative staff and football fans.

| Field | Description |
|---|---|
| `user_id` | Unique ID for each registered user |
| `full_name` | First and last name of the user |
| `email` | Email address used for login |
| `role` | Access level — `Ticket Manager` or `Football Fan` |
| `phone_number` | Contact mobile number |

### ⚽ Matches
Catalogs all upcoming tournament matches along with stadium logistics and ticket pricing.

| Field | Description |
|---|---|
| `match_id` | Unique ID for each football match |
| `fixture` | Competing teams (e.g., `Real Madrid vs Barcelona`) |
| `tournament_category` | League or cup name (e.g., `Champions League`) |
| `base_ticket_price` | Standard entry price per seat |
| `match_status` | Availability state — `Available`, `Selling Fast`, `Sold Out`, `Postponed` |

### 🎟️ Bookings
A transactional table that records every individual ticket purchase, linking users to their chosen matches.

| Field | Description |
|---|---|
| `booking_id` | Unique transaction ID for the ticket purchase |
| `user_id` | FK → Links to the user who made the booking |
| `match_id` | FK → Links to the specific match |
| `seat_number` | Allocated seat identifier (e.g., `A-12`) |
| `payment_status` | Financial status — `Pending`, `Confirmed`, `Cancelled`, `Refunded` |
| `total_cost` | Final invoice price |

---

## 📝 Queries Covered

This assignment covers **7 SQL queries** targeting the following real-world scenarios:

| # | Scenario | Concepts Used |
|---|---|---|
| 1 | Filter matches by tournament and availability status | `WHERE`, multiple conditions |
| 2 | Search users by name pattern (case-insensitive) | `LIKE`, `ILIKE` |
| 3 | Detect and handle missing payment status records | `IS NULL`, `COALESCE` |
| 4 | Retrieve full booking details with user and match info | `INNER JOIN` |
| 5 | List all users including those with no bookings | `LEFT JOIN` |
| 6 | Find bookings above the average total cost | Subquery, `AVG()` |
| 7 | Paginate match results by price, skipping the top entry | `ORDER BY`, `LIMIT`, `OFFSET` |

---
## 👨‍💻 Author

**Ovi Islam Abir**
