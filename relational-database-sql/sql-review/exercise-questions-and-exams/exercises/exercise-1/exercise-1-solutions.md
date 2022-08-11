# Exercise 1 solutions



1. List the Title, UPC and Genre of all CD titles. (Titles table)

```sql
SELECT Title, UPC, Genre 
FROM Titles;
```

2\. List the information of CD(s) produced by the artist whose ArtistID is 2. (Titles table)

```sql
SELECT * 
FROM Titles
WHERE ArtistID = 2;
```

3\. List the First Name, Last Name, HomePhome and Email address of all members. (Members table)

```sql
SELECT FirstName, LastName, HomePhone, Email
FROM Members;

```

4\. List the Member ID of all male members. (Members table)

```sql
SELECT MemberID, Gender
FROM Members
WHERE Gender = 'm'
```

5\. List the Member ID and Country of all members in Canada. (Members table)

```sql
SELECT MemberID, Country 
FROM Members
WHERE Country = 'Canada'
```

{% file src="../../../../../.gitbook/assets/Exercise_01.ipynb" %}
