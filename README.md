# Investigating the 2021 Texas Power Crisis

## Purpose:

In this assignment for UCSB's Environmental Data Science Geospatial Analysis class, we are investigating the population affected by the devastating 2021 blackout in Texas. We are practicing and demonstrating our skills in using data from multiple sources, appropriately preparing the data for spatial analyses, manipulating rasters, and building data explorations of socioeconomic impacts. 

## Description:

We are using **NASA VIIRS** data to obtain information about the blackout by analyzing changes in the light at night indices. Additionally, we are correcting this data using **OpenStreetMap roads** to exclude areas near highways from the analysis, as reduced traffic patterns may yield false positives for reduced power during the blackout. Next, to get the number of households affected by the blackout, we are using **OpenStreetMap house** data. Lastly, we will use the U.S. Census Bureau’s American Community Survey, **ACS** data, to obtain area-level socioeconomic data and identify patterns in the socioeconomic indices of folks who lost power, specifically income. 

## Data access:

### NASA VIIRS

Note: this data is in my .gitignore, so it is not available in the repository. However, it was downloaded from Level-1 and Atmospheric Archive & Distribution System Distributed Active Archive Center (LAADS DAAC) from NASA, and we are using the dates with less cloud cover (2021-02-07 and 2021-02-16) and the spatial tiles of Houston (h08v05 and h08v06). 

### OpenStreetMap roads

Note: this data is in my .gitignore, so it is not available in the repository. This data was obtained using `Geofabrik`, which extracts data from OpenStreetMap. It contains data from the Houston Metropolitan area. 

### OpenStreetMap houses

Note: this data is in my .gitignore, so it is not available in the repository. This data was obtained using `Geofabrik`, which extracts data from OpenStreetMap. It contains data from the Houston Metropolitan area. 

### ACS

Note: this data is in my .gitignore, so it is not available in the repository. This is 2019 Census data from the U.S. Census Bureau’s American Community Survey, filtered in the workflow for specific layers, like the geographic data layer `ACS_2019_5YR_TRACT_48_TEXAS` and the income data layer `INCOME_X19` and the metadata layer. 


## Authors and contributors

I am the sole author and contributor to this homework assignment. The assignment was written by Ruth Oliver and Annie Adams.

## References

### Data citations

### NASA VIIRS

NASA VIIRS (Visible Infrared Imaging Radiometer Suite) Data 2021. Distributed through NASA Level-1 and Atmospheric Archive & Distribution System Distributed Active Archive Center (LAADS DAAC). https://ladsweb.modaps.eosdis.nasa.gov/

### OpenStreetMap

This OpenStreetMap data used in this project is made available under the Open Database License: http://opendatacommons.org/licenses/odbl/1.0/. Any rights in individual contents of the database are licensed under the Database Contents License: http://opendatacommons.org/licenses/dbcl/1.0/

### ACS

U.S. Census Bureau, 2019 Census. Accessed via <https://www.census.gov/programs-surveys/acs>. 


# Repository structure

