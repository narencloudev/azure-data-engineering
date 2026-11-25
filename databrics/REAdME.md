Databricks built upon apache spark

unity catalog & Unity metastore
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

Volumes
   - stored in s3 or azure
   - access those files very easy  syntax select * from folder name
   - volumes 2 levels Managed Volumes(Unity catalog maintain) and External volumes (configure from external sources)

Databrics Architecture
  - control
  - compute
