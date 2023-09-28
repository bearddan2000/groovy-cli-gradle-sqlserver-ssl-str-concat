# groovy-cli-gradle-sqlserver-ssl-str-concat

## Description
Creates a small database table
called `dog`. This table, `dog`, has been normalized to 3NF.
Two new tables have been added, `breedLookup` and `colorLookup`.
Creates a new table `dog_expanded` that joins
`dog`, `breedLookup` and `colorLookup`. Added clustered indexes on
`dog`.breedId and `dog`.colorId. Turned `dog_expanded` into a view. Using
a RECURSIVE common table expression with the aggregate function
COUNT, create a new view `breed_count`. Create a new view `dog_final` based on `breed_count` adding concated color column. All output normally
seen in a terminal will be in `groovy-srv/log` which will dump to the screen. The project may seem to hang but the logs from the container must be written to the project this can take up to 3 min.

Sql server uses self-signed ssl.

## Tech stack
- groovy
- gradle
  - log4j
  - ms sql driver

## Docker stack
- alpine:edge
- gradle:jdk11
- mcr.microsoft.com/mssql/server:2017-latest-ubuntu

## To run
`sudo ./install.sh -u`
Creates groovy-srv/log

## To stop
`sudo ./install.sh -d`
Removes groovy-srv/log

## For help
`sudo ./install.sh -h`

## Credit
https://github.com/htorun/dbtableprinter
