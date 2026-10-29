# Mill Creek Daylight

A then-and-now map of Edmonton's Mill Creek: a 1967 city street map on one side of a slider, today's map on the other, with the old creek channel, today's creek and the Valley Line LRT drawn over both.

The creek's last stretch, from Connors Road to the North Saskatchewan, was diverted and put underground in 1970. This map was first made in March 2015, while the Valley Line LRT was being designed through the bottom of the ravine, and rebuilt in October 2026.

Live map: https://mattdance.github.io/Mill-Creek-Map/

## What's here

| File | What it is |
|---|---|
| `index.html` | The map page (Leaflet, OpenStreetMap basemap) |
| `web/` | Web-ready copies: the 1967 map as a JPEG and the line layers in WGS84 GeoJSON |
| `MC_1967_Channel.tif.0.tif` | The georeferenced 1967 street map scan (GeoTIFF, Web Mercator). Restored in 2026; `MC_1967_Channel.tif.vrt` points to it |
| `1967_channel.geojson` | The creek channel traced from the 1967 map (EPSG:3857) |
| `MC_Current_Channel.geojson` | The creek in Alberta's provincial base mapping, as downloaded in 2015 (EPSG:4269) |
| `Proposed_LRT_Route.geojson` | The Valley Line LRT route as proposed in 2015 (EPSG:3857) |
| `MC_Contours.geojson` | Provincial contours (EPSG:4269) |
| `Building_Roofline.geojson` | City of Edmonton building rooflines (EPSG:3776) |

The original GeoJSON files keep their 2015 coordinate systems. The copies in `web/` are reprojected to WGS84 so browsers and GitHub's map preview read them correctly.

## Viewing locally

The page loads its layers with `fetch`, so serve the folder rather than opening the file directly:

```
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Sources and credits

- 1967 map: a scanned 1967 Edmonton street map, georeferenced by Matt Dance in 2015.
- Basemap: © OpenStreetMap contributors.
- History: [Mill Creek Ravine, Wikipedia](https://en.wikipedia.org/wiki/Mill_Creek_Ravine); [Andrew Leach, March 2015](https://andrewleach.ca/uncategorized/the-mill-creek-and-the-valley-line-an-opportunity-we-shouldnt-pass-up/); [Taproot Edmonton, January 2025](https://edmonton.taproot.news/pulse/2025/01/23); [CTV News, August 2025](https://www.ctvnews.ca/edmonton/article/city-hall-committee-recommends-mill-creek-bridge-replacements-daylighting-creek/).
