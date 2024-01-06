# HackerRank-SQL

# SQL Easy Challenges

Q1. Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA. 

<img width="292" alt="easy1" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/084f7a1e-b6c8-494d-a666-ef9185e670df">

    SELECT *
    FROM city 
    WHERE 
        population > 100000 AND countrycode = 'USA';

-----
Q2. Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA. 

<img width="283" alt="q2" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/d169f375-ce24-4a7d-b178-13e71f2dd1be">

    SELECT name
    FROM city
    WHERE 
        population > 120000 AND countrycode = 'USA';

-----
Q3. Query all columns (attributes) for every row in the CITY table.

<img width="287" alt="q3" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/a59ef473-90d2-4cc8-9d67-d41648032f0c">

    SELECT *
    FROM city;

-----
Q4. Query all columns for a city in CITY with the ID 1661.

<img width="281" alt="q4" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4594b9db-e9b8-4c8a-9f9d-a9897f65e10a">

    SELECT *
    FROM city 
    WHERE id = 1661;

-----
Q5. Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN. 

<img width="288" alt="q5" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/22bc7aaf-222a-4ef8-a261-6aaefee14d41">

    SELECT *
    FROM city
    WHERE countrycode = 'JPN';

-----
Q6. Query a list of CITY and STATE from the STATION table. 

<img width="240" alt="q6" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4b4a665c-4bf8-46eb-9b68-7330c70db6b7">
    
    SELECT city , state
    FROM station;

-----
Q7. Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer. 

<img width="238" alt="q7" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/ef902d64-f2d0-4b39-b76a-5c06245cd582">

    SELECT DISTINCT city
    FROM station
    WHERE MOD(id,2) = 0;

-----
Q8. Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table. 

<img width="240" alt="q8" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4f101b04-6489-4522-9f9a-a6739ba2b676">

    SELECT 
        COUNT(city) - COUNT(DISTINCT city)
    FROM station;

-----
Q9. Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

<img width="240" alt="q8" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4f101b04-6489-4522-9f9a-a6739ba2b676">

    SELECT city,length(city) 
    FROM station 
    ORDER BY 
        length(city) asc, city asc limit 1;
        
    SELECT distinct(City),length(city) 
    FROM station 
    ORDER BY 
        length(city) desc, city asc limit 1;

-----
Q10. Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.

<img width="240" alt="q8" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4f101b04-6489-4522-9f9a-a6739ba2b676">

    SELECT city
    FROM station
    WHERE 
        LEFT(city,1) in ('a','e','i','o','u');

-----
Q11. Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

<img width="240" alt="q8" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4f101b04-6489-4522-9f9a-a6739ba2b676">

    SELECT DISTINCT city
    FROM station
    WHERE 
        RIGHT(city,1) in ('a','e','i','o','u');

-----
Q12. Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.

<img width="240" alt="q8" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4f101b04-6489-4522-9f9a-a6739ba2b676">

    SELECT DISTINCT city
    FROM STATION
    WHERE 
        RIGHT(city,1) in ('a','e','i','o','u') AND LEFT(city,1)  in ('a','e','i','o','u');

 -----
 Q13. Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.
 
<img width="240" alt="q8" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4f101b04-6489-4522-9f9a-a6739ba2b676">

    SELECT DISTINCT city
    FROM STATION
    WHERE 
        LEFT(city,1)  NOT IN ('a','e','i','o','u');

 -----
 Q14. Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

<img width="240" alt="q8" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4f101b04-6489-4522-9f9a-a6739ba2b676">

    SELECT DISTINCT city 
    FROM station 
    WHERE right(city,1) NOT in('a','e','i','o','u');

 -----
Q15. Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.

<img width="240" alt="q8" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4f101b04-6489-4522-9f9a-a6739ba2b676">

    SELECT distinct city 
    FROM station 
    WHERE 
        left(city,1) not in('a','e','i','o','u') OR right(city,1) not in('a','e','i','o','u');

 -----
 Q16. Query the list of CITY names from STATION that do not start with vowels and do not end with vowels. Your result cannot contain duplicates.

<img width="240" alt="q8" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/4f101b04-6489-4522-9f9a-a6739ba2b676">

    SELECT DISTINCT city 
    FROM station 
    WHERE 
        left(city,1) not in('a','e','i','o','u') AND right(city,1) not in('a','e','i','o','u');

 -----
Q17. Query the Name of any student in STUDENTS who scored higher than Marks. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.

<img width="231" alt="q17" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/1bdf2430-823c-4625-8d9b-92b0b02f96a9">
    
    SELECT name 
    FROM students 
    WHERE marks > 75 
    ORDER BY right(name,3),id ASC;

 -----    
Q18. Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

<img width="148" alt="q18" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/3946a0f5-9ad0-469c-b334-5671fd3feccb">
    
    SELECT name 
    FROM employee 
    ORDER BY name;

 -----    
 Q19. Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater than per month who have been employees for less than months. Sort your result by ascending employee_id.

 <img width="148" alt="q18" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/3946a0f5-9ad0-469c-b334-5671fd3feccb">

    SELECT name 
    FROM employee 
    WHERE 
         salary > 2000 AND months <10 
    ORDER BY employee_id;

 -----   
Q20. 












