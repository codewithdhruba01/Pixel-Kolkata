# Geographic Data Pipeline

## 1. Purpose

This document defines how source geographic data becomes a navigable isometric pixel-art map. Geographic data describes where features are; art assets define how those features look. The pipeline joins the two without treating them as the same thing.

## 2. Coverage boundary

Before acquisition, create and approve a `kolkata-coverage.geojson` polygon. Record:
- Boundary name and version.
- Included administrative areas.
- Coordinate reference system.
- Date approved.
- Known exclusions.

Suggested initial coverage can include Kolkata, Howrah, Bidhannagar/Salt Lake and New Town/Rajarhat. Expand to the wider metropolitan area only after defining its boundary precisely.

## 3. Candidate data sources

- OpenStreetMap regional extracts or Overpass API for roads, buildings, waterways, parks and points of interest.
- Overture Maps for supplementary feature datasets where suitable.
- Official or authoritative public datasets where available and licensed.
- Manually curated landmark records with verified coordinates and descriptions.

Check source freshness, coverage, attribution requirements and licence compatibility before use. OpenStreetMap data is under ODbL and requires appropriate attribution; review share-alike implications for derivative databases. Keep a source register.

## 4. Processing stages

1. Acquire source extracts and save their metadata.
2. Clip features to the approved coverage boundary.
3. Normalize tags into project categories.
4. Validate geometries and remove invalid or irrelevant records.
5. Reproject to a suitable local metric CRS for spatial operations.
6. Simplify geometry by feature class and intended zoom level.
7. Generate stable feature IDs and provenance fields.
8. Convert features into grid/chunk references.
9. Attach sprite/style mappings.
10. Export chunk assets, search records and a manifest.
11. Run automated validation and visual QA.

## 5. Feature categories

| Source feature | Project category | Visual representation |
|---|---|---|
| Building polygon | building | Building sprite or simplified footprint |
| Road line | road | Road tiles or vector overlay |
| Railway line | railway | Rail tiles/line |
| Waterway/polygon | water | Water tiles or polygon |
| Park/green area | green_space | Grass and tree assets |
| Place/attraction | landmark or POI | Marker and custom sprite |
| Transit station | transport | Station sprite and searchable point |

## 6. Coordinate handling

- Store original WGS84 longitude/latitude for interoperability.
- Use an appropriate projected CRS for metric processing and grid generation.
- Keep the CRS identifier in pipeline configuration and output metadata.
- Never mix degrees and metres in the same calculation.
- Preserve a reversible mapping from map-grid position to geographic location.

## 7. Chunk generation

Each output chunk should have:
- A stable ID.
- Grid coordinate and geographic bounds.
- Feature IDs contained or intersecting the chunk.
- Render order or layer information.
- Asset references.
- Data version and build timestamp.

Features crossing chunk boundaries need a consistent clipping/ownership strategy so roads and rivers do not develop seams or duplicate hit targets.

## 8. Pixel-art mapping

Use deterministic style rules:
- Road class maps to a road-tile family.
- Building type/height, when reliable, maps to an appropriate building style.
- Green-space polygons map to ground and vegetation patterns.
- Important landmarks map to hand-crafted sprites.
- Missing or uncertain tags use a neutral fallback asset.

Do not invent exact building heights or architectural details from incomplete source data. Mark approximate or stylized features accordingly.

## 9. Validation

Automated checks:
- All output geometries are valid.
- All chunks fall within the approved boundary.
- No duplicate stable IDs.
- All sprite references resolve.
- Manifest references existing assets.
- Attribution metadata is present.
- Feature counts and source dates are recorded.

Visual checks:
- Roads and waterways connect across chunk edges.
- Landmark positions are plausible.
- No obvious holes or overlaps.
- Labels remain legible at intended zoom levels.
- Map orientation is consistent.

## 10. Reproducibility and licensing

Store pipeline configuration, source URLs, acquisition dates, source versions, processing code version and output version. Keep attribution visible in the application and in downloadable datasets where required. Review each dataset's terms before combining or redistributing it.
