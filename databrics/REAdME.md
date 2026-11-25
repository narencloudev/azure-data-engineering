DataBricks built upon apache spark

1. unity catalog & Unity metastore
  - Unity metastore means infoemation about catalog, schemas, tables etc put everything n metastore
  -  centralize store
  -  Unity catalog created inside metastore
  -  catalog same as database
  -  unity metastore
  -  > external location
  -   > catalog > schema = volumes, views, tables, functions, models
  - > Clean room
unity meta store oparated by admin
unity catalog is under our control

2. Volumes
   - stored in s3 or azure
   - access those files very easy  syntax select * from folder name
   - volumes 2 levels Managed Volumes(Unity catalog maintain) and External volumes (configure from external sources)

3. Databrics Architecture
  - control
  - compute

4. Delta Tables
  - Open Table Format
  - delta tables created by  delta lake
  - acid rollback schema on write
  - paraquet, delta_log, json,

5. Lakeflow Connect
  - pull the data from different resource(s3, postgredatabase, kafka) to databrics
  - database connectors
  - sql database > incremetal loading< databrics need lot of coding
  - buit in databrics connecting change data capture or query based capture will use
  - different conectors file conectors(pyspark code is best for fetch the data), saas conectors

6. AutoLoader
   - 































  - 
