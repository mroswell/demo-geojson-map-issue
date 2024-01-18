# demo-geojson-map-issue

The db is a subset of the geojson file. I used datasette-geojson to filter, and I used geojson-to-sqilte to make the db.

What I see when I load this with `dataset . --root` is documented at https://github.com/eyeseast/datasette-geojson-map/issues/26 

I get the broken images regardless of whether the table is simply loaded by default or there is a simplestyle SQL query
```
SELECT rowid, geometry, "#ff0000" as fill, "#0000ff" as stroke, 0.5 as [stroke-width]
FROM vacant_bldg_rehabs
ORDER BY rowid
```
The key point is that for some reason it is trying to pull markers from a mapbox location where I don't have credentials to see them. The image link for each marker is: https://a.tiles.mapbox.com/v3/marker/pin-m+7e7e7e@2x.png
which for me yields:
```
{
"message": "Not Authorized",
"error_detail": "Direct access not allowed"
}
```
