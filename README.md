# leaflet-challenge

An interactive visualisation of global earthquake activity was created using Javascript. Global earthquake data for all magnitudes over the past week was obtained from the USGS GeoJSON website. 

First the Tilelayer function was used to create a basemap on which the data will be visualised. The basemap was powered by OpenStreetMap. An additional Street tile layer was also added, as this provides greater detail at a street level. The L.map function was used to initialise the map object and the Centerpoint coordinates were also defined and the default tile layer was set to basemap.

Then two separate layers were created to store the earthquake and tectonic data. Basemaps and OverlayMaps were then defined to allow the user to switch between our basemap and street view or the earthquake and tectonic plate data. THe control.layers function was used to assist with adding this depth and flexibility to the visualisation.

The d3.json function was used to define the URL being used. The "https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/all_week.geojson" URL was used to pull earthquake data of all magnituds over a 7 day period.

Next the StyleInfo function was coded to define the styling details for the visualisation. For example, the fillcolor feature determines the colour based on earthquake depth and the radius feature scales the earthquake marker based on the magnitude. The getColor(depth) function is also used to define the marker colours based on the depth of the earthquake. 

The getRadius(magnitude) function is used to increase the scale of marker size by 5, for better visibility.

Finally, the earthquake markers are added to the map and the L.circleMarker(latlng) funciton is used to define the earthquake locations as circle markers. The layer.bindPopup function is used to set the popup features for each earthquake marker. Thereby, clicking on an individual earthquake marker will display its location, depth and magnitude. A legend is also defined for the visualisation, that maps the depths of the earthquake with the applicable colours.

In the end, the d3.json fucntion is once used to fetch tectonic plate boundaries data from "https://raw.githubusercontent.com/fraxen/tectonicplates/master/GeoJSON/PB2002_boundaries.json". 