# PersistenceTest
Intended to reproduce the issue linked with EFCorePowerTools

Use the following script to create the table
```
create table test.location
(
    year                   smallint              not null,
    inst_id                int                   not null,
    latitude               numeric(9, 6)         not null,
    longitude              numeric(9, 6)         not null,
    geolocation            geometry(Point, 4326) not null,
    primary key (year, inst_id)
)
create index location_ix on test.location using gist (geolocation);
```