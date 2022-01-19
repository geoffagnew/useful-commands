# psql commands and basics

### Postgres login commands
If you are logged into the same computer that Postgres is running on you can use the following psql login command, specifying the username (myuser):

`psql -U myuser`

#### Common psql commands
List DB's

`\l`

Select a DB

`\c database_name`

List tables in DB

`\dt`

Select all data in table

`SELECT * FROM table_name`

Quit psql

`\q`


### Export a db with pg_dump
`pg_dump --no-owner my_db_name > name_of_file_to_dump_to.sql`

Use the `--no-owner` flag to prevent output commands that set ownership of objects to match the original database. This option is only meaningful for the plain-text format. For the archive formats, you can specify the option when you call `pg_restore`.

For example, if the db owner from my export location is `geoff` but the db owner at my import location is `geoffrey`, `--no-owner` lets the import succeed because it doesn't try to set ownership of objects to `geoff`.

### Import a db
For importing to my local postgres database:

`psql -U myuser my_db_name < name_of_file_to_import.sql`
