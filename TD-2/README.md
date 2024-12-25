# TD2: Creating Spatial Tables

This guide explains how to create spatial tables in a PostgreSQL database with PostGIS enabled. Spatial tables allow you to store and manage geographic data such as points, polygons, and lines.

## Prerequisites

- A PostgreSQL database with PostGIS extension installed (see TD1 if you need help setting this up).
- pgAdmin and/or QGIS installed for managing and visualizing data.

## Steps to Follow

### 1. Creating a Spatial Table (Points)
1. Open **pgAdmin 4** and connect to your PostgreSQL server.
2. Open the `Query Tool` for your spatial database.
3. Execute the following SQL query to create a table with a geometry column:

   ```sql
   CREATE TABLE points_of_interests (
       id SERIAL PRIMARY KEY,
       name VARCHAR(255),
       geom GEOMETRY(Point, 4326)
   );
   ```

4. This table contains:
   - `id`: A unique identifier.
   - `name`: The name of the point of interest.
   - `geom`: A geometry column for storing point data in EPSG:4326 coordinate system.

### 2. Adding Data Using QGIS
1. Open **QGIS** and connect to your PostgreSQL database:
   - Right-click on **PostgreSQL** in the Browser panel and select `New Connection`.
   - Provide the connection details for your database (host, port, database name, user, and password).
   - Click `Test Connection` and then `OK`.
2. Once connected, locate the `points_of_interests` table and add it as a layer.
3. Switch to **Edit Mode** to add new points.
4. Use the map interface to add points and save your changes.

### 3. Verifying Data in pgAdmin
1. Open **pgAdmin** and execute the following query to view the data:

   ```sql
   SELECT * FROM points_of_interests;
   ```
2. The result will display the points you added in QGIS.

### 4. Creating a Spatial Table (Polygons)
To create a table for polygons, use the following SQL command in pgAdmin:

```sql
CREATE TABLE protected_areas (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255),
    geom GEOMETRY(Polygon, 4326)
);
```

Repeat the same steps as above to populate and verify the data.

### 5. Creating a Spatial Table (Linestrings)
For storing line-based geometry data, use the following SQL command:

```sql
CREATE TABLE roads (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255),
    geom GEOMETRY(LINESTRING, 4326)
);
```

## Next Steps

You now have the skills to create and populate spatial tables in PostgreSQL. In the next tutorial (TD3), you will learn how to use spatial SQL functions for advanced analysis.

## Resources

- [PostGIS Documentation](https://postgis.net/documentation/)
- [QGIS Documentation](https://www.qgis.org/en/docs/)


#### Shipfile's link : 
- https://maps.leegov.com/datasets/80708a2f5f56426f94c8be97c182176b/about
