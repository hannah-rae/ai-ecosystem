# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- GeoJSON and GeoParquet examples.

### Changed

- `ml:admin1` is a ISO 3166-2 Code for provinces/states.
- `ml:admin2` is a modified HASC-2 Code for counties/municipalities. The modification replaced the `.` to `-`, to more closely resemble the ISO 3166-2 Codes.

### Deprecated

- ...

### Removed

- Removed the following features, as seemed unnecessary at this point in time. Open to adding them back in as needed in the future.

| Property Name   | Type   | Description |
| --------------- | ------ | ----------- |
| ml:creation_method | string | **REQUIRED**. how the label was created e.g. field walk, image-annotated, ML generated |
| ml:creation_method_detail | string |  additional details about the creation method, including potentially a link to the algorithm |
| ml:boundary_type | string | **REQUIRED**. whether the boundary is for a field, ownership parcel, hedge, or other boundary |
| ml:creation_date | datetime  | **REQUIRED**.[Auto-added] Date collection was created or published |
| ml:verified_until | datetime | **REQUIRED**. the last date for which the boundary is verified to be present on ground (e.g., through ground-truth or remote sensing image verification) |
| ml:quality | string | **REQUIRED**. the level of quality control applied to this polygon |
| ml:confidence | float | a value between zero and one that represents the confidence in a generated polygon (higher value = higher confidence) |
| ml:machine_generated | boolean | **REQUIRED**. Indication of machine-generated boundaries or not |
| ml:admin0 | string | **REQUIRED**. [Auto-added] a unique admin0 (country) name for the administrative region that contains the field - can auto-generate from [GADM boundaries](https://geodata.ucdavis.edu/gadm/) |
| ml:crop_type | string | the type of crop e.g. maize |
| ml:crop_category | string | **REQUIRED**. high-level crop category e.g. cereal (e.g. [FAO](https://unstats.un.org/unsd/classifications/Family/Detail/1002)) |

### Fixed

- ...

## [v0.1.0] - 2024-03-01

- First release

[Unreleased]: <https://github.com/radiantearth/stac-spec/compare/v0.1.0...main>
[v0.1.0]: <https://github.com/radiantearth/stac-spec/tree/v0.1.0>
