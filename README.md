# sql_practice_part 1
Refreshed my SQL knowledge
I worked through SQLBolt Tutorial (https://sqlbolt.com/lesson) in order to refresh my SQL knowledge. 
I learned the following:

1. The tutorial was extremely useful for refreshing aggregate functions, for example:
    1.1. Finding a specific number of items (in this case artists):
    SELECT role, COUNT(*) as number_of_artists
    FROM employees
    WHERE role = "Artist"
    
    1.2. Calculating totals (this case for the total number of years worked by all engineers)
    SELECT role, SUM(years_employed)
    FROM employees
    GROUP BY role
    HAVING role = "Engineer"

2. Refreshed my knowledge of JOINS, for example:

    2.1. Inner Joins
    SELECT title, domestic_sales, international_sales
    FROM movies
    INNER JOIN boxoffice
        ON movies.id = boxoffice.movie_id
    WHERE international_sales > domestic_sales

    2.2. Left Joins
    SELECT DISTINCT building_name, role 
    FROM buildings 
    LEFT JOIN employees
        ON building_name = building

3. I haven't worked with creating or editing tables in the database in the professional setting before,
   but I enjoyed learning the basics of inserting new data, updating existing data and inserting new tables.
   A few examples of the code:

    3.1. Updating Existing Tables
    UPDATE movies
    SET title = "Toy Story 3", director = "Lee Unkrich"
    WHERE id = 11;

    3.2. Altering Tables
      ALTER TABLE Movies
      ADD COLUMN Aspect_ratio FLOAT DEFAULT 2.39;
    
    3.3. Creating New Table
    CREATE TABLE Database (
        Name TEXT,
        Version FLOAT,
        Download_count INTEGER
        );
