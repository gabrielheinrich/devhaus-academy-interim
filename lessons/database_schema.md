# Relational Databases and SQL

## Resources

[SQL Island Learning Game](https://sql-island.informatik.uni-kl.de/)
[SQL Murder Mystery Learning Game](https://mystery.knightlab.com/)

[Creating column with auto incrementation](https://www.postgresqltutorial.com/postgresql-serial/) (usefull for ids/primary keys)
[SQL Fiddle for testing CREATE, INSERT and SELECT statements](https://www.db-fiddle.com/)

[Slides](https://docs.google.com/presentation/d/1mdt7Na6kKvD_YFjjv5wVqTeJyFQAxM41AuB5_oZOtgk/edit?usp=sharing)

## Types of databases

#### SQL Databases

- Postgres
- MySQL
- SQLite
- MariaDB

#### NoSQL Databases

- MongoDB
- Firestore
- DynamoDB

#### Other

- Redis (Key Value Store for Caching)
- Cassandra (Column Store)
- noe4j (Graph)
- Elastic Search

## SQL Snippets

```sql
CREATE TABLE events (
  id integer PRIMARY KEY AUTOINCREMENT,
  title varchar(255) UNIQUE NOT NULL,
  date datetime NOT NULL,
  location varchar(255),
  details text
);
```

```sql
INSERT INTO events (title, date, location, details) VALUES (
    'Pair Programming',
    '05/16/2020 15:00',
    'Zoom Room',
    'Topic: Object Oriented Programming'
  );
```

```sql
-- getting all columns from table
SELECT * FROM events;

-- getting specific columns from table
SELECT id, date, location FROM events;

-- order, limit and paginate result
SELECT * FROM events
ORDER BY date DESC
LIMIT 10 offset 30;

-- retrieve specific data
SELECT * FROM events WHERE id = 42;
-- % is a wildcard and means 0 or many characters
-- the where statement limits the results to those
-- whose details contain the substring Javascript
SELECT * FROM events WHERE details LIKE "%Javascript%"
```

```sql
UPDATE events SET title = 'Kata Session' WHERE id = 42;
```

```sql
DELETE FROM events WHERE id = 42;
```

```sql
CREATE TABLE event_attendees (
  event_id INTEGER REFERENCES events(id),
  attendee_id INTEGER REFERENCES users(id),
  PRIMARY KEY(event_id, attendee_id)
)
```
--- 
## Data Modeling Exercises


### Botanical Gardens

A botanical garden has a name, an adress, a city it is located in and an optional telephone number. A botanical garden can be home to many plants. Plants can grow in different botanical gardens. Every botanical garden is home to a special type of buttefly. There can be no, 1 or more butterflies of the same type in a botanical garden. The information about the butterfly is its unique latin name, birthday, name, gender and coloration.

### Vineyards

Wine-growing regions, e.g. Saale-Unstrut, Rheinhessen, Pfalz, are identified by their name, a description is optional. A vineyard is located in one region. It has a unique name, an adress, an establishement date and an owner. It optionally has a website and a phone number

A grape variety (type of grape), e.g. Riesling, Spätburgunder, is identified by its name. They too have an optional description. A wine is made from one variety. A variety can be used in multiple wines.

Wines are identified by their brand name. A wine is made at one vineyard exclusively. A wine can have multiple vintages (Jahrgang), that are identified by the year. The have an optional price, rating and alcohol content.

### Spark 

Create a database schema for a multi user spark application. Think of necessary tables for features like login, adding multiple tags to notes, note types (checklist, text, notification) or note collections.

### Additional Execises
- add a valid database state
- write a database state that violates the database schema
- write an approriate `CREATE TABLE` statement