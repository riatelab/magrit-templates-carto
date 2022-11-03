Template France
---------------

Template created with sf, mapinsetr, rnaturalearth, rnaturalearthdata, rmapshaper and readxl R libraries.

Data sources : Natural Earth, IGN

Made by : Ronan Ysebaert (@rysebaert on GitHub)


Data processing
---------------

The data processing for this map template is the following :

1. Area calculation and extract centroids from ADMIN-EXPRESS-COG édition 2022 France entière (municipalities).
2. Extract world countries from Natural Earth large scale data (1:10m), with rnaturalearth.
3. Simplify polygons with rmapshaper library (60 % of the points of the Natural Earth layer are deleted).
4. Create Voronoi polygons from municipal centroids, intersected with world boundaries. If a given point fall out of the French territory, a 1000m buffer is created around it, and aggregated to the French territory if the buffer area is located within a 1000 m perimeter of the French territory. This step allows to create missing little islands in the world country layer (Molène, Houëdic islands). In that way, all the French muncipalities are included in the Voronoi layer.
5. Union of the Voronoi municipal layer. The World layer is recalculated (difference) to ensure that borders are perfectly seamless with the aggregation of French Voronoi.
6. The Voronoi municipal layer is aggregated in upper territorial divisions : Zones d'emploi, Aires d'attractions des villes, Établissements de Coopération Intercommunale, Départements and Régions. Statistical attributes (area and population 2017) are aggegated (sum) for all these layers.
7. DROM are moved and resized in predefined boxes, using the mapinsetr library. It is done for all territorial divisions.

Available layers
----------------

At the end, 6 layers are available with 3 attributes (total population 2017, total area and name of the territorial unit) and can be joined with French statistics : municipalites (com.geojson), Établissements de Coopération Intercommunale urban areas (epci.geojson) (aav.geojson), employment areas (zemp.geojson), départements (dep.geojson) and regions (reg.geojson).

This template uses Établissements de Coopération Intercommunale, urban areas, employment areas, départements and regions while the other "France" template uses communes, départements and regions.

4 additional layers are useful to build the map template : French neighboring countries, for metropolitan area (countries.geojson) and oversea territories (country_box.geojson), their respective boundaries (borders.geojson and borders_box.geojson) boxes (boxes.geojson)

All the layers are in geojson format, in latitude/longitude (WGS84). To be correctly displayed, they need to be transformed in the reference projection in France (RGF93 v1 / Lambert-93 - France - EPSG:2154).


More information, code, etc.
----------------------------

Feel free to open an issue on this repository or on Magrit issue tracker if you need more information or want to get access to the R code that was used to prepare this template.
