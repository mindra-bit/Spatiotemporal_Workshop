# Spatiotemporal Workshop — Data Repository

Shared data assets for the four-day Bayesian Spatiotemporal and R-INLA workshop led by Henk Folmer and I Gede Nyoman Mindra Jaya.

## Bandung boundary

- [data/bandung_kecamatan_gadm41.geojson](data/bandung_kecamatan_gadm41.geojson) — 30 Kota Bandung kecamatan polygons, as provided by the course organizer.
- [Direct raw download](https://raw.githubusercontent.com/mindra-bit/Spatiotemporal_Workshop/main/data/bandung_kecamatan_gadm41.geojson)

The R Markdown ebook automatically downloads this public GeoJSON, validates the 30 district names, and caches it in its local `data/` folder. The synthetic teaching grid is a fallback only; it must never be interpreted as real administrative geometry.

## Use in R / Posit Cloud

```r
map_url <- "https://raw.githubusercontent.com/mindra-bit/Spatiotemporal_Workshop/main/data/bandung_kecamatan_gadm41.geojson"
bandung <- sf::st_read(map_url, quiet = TRUE)
stopifnot(nrow(bandung) == 30, "NAME_3" %in% names(bandung))
plot(sf::st_geometry(bandung))
```

## Data provenance

The boundary was supplied in the organizer's `data.zip` attachment. Confirm original licensing/attribution before redistribution in published research. The workshop's epidemiological case counts, covariates, and relative risks remain **simulated**, not public-health observations.

When observational CSV data are added, please document column names, geographic identifiers, time reference, units, source, and usage permissions.
