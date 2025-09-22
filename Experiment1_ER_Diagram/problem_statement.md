# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
*Paste or attach your diagram here*  
![TarunKumar_ERWorkshop](https://github.com/user-attachments/assets/1a4b33b0-8f39-439b-808f-2b72245daf5c)


### Entities and Attributes

| Entity     |        Attributes (PK, FK)              | Notes             |
|------------|-----------------------------------------|-------------------|
| Member     | member_id, name, membership_type,       | Details of        |
|            | start_date, contact_info                | members           |
| Program    | program_id, program_name, description,  | Details of        |
|            | duration                                | programs          |
| Trainer    | trainer_id, name, specialization,       | Details of        |
|            | contact_info                            | trainers          |
| Session    | session_id, date, time, member_id       | Details of        |
|            | trainer_id                              | sessions          |
| Attendance | attendance_id, date, status,            | Details of        |
|            | session_id                              | attendance        |
| Payment    | payment_id, amount, payment_date,       | Details of        |
|            | payment_type, member_id                 | transactions      |

### Relationships and Constraints

|     Relationship    | Cardinality |    Participation     |                Notes                    |
|---------------------|-------------|----------------------|-----------------------------------------|
| member_program      | M:N         | Member, Program      | Details of membership                   |
| trainer_program     | M:N         | Trainer, Program     | Details of trainer plan                 | 
| personal_session    | 1:1         | Member, Trainer      | Details of member and personal trainer  |
| fees                | 1:M         | Member, Payment      | Details of fees transcation             |
| tracking            | 1:1         | Session, Attendance  | Details of member and personal trainer  |

### Assumptions
- There are members and trainers, members have different membership types (e.g., daily, monthly).
- The system tracks classes and equipment, and there's a focus on managing attendance and payments. 

---

# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