```
├── data
│   ├── ACS_2019_5YR_TRACT_48_TEXAS.gdb
│   │   ├── a00000001.gdbindexes
│   │   ├── a00000001.gdbtable
│   │   ├── a00000001.gdbtablx
│   │   ├── a00000001.TablesByName.atx
│   │   ├── a00000002.gdbtable
│   │   ├── a00000002.gdbtablx
│   │   ├── a00000003.gdbindexes
│   │   ├── a00000003.gdbtable
│   │   ├── a00000003.gdbtablx
│   │   ├── a00000004.CatItemsByPhysicalName.atx
│   │   ├── a00000004.CatItemsByType.atx
│   │   ├── a00000004.FDO_UUID.atx
│   │   ├── a00000004.freelist
│   │   ├── a00000004.gdbindexes
│   │   ├── a00000004.gdbtable
│   │   ├── a00000004.gdbtablx
│   │   ├── a00000004.spx
│   │   ├── a00000005.CatItemTypesByName.atx
│   │   ├── a00000005.CatItemTypesByParentTypeID.atx
│   │   ├── a00000005.CatItemTypesByUUID.atx
│   │   ├── a00000005.gdbindexes
│   │   ├── a00000005.gdbtable
│   │   ├── a00000005.gdbtablx
│   │   ├── a00000006.CatRelsByDestinationID.atx
│   │   ├── a00000006.CatRelsByOriginID.atx
│   │   ├── a00000006.CatRelsByType.atx
│   │   ├── a00000006.FDO_UUID.atx
│   │   ├── a00000006.gdbindexes
│   │   ├── a00000006.gdbtable
│   │   ├── a00000006.gdbtablx
│   │   ├── a00000007.CatRelTypesByBackwardLabel.atx
│   │   ├── a00000007.CatRelTypesByDestItemTypeID.atx
│   │   ├── a00000007.CatRelTypesByForwardLabel.atx
│   │   ├── a00000007.CatRelTypesByName.atx
│   │   ├── a00000007.CatRelTypesByOriginItemTypeID.atx
│   │   ├── a00000007.CatRelTypesByUUID.atx
│   │   ├── a00000007.gdbindexes
│   │   ├── a00000007.gdbtable
│   │   ├── a00000007.gdbtablx
│   │   ├── a00000009.gdbindexes
│   │   ├── a00000009.gdbtable
│   │   ├── a00000009.gdbtablx
│   │   ├── a0000000a.gdbindexes
│   │   ├── a0000000a.gdbtable
│   │   ├── a0000000a.gdbtablx
│   │   ├── a0000000b.gdbindexes
│   │   ├── a0000000b.gdbtable
│   │   ├── a0000000b.gdbtablx
│   │   ├── a0000000c.gdbindexes
│   │   ├── a0000000c.gdbtable
│   │   ├── a0000000c.gdbtablx
│   │   ├── a0000000d.gdbindexes
│   │   ├── a0000000d.gdbtable
│   │   ├── a0000000d.gdbtablx
│   │   ├── a0000000e.gdbindexes
│   │   ├── a0000000e.gdbtable
│   │   ├── a0000000e.gdbtablx
│   │   ├── a0000000f.gdbindexes
│   │   ├── a0000000f.gdbtable
│   │   ├── a0000000f.gdbtablx
│   │   ├── a00000010.gdbindexes
│   │   ├── a00000010.gdbtable
│   │   ├── a00000010.gdbtablx
│   │   ├── a00000011.gdbindexes
│   │   ├── a00000011.gdbtable
│   │   ├── a00000011.gdbtablx
│   │   ├── a00000012.gdbindexes
│   │   ├── a00000012.gdbtable
│   │   ├── a00000012.gdbtablx
│   │   ├── a00000013.gdbindexes
│   │   ├── a00000013.gdbtable
│   │   ├── a00000013.gdbtablx
│   │   ├── a00000014.gdbindexes
│   │   ├── a00000014.gdbtable
│   │   ├── a00000014.gdbtablx
│   │   ├── a00000015.gdbindexes
│   │   ├── a00000015.gdbtable
│   │   ├── a00000015.gdbtablx
│   │   ├── a00000016.gdbindexes
│   │   ├── a00000016.gdbtable
│   │   ├── a00000016.gdbtablx
│   │   ├── a00000017.gdbindexes
│   │   ├── a00000017.gdbtable
│   │   ├── a00000017.gdbtablx
│   │   ├── a00000018.gdbindexes
│   │   ├── a00000018.gdbtable
│   │   ├── a00000018.gdbtablx
│   │   ├── a00000019.gdbindexes
│   │   ├── a00000019.gdbtable
│   │   ├── a00000019.gdbtablx
│   │   ├── a0000001a.gdbindexes
│   │   ├── a0000001a.gdbtable
│   │   ├── a0000001a.gdbtablx
│   │   ├── a0000001b.gdbindexes
│   │   ├── a0000001b.gdbtable
│   │   ├── a0000001b.gdbtablx
│   │   ├── a0000001c.gdbindexes
│   │   ├── a0000001c.gdbtable
│   │   ├── a0000001c.gdbtablx
│   │   ├── a0000001d.gdbindexes
│   │   ├── a0000001d.gdbtable
│   │   ├── a0000001d.gdbtablx
│   │   ├── a0000001e.gdbindexes
│   │   ├── a0000001e.gdbtable
│   │   ├── a0000001e.gdbtablx
│   │   ├── a0000001f.gdbindexes
│   │   ├── a0000001f.gdbtable
│   │   ├── a0000001f.gdbtablx
│   │   ├── a00000020.gdbindexes
│   │   ├── a00000020.gdbtable
│   │   ├── a00000020.gdbtablx
│   │   ├── a00000021.gdbindexes
│   │   ├── a00000021.gdbtable
│   │   ├── a00000021.gdbtablx
│   │   ├── a00000022.gdbindexes
│   │   ├── a00000022.gdbtable
│   │   ├── a00000022.gdbtablx
│   │   ├── a00000023.gdbindexes
│   │   ├── a00000023.gdbtable
│   │   ├── a00000023.gdbtablx
│   │   ├── a00000024.gdbindexes
│   │   ├── a00000024.gdbtable
│   │   ├── a00000024.gdbtablx
│   │   ├── a00000025.gdbindexes
│   │   ├── a00000025.gdbtable
│   │   ├── a00000025.gdbtablx
│   │   ├── a00000026.gdbindexes
│   │   ├── a00000026.gdbtable
│   │   ├── a00000026.gdbtablx
│   │   ├── a00000027.gdbindexes
│   │   ├── a00000027.gdbtable
│   │   ├── a00000027.gdbtablx
│   │   ├── a00000028.freelist
│   │   ├── a00000028.gdbindexes
│   │   ├── a00000028.gdbtable
│   │   ├── a00000028.gdbtablx
│   │   ├── a00000028.spx
│   │   ├── gdb
│   │   └── timestamps
│   ├── gis_osm_buildings_a_free_1.gpkg
│   ├── gis_osm_roads_free_1.gpkg
│   └── VNP46A1
│       ├── VNP46A1.A2021038.h08v05.001.2021039064328.tif
│       ├── VNP46A1.A2021038.h08v06.001.2021039064329.tif
│       ├── VNP46A1.A2021047.h08v05.001.2021048091106.tif
│       └── VNP46A1.A2021047.h08v06.001.2021048091105.tif
├── texas-blackout-analysis.Rproj
├── texas-blackout-analysis.qmd
└── README.md
```
