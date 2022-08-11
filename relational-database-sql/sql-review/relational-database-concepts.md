# Relational database concepts

### How does relational databases store data?

Tables!

For example of a students table:

| ID | Name    | CIN       | Grade | LastModified     |
| -- | ------- | --------- | ----- | ---------------- |
| 1  | Eric    | 12345678  | 93    | 2016-09-30 12:59 |
| 2  | Michael | 32145678  | 96    | 2016-08-22 13:10 |
| 3  | Mark    | 555555555 | 90    | 2016-08-12 18:30 |
| 4  | Pierre  | 87654321  | 100   | 2016-08-03 19:03 |

By looking at table, users will be able to tell what grade a person get, CIN of a user, and when is the last modified date for the user.

* Candidate key
  * Unique identifier per record
  * Can have multiple candidate key
* Primary key
  * Only candidate key(s) as primary key
  * Only one primary key per table

Now is the time to introduce some of the terminology:

* Table (Relation)
  * like name of the table (students)
* Record (table row or tuple)
  * Each row is a record
* Field (column or attribute)
  * Each column is a field

#### Data types

Determine what type of data a column will store.

A few examples of data types:

* Integer
  * like `ID`
* String(Text)
  * like `Name`
* Date/time
  * like `LastModified`
* Boolean (true or false)
  * Maybe we can add more field like Passing

#### Schema

The "definition" of a table:

* Names of table
* Attributes and attribute types
* Constraints on the table
* Dependencies between tables

Above all summarizes the introduction to database, from now we will be setting up environment on your computer and hopefully get you used to the environment.



An example on how SQL defines schema:

```sql
CREATE TABLE `students` (
  `ID` mediumint(8) unsigned NOT NULL DEFAULT 0,
  `Name` varchar(200) unsigned NOT NULL DEFAULT 0,
  `CIN` varchar(8) NOT NULL DEFAULT '',
  `Grade` mediumint(8) unsigned NOT NULL DEFAULT 0,
  KEY `ID` (`ID`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci;
```

Running above sql query will create a students table.

\
\
