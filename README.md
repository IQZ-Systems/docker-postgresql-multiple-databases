# Using multiple databases with the official PostgreSQL Docker image

The [official recommendation](https://hub.docker.com/_/postgres/) for creating
multiple databases is as follows:

_If you would like to do additional initialization in an image derived from
this one, add one or more \`_.sql`,`_.sql.gz`, or`_.sh`scripts under`/docker-entrypoint-initdb.d`(creating the directory if necessary). After the
entrypoint calls`initdb`to create the default`postgres`user and database,
it will run any`_.sql`files and source any`_.sh\` scripts found in that
directory to do further initialization before starting the service.\*

This directory contains a script to create multiple databases using that
mechanism.

## Usage

Open `docker-compose.yml` file and edit the `POSTGRES_MULTIPLE_DATABASES` environment variable with a list of db names you'd like to be created in the postgres container. The db names should be comma(`,`) separated.

Save the file and simpy run:

    docker-compose up

to get the container up and running. Your databases would automatically be created and will be exposed by default on port `5432`.

# Credits

Thanks to [@mrts][original-author-link] for the inspiration and [original script][original-repo-url].

[original-author-link]: https://github.com/mrts

[original-repo-url]: https://github.com/mrts/docker-postgresql-multiple-databases
