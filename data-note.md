# Data notes

## Question
- Where are schools actually located across Kwara state, and how complete is OSM coverage of them by ward?

## Study Area
Kwara, Nigeria.

## Kwara-wards
- Source: GRID3/ NGA Operational wards. https://data.grid3.org
- Published date: 30-06-2026.
- Downloaded: 10-09-2026.
- Geometry: polygon(multipolygon).
- Dataset covered 24 states(not yet validated for all states).
- Filtered to Kwara only as that is what my project needed.
- Features count: 193 features.
- Columns include: 14 columns(country, iso3, state, statecode, multipart,  lga, lga_alt_na, ward, ward_alt_n, ward_v1_gr, ward_in_gr,area_sqkm, source, date).
- ward name field: no nulls, all 193 wards are fully named.
- Covers Kwara wards fully.

## Amenity_school_kwara_clipped.
- Source: OpenStreetMap via QuickOSM in Qgis.(produced two geometries(points and polygon)).
- Geometry: point.
- query Tag: key=amenity, value=school.
- Spatial extent used: layer extent.
- Raw data pull returned 183 features(layer extent uses bounding box, not exact boundary) and 18 columns.
- clipped to kwara_wards boundary which returned 102 features. columns was unchanged.
- 42 out of the 102 features have a NULL name field.

## Polygon_amenity_school_clipped.
- Same query as above.
- Geometry:polygon.
- Raw data pull returned 153 features(layer extent uses bounding box, not exact boundary) and 18 columns.
- Clipped to kwara_wards boundary which got reduced to 8 correct features and unchanged columns.
- 5 out of the 8 schools have NULL name field.

## Known Issue
- QuickOSM's layer extent searches bounding rectangle of the boundary layer, not its true shape. 
