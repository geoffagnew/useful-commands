# psql commands and basics

### Postgres login commands
If you are logged into the same computer that Postgres is running on you can use the following psql login command, specifying the username (myuser):

`psql -U myuser`

### Export a db with pg_dump
`pg_dump myDBName > name_of_file_to_dump_to.sql`
