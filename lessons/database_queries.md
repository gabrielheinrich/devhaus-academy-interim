# Databases: Creating Tables, Inserting and selecting values

## Ressources

- [SQL Wildcards](https://www.w3schools.com/sql/sql_wildcards.asp)

## Setup

Create a `docker-compose.yml` with the following contents:

```yml
version: "3.7"

services:
  pgadmin:
    image: dpage/pgadmin4

    links:
      - postgres:postgres

    ports:
      - "9001:80"

    environment:
      PGADMIN_DEFAULT_EMAIL: spark@devhausleipzig.de
      PGADMIN_DEFAULT_PASSWORD: spark

  postgres:
    image: postgres:13.0

    environment:
      POSTGRES_DB: spark
      POSTGRES_USER: spark
      POSTGRES_PASSWORD: spark

    volumes:
      - ./postgres/data:/var/lib/postgresql/data:rw

    ports:
      - "5432:5432/tcp"
```

Open localhost:9001 in your browser.

1. Create a new server
2. 
When in doubt:
- Port forwarded?
- Double instead of single Quotes?
- Semicolon at end of statement if multiple statements in one query (creating and inserting at the same time)
- SERIAL might not work in db fiddle because you need to create a so called SEQUENCE. In pgAdmin you don’t have to worry about that and use the SERIAL keyword without any configuration. (Chapter 4: IDs http://users.informatik.uni-halle.de/~brass/dbp19/print/p1_tabdf.pdf)

## Exercise

Create tables that make it possible to tag notes. A note can have multiple tags and the same tag can be apllied to different notes.

SOLUTION 
```sql
DROP TABLE IF EXISTS notes, tags, note_tags;

CREATE TABLE notes(
	note_id SERIAL PRIMARY KEY,
	title varchar(70) NOT NULL,
	author integer REFERENCES users(user_id) NOT NULL
);

CREATE TABLE tags (
  tag_id serial primary key,
  tag_name varchar(25)
);

CREATE TABLE note_tags (
  tag_id integer REFERENCES tags(tag_id),
  note_id integer REFERENCES notes(note_id),
  PRIMARY KEY (tag_id, note_id)
);

INSERT INTO notes values(default, '1 note', 1);
INSERT INTO notes values(default, 'another note', 1);
INSERT INTO notes values(default, 'second users note', 2);
INSERT INTO notes values(default, '222', 2);
INSERT INTO notes values(default, '3 times a charm', 3);
INSERT INTO notes values(default, '3 != 4', 3);
 
INSERT INTO tags VALUES (DEFAULT, 'job');
INSERT INTO tags VALUES (DEFAULT, 'personal');
 
INSERT INTO note_tags VALUES (1, 1);
INSERT INTO note_tags VALUES (1, 2);
INSERT INTO note_tags VALUES (1, 4);
INSERT INTO note_tags VALUES (2, 1);
INSERT INTO note_tags VALUES (2, 2);
INSERT INTO note_tags VALUES (2, 3);

SELECT note_tags.note_id, note_tags.tag_id, title, tag_name
FROM notes, tags, note_tags
WHERE notes.note_id = note_tags.note_id
AND tags.tag_id = note_tags.tag_id;
```


SNIPPETS 

```sql
-- Creating a Table

CREATE TABLE IF NOT EXISTS notes (
    id SERIAL PRIMARY KEY,
    title VARCHAR NOT NULL,
    content VARCHAR,
    collection VARCHAR NOT NULL,
    createdBy VARCHAR,
    createdAt TIMESTAMPTZ,
    updatedAt TIMESTAMPTZ,
    deletedAt TIMESTAMPTZ
  )

CREATE TABLE IF NOT EXISTS users (
    user_id SERIAL PRIMARY KEY,
    name VARCHAR NOT NULL
  );


CREATE TABLE IF NOT EXISTS notes (
    id SERIAL PRIMARY KEY,
    title VARCHAR NOT NULL,
	createdby integer REFERENCES users(user_id)
  );

-- Adding values to database:
INSERT INTO notes (title, content, id)
VALUES ('some note', 'somethingsomething', DEFAULT);

-- Shorthand (column values must be in correct order or table!)
INSERT INTO notes VALUES (DEFAULT, 'some note', 'somethingsomething');

-- Dropping (deleting a table)
DROP TABLE notes;

-- Dummy Data
insert into notes values(default, '1 note', 1);
insert into notes values(default, 'another note', 1);
insert into notes values(default, 'second users note', 2);
insert into notes values(default, '222', 2);
insert into notes values(default, '3 times a charm', 3);
insert into notes values(default, '3 != 4', 3);
select * from notes;

-- Querying related data
SELECT *
FROM notes, users
WHERE notes.createdby = users.user_id;
```