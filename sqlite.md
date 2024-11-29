# SQLite
Here I joined all the knowledge I acquired and judged that it is important to know how to use and manipulate SQLite databases.   
[SQLite](https://www.sqlite.org/) is one of the smallest, easiest to use and greatest relational database in the world in my opinion.  
For this cheatsheet I am presuming you already downloaded, installed and added the sqlite3 bin to the PATH environment var.

## At Command Line:  

### Create a new or access an existing database and enter sqlite shell: 
```sh
$ sqlite3 db_name.db
```

### Create EMPTY database only and exit (building the correct db structure) 
```sh
$ sqlite3 your_db_name.db "VACUUM;"
```

### Import data or dump to database
```sh
$ sqlite3 your_db_name.db -init dump.sql
```

### Execute SQL statement in one line on terminal, output the result and exit, example:
```sh
$ sqlite3 your_db_name.db "select * from users;" ".exit"
```
or, if you want in CSV format:
```sh
$ sqlite3 your_db_name.db ".mode csv" "select * from users;" ".exit"
```

## At SQLite shell
_To enter in SQLite shell, just type sqlite3 on terminal and press enter/return. Again: make sure SQLLite3 executable file was added to the PATH var._
These are the most common "commands" (called dot-commands) you can use in its shell:

|   |   |
|---|---|
|.databases|list names and files of attached databases|
|.tables|will show all your db tables|
|.schema _table_name_|will show the "create table _table_name_" structure, like "DESCRIBE _table_name_"|
|.open _your_db_name.db_|open a database if you just enter in sqlite shell|
|.header on/off|enable/disable the column names when output|
|.mode _name_|change the output mode: list (default), csv, column, box, table, or markdown|
|.output _path/filename.ext_|will output the next statement into the _path/filename.ext_|
|.exit|exit the sqlite shell|
|.indices _table_name_|show table indexes|
|.dump _?table_name_|dump all the db, or the specified table. Used with .output|
|.read _your_sql.sql_|Read sql file, usefull tu import data|


---
### Data you can use to test:

```sql
CREATE TABLE users (
   id INTEGER PRIMARY KEY, 
   name CHAR(255) NOT NULL,
   email CHAR(60) NOT NULL UNIQUE,
   document_number CHAR(11) NOT NULL,
   date_of_birth DATE NOT NULL,
   bio TEXT,
   salary REAL DEFAULT 0.00,
   created_at DATETIME NOT NULL DEFAULT current_timestamp,
   updated_at DATETIME NOT NULL DEFAULT current_timestamp
);

CREATE INDEX document_number_index on users (document_number);
CREATE UNIQUE INDEX IF NOT EXISTS email_unique ON users(email);

INSERT INTO users (name, email, document_number, date_of_birth, bio, salary) VALUES ('luke', 'luke@luke.com', '11111111111', '1996-12-23', 'web dev', 10000.0);
INSERT INTO users (name, email, document_number, date_of_birth, bio, salary) VALUES ('john', 'john@john.com', '22222222222', '1985-04-15', 'programmer', 5000.50);
INSERT INTO users (name, email, document_number, date_of_birth, bio, salary) VALUES ('mary', 'mary@mary.com', '33333333333', '1991-10-03', 'teacher', 8123.45);

```
**Tips**:
- Today `AUTOINCREMENT` is automatic for `column_name integer primary key`, so no need to let it explicit like `id INTEGER PRIMARY KEY AUTOINCREMENT`
- execute the statement: `PRAGMA table_info(_table_name_);` to get a descriptive structure of the table, very like the `.schema _table_name_` or `DESCRIBE` behavior
- if you want to simulate `ON UPDATE CURRENT_TIMESTAMP` like other databases, commonly used in `updated_at` field, you can use trigger like:
```sql
CREATE TRIGGER tg_table_name_updated_at 
AFTER UPDATE 
ON table_name FOR EACH ROW 
BEGIN 
  UPDATE table_name SET updated_at = current_timestamp 
    WHERE id = old.id; 
END;
```
