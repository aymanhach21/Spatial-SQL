### Summary of TD-3: Spatial SQL Functions

1. **Import Shapefile into PostGIS**
   - Use the PostGIS Shapefile Import/Export Manager to load the shapefile of Florida parcels into a PostgreSQL table.

2. **Query Parcel Count**
   - Execute a query in `pgAdmin` to count the number of parcels in the table.

3. **Identify Fire Point**
   - Determine the centroid of a specific parcel (e.g., parcel with `gid = 462273`) to represent the fire point.

4. **Define a 1 km Fire Risk Zone**
   - Duplicate the parcel layer in QGIS and apply a spatial filter to highlight parcels within a 1 km radius of the fire point.
   - Adjust symbology to visualize risk zones and include an additional fire point (e.g., parcel `gid = 460957`) by modifying the filter.

5. **Answer Spatial Questions**
   - Write spatial SQL queries to:
     - Count parcels within a 1 km radius of the two fire points.
     - Calculate the total area of parcels near the fire points.
