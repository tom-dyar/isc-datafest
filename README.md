# The InterSystems IRIS DataFest Demo

This is the DataFest Demo, mixing the most exciting IRIS data &amp; analytics features from 2023. 
Best served ice cold!

## Overview

## Tutorial

### Creating the Foreign Tables

Shortcut:
```ObjectScript
do ##class(bdb.sql.InferSchema).CreateForeignSchema("/opt/irisbuild/data/taxi/", { "verbose":1, "targetSchema":"demo_files" })
```

### Working with dbt

Never heard of [dbt](http://getdbt.com)? It's the T in ELT (and if you haven't heard of that either, you're missing out!)


### Building models with IntegratedML

This takes very long!

```SQL
create model distance predicting (trip_distance) from demo_files.yellow_tripdata_2020_05;

train model distance;
```