#rake db:migrate

When you run db:migrate for the first time, a table called schema_migrations is created.
This table stores the version number of each migration (the number that prefaces the migration name).
When you run db:migrate subsequently, only migrations which have not been run are run.
Running db:migrate also updates db/schema.rb file to match the structure of your database.
