# HackerRank-SQL

# SQL Easy Challenges

Q1. Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA. 

<img width="292" alt="easy1" src="https://github.com/Maidira/HackerRank-SQL/assets/60576485/084f7a1e-b6c8-494d-a666-ef9185e670df">
( *** )

    SELECT *
    FROM city 
    WHERE 
        population > 100000 AND countrycode = 'USA';
