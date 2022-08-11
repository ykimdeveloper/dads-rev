# Lab 1A solutions

Total points: 10pts (each problem 1 point)

1. List the first name, last name, home phone, and gender of all members from Georgia who either have a home phone in area code 822 or are female

```sql
SELECT FirstName, LastName, HomePhone, Gender 
FROM Members
WHERE Region = 'GA' AND (HomePhone LIKE '822%' or Gender = 'F')
```

2\. List all the information of tracks that do not have an MP3.

```sql
SELECT *
FROM Tracks
WHERE MP3 = '0'
```

3\. List the TitleID, Title, and UPC of any titles whose UPC end with '2'

```sql
SELECT TitleID, Title, UPC 
FROM Titles
WHERE UPC LIKE '%2'
```

4\. If the Base field reports the daily base salary of each salesperson, report the Fristname, Lastname, and weekly (5 work days) salary of each salesperson whose weekly salary is greater than $1000. The format of the results should be: First Name  Last Name  Weekly Salary

```sql
SELECT FirstName AS 'First Name', LastName AS 'Last Name', (Base * 5) AS 'Weekly Salary'
FROM SalesPeople
WHERE (Base * 5) > 1000;
```

5\. Report the average, shortest and longest track length in minutes of all tracks.

```sql
SELECT AVG(LengthSeconds/60) AS 'Average', MIN(LengthSeconds/60) AS 'Shortest', MAX(LengthSeconds/60) AS 'Longest'
FROM Tracks;
```

6\. List the number of track titles that begin with the letter 's' and the average length of these tracks in seconds

```sql
SELECT COUNT(TrackTitle) AS 'Number of Tracks', AVG(LengthSeconds) AS 'Average Length'
FROM Tracks
WHERE TrackTitle LIKE 's%';
```

7\. Report the number of tracks for each TitleID

```sql
SELECT TitleID, COUNT(TitleID) AS 'Number of Tracks'
FROM Tracks
GROUP BY TitleID
```

8\. Report the total time in minutes for each titleid

```sql
SELECT TitleID, SUM(LengthSeconds/60) AS 'Total Time in Minutes'
FROM Tracks
GROUP BY TitleID
```

9\. Report region and the number of members in each region in the members table. Sort the results by the region.

```sql
SELECT Region, COUNT(MemberID) AS 'Number of Members'
FROM Members
GROUP BY Region
```

10\. For any region that has more than one member with an e-mail address, list the region and the number of members with an e-mail address.

```sql
SELECT Region, COUNT(MemberID) AS 'Number of Members'
FROM Members
WHERE Email IS NOT NULL 
GROUP BY Region HAVING COUNT(MemberID) > 1
```

{% file src="../../../../../.gitbook/assets/Questions_01.ipynb" %}
\

{% endfile %}
