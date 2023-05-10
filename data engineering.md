# 1. Design and implement data storage
## Design data storage structure
- file types for storage 
  - Azure blob: scalble object store for text and binariry data 
  - Azure file: file share for on premise deplyoments - network file system
  - Azeure queue: message store for massenging application
  - Table service:
- Type of analytical queries
  - Structure data: RDBMS
  - Non Strucutred data: Audio, image , text
    - key value
    - document databases
    - graph databases
    - column databases
- Design for efficient query
  -  source--> ingest--> prepare --> analyse --> consume
-  Design for data pruning: using dynamic partition pruning we can save lot of time while proccessing big data queries. DFD (dynamic file pruning)
-  Design folder and organisational structure
  -  Classify your data 
    -   structure data: DB tables
    -   semi structure data: mongo db (XML, JSON, YAML)
    -   unstrucure data: Media, audio
-  Design a data distribution strategy
  - Hash distributed: Table size > 2GB, Frequent updates
  - Round-robin: for even distribution and no pattern for SQL pool and azure synopsis
- Design a data archive solution
  -  Key concept: Multiple copies, tested and automated
  -  We can use native azute service or third party service for backup (azure blob other other data store)
  -  
## Design a partition strategy
- Overview
  - Reason for partitions: scalability, Performance, Security, operational flexibility(min cost, monitor), Match data pattern(media f=goes in blob and files into tables),availibility (no failure).
- Partitioning strategies
  - Horizontal (sharding): DB table splitby rows. say based on group of alphabetical values e.g. a-m into table1 and n-z into table 2
  - Vertical: spliting columns across machine. Hbase , cassandra
  - Functional:based on logical fucntion like HR, operation, admin
## Design and serving layer
  - Design analytical store: using Azure data factory for data dintegration service, pipeline service and platform. All types of data can be processed using data factory
  - Design metastore: Using azure databricks solution provides:
    - Control plane:
    - Data plane: 
# 2. Design and develop data proccessing
## Overview
- Ingest and transform data
- Design and develop a batch processing solution
- Design and develop a stream processing solution
## Ingest and transform data
- Transform data by using Apache spark, data factory, data bricks and more
  - 
