# Lab 1B solutions

1. List the first name, last name, and region of all members from Virginia who either have a work phone or an email address.

```sql
SELECT FirstName, LastName, Region
FROM Members
WHERE Region = 'VA' AND (WorkPhone IS NOT NULL OR EMail IS NOT NULL);
```

2\. List the artist name and web address of any artists who has a web address. Rename the attributes artistname, webaddress as Artist Name, Web Address.

```sql
SELECT ArtistName AS 'Artist Name', WebAddress AS 'Web Address' 
FROM Artists
WHERE WebAddress IS NOT NULL;

```

3\. List the TitleID, TrackNum, and TrackTitle of all tracks with 'Song' at the beginning of the TrackTitle

```sql
SELECT TitleID, TrackNum, TrackTitle
FROM Tracks 
WHERE TrackTitle LIKE 'Song%'
```

4\. Report the total time in minutes of all tracks with length greater than 150.

```sql
SELECT SUM(LengthSeconds/60) AS 'Total time' 
FROM Tracks
WHERE LengthSeconds > 150
```

5\. List the number of tracks, total length in seconds and the average length in seconds of all tracks with titleID 4.

```sql
SELECT COUNT(TitleID) AS 'Number of Tracks', SUM(LengthSeconds) AS 'Total Length', AVG(LengthSeconds) AS 'Average Length'
FROM Tracks
WHERE TitleID = 4;
```

6\. Report the number of male members who are in US.

```sql
SELECT COUNT(Gender) AS 'Number of Males in US'
FROM Members
WHERE Gender = 'M'
GROUP BY Country HAVING Country = 'USA'
```

7\. Report the number of members by state and gender. Sort the results by the region

```sql
SELECT  Gender, COUNT(MemberID) AS 'Number of Members', Region
FROM Members
GROUP BY Gender, Region 
```

8\. For each kind of LeadSource, report the number of artists who came in to the system through that lead source, the earliest EntryDate, and the most recent EntryDate.

```sql
SELECT LeadSource, COUNT(ArtistID) AS 'Number of Artists', MIN(EntryDate) AS 'Earliest Entrydate', MAX(EntryDate) AS 'Latest Entrydate'
FROM Artists
GROUP BY LeadSource
```

9\. Report the TitleID and number of tracks for any TitleID with fewer than nine tracks.

```sql
SELECT TitleID, COUNT(TitleID) AS 'Number of Tracks'
FROM Tracks 
GROUP BY TitleID HAVING Count(TitleID) < 9
```

10\. Report the titleid, average, shortest and longest track length in minutes of all tracks for each titleid with average length greater than 300. Use proper column alias.

```sql
SELECT TitleID, 
    AVG(LengthSeconds/60) AS 'Average', 
    MIN(LengthSeconds/60) AS 'Shortest',
     MAX(LengthSeconds/60) AS 'Longest'
FROM Tracks
GROUP BY TitleID HAVING AVG(LengthSeconds) > 300
```

