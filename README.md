# Entity-relationship-model-Checkpoint
# Entity Relationship Model - Gym Management System

This repository provides a comprehensive Entity Relationship Model (ERM) to manage a gym chain's operations. It covers gym locations, members, sessions, and coaches to replace manual card-based systems with an efficient database-driven solution.

## 📌 Project Overview

The goal of this project is to design a database system that accurately represents the relationships between gymnasiums, members, sessions, and coaches. This solution helps automate member registration, session management, and coach assignment.

## 📊 Entity Relationship Model (ERM) Structure

### 1. Gymnasium
- Unique identifier (Primary Key)
- Name
- Address
- Phone Number

### 2. Member
- Unique identifier (Primary Key)
- First Name
- Last Name
- Address
- Date of Birth
- Gender (M/F)
- Gym ID (Foreign Key referencing Gymnasium)

### 3. Coach
- Unique identifier (Primary Key)
- First Name
- Last Name
- Age (Must be over 18)
- Specialty

### 4. Session
- Unique identifier (Primary Key)
- Sport Type
- Schedule (Date & Time)
- Maximum Capacity (Default: 20)
- Gym ID (Foreign Key referencing Gymnasium)

### 5. Relationships
- **Session-Member**: Many-to-Many relationship between Members and Sessions
- **Session-Coach**: Many-to-Many relationship between Sessions and Coaches

## 📂 File Structure
```
├── README.md
└── gym_erp_model.sql
```

## 🛠️ How to Set Up the Database

1. Clone the repository:

    ```bash
    git clone https://github.com/omarmechergui/Entity-relationship-model-Checkpoint.git
    cd Entity-relationship-model-Checkpoint
    ```

2. Ensure PostgreSQL is installed on your system.

3. Create a new database:

    ```sql
    CREATE DATABASE gym_management;
    ```

4. Run the SQL script to initialize the schema:

    ```bash
    psql -U your_username -d gym_management -f gym_erp_model.sql
    ```

## 📌 Usage Instructions

1. **Add a Gymnasium:**

    ```sql
    INSERT INTO Gymnasium (name, address, phone_number) VALUES ('Fitness Pro', '123 Main St', '123-456-7890');
    ```

2. **Register a Member:**

    ```sql
    INSERT INTO Member (last_name, first_name, address, date_of_birth, gender, gym_id)
    VALUES ('Doe', 'John', '456 Elm St', '1990-05-15', 'M', 1);
    ```

3. **Create a Session:**

    ```sql
    INSERT INTO Session (sport_type, schedule, gym_id) VALUES ('Yoga', '2024-03-01 10:00:00', 1);
    ```

## 📋 Future Improvements

- Implement session tracking and attendance.
- Add payment and subscription management.
- Design a web interface for ease of use.

## 📧 Contact

For questions or contributions, feel free to reach out via GitHub Issues or Fork the repository and submit a pull request!

Happy coding! 🚀

