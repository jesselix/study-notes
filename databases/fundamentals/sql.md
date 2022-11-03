# SQL

## Classifications
| SQL Classifications | Commands |
| --- | --- |
| DQL | select |
| DDL | create, alter, drop |
| DML | insert, update, delete |
| DCL | grant, revoke |
| CCL | declare cursor, fetch into, update where current |
| TPL | begin transaction, commit, rollback |


## CRUD
Create, Read, Update, and Delete (CRUD) are the four basic operations of persistent storage.

I prefer the abbreviation RCUD to CRUD because "Read" is the only operation which doesn't affect table.

| CRUD | SQL | HTTP methods | RESTful API Examples |
| --- | --- | --- | --- |
| Read | select | get | /api/movie/{id} |
| Create | insert | post | /api/movie |
| Update | update | put | /api/movie |
| Delete | delete | delete | /api/movie/{id} |

## SQL Query Optimization
