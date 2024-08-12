# SQL_ACTIVITIES
SQL Review: Simple SELECT Queries

1. List all the Canadian cities and their populations
SELECT CITY, POPULATION FROM north_american_cities
WHERE COUNTRY = "Canada"; 

2. Order all the cities in the United States by their latitude from north to south 
SELECT CITY, LATITUDE FROM north_american_cities
WHERE COUNTRY = "United States"
ORDER BY LATITUDE DESC;

3. List all the cities west of Chicago, ordered from west to east
SELECT CITY, LONGITUDE FROM north_american_cities
WHERE LONGITUDE < -87.629798
ORDER BY LONGITUDE ASC;

4. List the two largest cities in Mexico (by population)
SELECT CITY, POPULATION FROM north_american_cities
WHERE COUNTRY = "Mexico"
ORDER BY POPULATION DESC
LIMIT 2;

5. List the third and fourth largest cities (by population) in the United States and their population
SELECT CITY, POPULATION FROM north_american_cities
WHERE COUNTRY = "United States"
ORDER BY POPULATION DESC
LIMIT 2 OFFSET 2;
--------------------------------------------------------

SQL Lesson 12: Order of execution of a Query

1. Find the number of movies each director has directed
SELECT director, COUNT(id) as Num_movies_directed
FROM movies
GROUP BY director;

2. Find the total domestic and international sales that can be attributed to each director
SELECT director, SUM(Domestic_sales+International_sales) as sum_sales_director
FROM Movies
INNER JOIN Boxoffice
    ON Movies.Id = Boxoffice.Movie_Id
    GROUP BY director;


--------------------------------------------------------
1. A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit all records' details.

SELECT * FROM mailing_list;

2. White hat hacker has sent SQLPD exposed members' details of a shady site connected to various persons of interest. Please submit all members' details.

SELECT * FROM members;

3. A mailing list of an illegal online services was sent to the SQLP hot-line. Please submit all entries family names, emails and given names' details.

SELECT FamilyName, Email, GivenName FROM mailing_list;

4. White hat hacker has sent SQLP exposed members' details of a shady site connected to various persons of interest. Please submit all members names, password hashes and usernames' details

SELECT Name, PasswordHash, Username FROM members;

5. White hat hacker has sent SQLPD exposed subscribers' details of a shady site connected to various persons of interest. Please submit all subscribers subscription dates' details. Please make sure there are no duplicates.

SELECT DISTINCT SubscriptionDate FROM subscribers;

6. White hat hacker has sent SQLPD exposed subscribers' details of a shady site connected to various persons of interest. Please submit all subscribers' details sorted by mailing addresses in ascending order.

SELECT * FROM subscribers ORDER BY MailingAddress ASC;

7. A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit all records' details sorted by number of password changes in descending order.

SELECT * FROM mailing_list ORDER BY PasswordChanges DESC;

8. An illegal site's servers were seized in a recent operation. Please submit all users given names and last access times' details sorted by last access times in descending order. Please make sure there are no duplicates.

SELECT DISTINCT GivenName, LastAccess FROM users ORDER BY LastAccess DESC;

9. An illegal site's servers were seized in a recent operation. Please submit all users emails and last access times' details sorted by emails in descending order and then by last access times in ascending order.

SELECT Email, LastAccess
FROM users
ORDER BY Email DESC, LastAccess ASC;

10. An illegal site's servers were seized in a recent operation. Please submit the top 5 users' details when sorted by email addresses in ascending order and then by given names in ascending order.

SELECT * FROM users ORDER BY EmailAddress ASC, GivenNAME ASC LIMIT 5;




