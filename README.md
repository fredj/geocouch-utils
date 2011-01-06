Helper Functions for GeoCouch
=============================

This is a small CouchApp that contains some helper functions for GeoCouch. Licensed under the MIT License.

lists
-----

### geojson.js ###

This function outputs a GeoJSON FeatureCollection (compatible with
OpenLayers). The geometry is stored in the `geometry` property, all
other properties in the `properties` property.

Examples:

    $ curl -X PUT -d '{"type":"Feature", "color":"orange" ,"geometry":{"type":"Point","coordinates":[11.395,48.949444]}}' 'http://localhost:5984/gc-utils/myfeature'
    {"ok":true,"id":"myfeature","rev":"1-2eeb1e5eee6c8e7507b671aa7d5b0654"}

    $ curl -X GET 'http://localhost:5984/vmxch/_design/gc-utils/_list/geojson/all'
    {"type": "FeatureCollection", "features":[{"type": "Feature", "geometry": {"type":"Point","coordinates":[11.395,48.949444]}, "properties": {"_id":"myfeature","_rev":"1-2eeb1e5eee6c8e7507b671aa7d5b0654","type":"Feature","color":"orange"}}
