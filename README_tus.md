# SQL

## Linking two tables

### Step 1:
Make one table and asign a primary key to it.

-- CREATE TABLE staff_details
-- (
--     staff_id INT IDENTITY(1,1),
--     staff_first_name VARCHAR(10),
--     staff_middle_name VARCHAR(10),
--     staff_last_name VARCHAR(10),
--     PRIMARY KEY (staff_id)
-- );

### Step 2
Create a second table, asign a foreign key to it.

CREATE TABLE work_hours
-- (
--     dates VARCHAR(10),
--     hours_working INT,
--     start_time TIME,
--     end_time TIME,
--     PRIMARY KEY (dates),
--     staff_id INT IDENTITY(1,1) FOREIGN KEY REFERENCES staff_details(staff_id)
-- );
***
