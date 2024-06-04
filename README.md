'''sql
# SQL_assessment 
<h2>Question 1:Add two more movies of your choosing to the table. </h2>
  mysql> INSERT INTO MOVIES ( Title,Runtime,Genre,ImdbScore,Rating) VALUES ('Frozen',102,'A
nimation', 7.4,'PG');
Query OK, 1 row affected (0.00 sec)

   mysql> INSERT INTO MOVIES ( Title,Runtime,Genre,ImdbScore,Rating) VALUES ('Paid in Full',
132,'Crime',7.0,'R');
Query OK, 1 row affected (0.01 sec)

<h2> Question 2:Create a query to find all movies in the Sci-Fi genre.</h2>
mysql> SELECT Genre,Title
    -> FROM MOVIES
    -> WHERE Genre='Sci-Fi';
+--------+-------------------+
| Genre  | Title             |
+--------+-------------------+
| Sci-Fi | Howard the Duck   |
| Sci-Fi | Starship Troopers |
+--------+-------------------+

<h2>Question 3: Create a query to find all films that scored at least a 6.5 on IMDB </h2>

mysql> SELECT *
    -> FROM MOVIES
    -> WHERE ImdbScore >= 6.5;
+-------------------+---------+-------------+-----------+--------+
| Title             | Runtime | Genre       | ImdbScore | Rating |
+-------------------+---------+-------------+-----------+--------+
| Frozen            |     102 | Animation   |       7.4 | PG     |
| Monsters Inc.     |      92 | Animation   |       8.1 | G      |
| Paid in Full      |     132 | Crime       |       7.0 | R      |
| Spaceballs        |      96 | Comedy      |       7.1 | PG     |
| Starship Troopers |     129 | Sci-Fi      |       7.2 | PG-13  |
| Waltz With Bashir |      90 | Documentary |       8.0 | R      |
+-------------------+---------+-------------+-----------+--------+


<h2>Question 4:For parents who have young kids, but who don't want to sit through long children's movies, create a query to find all of the movies rated G or PG that are less than 100 minutes long.</h2>

mysql> SELECT Title
    -> FROM MOVIES
    -> WHERE Rating IN ('G','PG') AND Runtime <100;
+---------------+
| Title         |
+---------------+
| Monsters Inc. |
| Spaceballs    |
+---------------+


<h2>Question 5:Create a query to show the average runtimes of movies scoring below a 7.5 on imdb, grouped by their respective genres. </h2>

mysql> SELECT Genre,AVG(Runtime) AS AvgRuntime
    -> FROM MOVIES
    -> WHERE ImdbScore < 7.5
    -> GROUP BY GENRE;
+-----------+------------+
| Genre     | AvgRuntime |
+-----------+------------+
| Animation |   102.0000 |
| Sci-Fi    |   119.5000 |
| Horror    |    83.0000 |
| Crime     |   132.0000 |
| Comedy    |    96.0000 |
+-----------+------------+
5 rows in set (0.03 sec)


<h2>Question 6:There's been a data entry mistake; Starship Troopers is actually rated R, not PG-13. Create a query that finds the movie by its title and changes its rating to R. </h2>

UPDATE MOVIES SET Title = 'R' WHERE Rating = 'PG-13';
Query OK, 1 row affected (0.04 sec)
Rows matched: 1  Changed: 1  Warnings: 0

<h2>Question 7: Show the ID number and rating of all of the Horror and Documentary movies in the database. Do this in only one query or two queries.</h2>
id number?

<h2>Question 8:This time let's find the average, maximum, and minimum IMDB score for movies of each rating. </h2>


<h2>Question 9:That last query isn't very informative for ratings that only have 1 entry. Use a HAVING COUNT(*) > 1 clause to only show ratings with multiple movies showing. </h2>

<h2>Question 10:Make the movie list more child-friendly. Delete all entries that have a rating of R. Remember to record your queries in a README.md file </h2>

<h2>Question 11:Delete the Movies Table </h2>

<h2>Question 12:Delete the Database </h2>
DROP TABLE MOVIES;

