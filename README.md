# The InterSystems IRIS DataFest Demo

This is the DataFest Demo, mixing the most exciting IRIS data &amp; analytics features from 2023. 
Best served ice cold!

## Overview

## Tutorial

### Building the image

```Shell
docker build . --tag iris-datafest
docker run -d --name iris-datafest -p 41773:1972 -p 42773:52773 iris-datafest
```

or 

```Shell
docker-compose up
```

To log in to the container, use `docker exec -it <container-name> bash`, or use your favourite SQL tool to connect through port 41773.

### Creating the Foreign Tables

Shortcut:
```ObjectScript
do ##class(bdb.sql.InferSchema).CreateForeignTables("/opt/irisbuild/data/taxi/", { "verbose":1, "targetSchema":"demo_files" })
```

### Working with dbt

Never heard of [dbt](http://getdbt.com)? It's the T in ELT (and if you haven't heard of that either, you're missing out!)


### Building models with IntegratedML

This takes very long!

```SQL
SET ML CONFIGURATION %H2O;

CREATE MODEL distance PREDICTING (trip_distance) FROM demo_files.yellow_tripdata_2020_05;

TRAIN MODEL distance;
```