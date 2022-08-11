# Create Table and Insert Statements

### Show all tables

Postgres SQL

```sql
SELECT table_name FROM information_schema.tables WHERE table_schema='public'
```

MS SQL

```sql
SELECT
  *
FROM
  SYSOBJECTS
WHERE
  xtype = 'U';
GO
```





### Create tables

Create a table named departments with two columns (department and division) with a primary key constraint for the department column.

```sql
create table departments (
    department varchar(100),
    division varchar(100),
    primary key (department)
  );
```

{% hint style="info" %}
The **PRIMARY KEY constraint** uniquely identifies each record in a table. Primary key constraints prevents duplicates. Primary keys must contain UNIQUE values, and cannot contain NULL values. A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns (fields).&#x20;
{% endhint %}







