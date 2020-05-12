# Used Commands in SQL

-- CREATE TABLE film_table
-- (
--     film_id INT IDENTITY(1,1),
--     film_name VARCHAR(20),
--     film_type VARCHAR(10),
--     date_of_release DATE,
--     director VARCHAR(20),
--     writer VARCHAR(20),
--     star VARCHAR(20),
--     film_language VARCHAR(10),
--     offical_website VARCHAR(50),
--     plot_summary VARCHAR(150)
-- );

-- SELECT *
-- FROM film_table;

-- SP_HELP film_table;

-- DROP TABLE film_table;

-- ALTER TABLE film_table
-- ADD rating INT;

-- ALTER TABLE film_table
-- DROP COLUMN star;

-- INSERT INTO film_table
-- (
--     film_name, film_type, director, writer, film_language, offical_website, plot_summary, rating
-- )
-- VALUES
-- (
--     'Singhplotion', 'comedy', 'Brad Ward', 'Brad Ward', 'English', 'Youtube.com', 'The epic life stroy of singhnamie', 10
-- )

-- INSERT INTO film_table
-- (
--  date_of_release
-- )
-- VALUES
-- (
--    '20200725'
-- )


-- CREATE TABLE work_hours
-- (
--     dates VARCHAR(10),
--     hours_working INT,
--     start_time TIME,
--     end_time TIME,
--     PRIMARY KEY (dates),
--     staff_id INT IDENTITY(1,1) FOREIGN KEY REFERENCES staff_details(staff_id)
-- );
