# demo-geojson-map-issue

The db is a subset of the geojson file. I used datasette-geojson to filter, and I used geojson-to-sqilte to make the db.

What I see when I load this with `dataset . --root` is documented at https://github.com/eyeseast/datasette-geojson-map/issues/26 

I get the broken images regardless of whether the table is simply loaded by default or there is a simplestyle SQL query
```
SELECT rowid, geometry, "#ff0000" as marker, "#0000ff" as stroke, 0.5 as [stroke-width]
FROM vacant_bldg_rehabs
ORDER BY rowid
```

