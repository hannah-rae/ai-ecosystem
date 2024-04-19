# AI Ecosystem Extension Specification

This document explains the AI Ecosystem Extension to the
[Field Boundaries for Agriculture (fiboa) Specification](https://github.com/fiboa/specification).

- **Title:** AI ecosystem
- **Identifier:** <https://fiboa.github.io/ai-ecosystem/v0.1.0/schema.yaml>
- **Property Name Prefix:** ml
- **Extension Maturity Classification:** Proposal
- **Owner**: @hannah-rae @subash-khanal @yanglexie @jacobsn @eddiechoi00

This extension also adds support for properties useful for integrating field boundary data with the AI/ML ecosystem.

- Examples: (TODO)
  - [GeoJSON](examples/geojson/)
  - [GeoParquet](examples/geoparquet/)
- [Schema](schema/schema.yaml)
- [Changelog](./CHANGELOG.md)

## Properties

The fields in the table below can be used in these parts of fiboa documents:

- [ ] Collection
- [x] Feature Properties

| Property Name   | Type   | Description |
| --------------- | ------ | ----------- |
| ml:creation_method | string | **REQUIRED**. how the label was created e.g. field walk, image-annotated, ML generated |
| ml:creation_method_detail | string |  additional details about the creation method, including potentially a link to the algorithm |
| ml:boundary_type | string | **REQUIRED**. whether the boundary is for a field, ownership parcel, hedge, or other boundary |
| ml:creation_date | datetime  | **REQUIRED**.[Auto-added] Date collection was created or published |
| ml:verified_from | datetime | **REQUIRED**. the first date for which the boundary is verified to be present on ground (e.g. through ground-truth or remote sensing image verification) |
| ml:verified_until | datetime | **REQUIRED**. the last date for which the boundary is verified to be present on ground (e.g., through ground-truth or remote sensing image verification) |
| ml:author | string | **REQUIRED**. Name of individual or organization who created this |
| ml:quality | string | **REQUIRED**. the level of quality control applied to this polygon |
| ml:confidence | float | a value between zero and one that represents the confidence in a generated polygon (higher value = higher confidence) |
| ml:machine_generated | boolean | **REQUIRED**. Indication of machine-generated boundaries or not |
| ml:country_code | string | **REQUIRED**. [Auto-added] three-letter country code for the country that contains the field, e.g. SDN; Can be found <https://www.iso.org/obp/ui/#search> under the Alpha-3 code column |
| ml:admin0 | string | **REQUIRED**. [Auto-added] a unique admin0 (country) name for the administrative region that contains the field - can auto-generate from [GADM boundaries](https://geodata.ucdavis.edu/gadm/) |
| ml:admin1 | string | **REQUIRED**. [Auto-added] a unique admin1 (state) name for the administrative region that contains the field - can auto-generate from [GADM boundaries](https://geodata.ucdavis.edu/gadm/) |
| ml:admin2 | string | **REQUIRED**. a unique admin2 (county) name for the administrative region that contains the field - can auto-generate from [GADM boundaries](https://geodata.ucdavis.edu/gadm/) |
| ml:crop_type | string | the type of crop e.g. maize |
| ml:crop_category | string | **REQUIRED**. high-level crop category e.g. cereal (e.g. [FAO](https://unstats.un.org/unsd/classifications/Family/Detail/1002)) |

## Contributing

See the [contributing guideline](CONTRIBUTING.md) for more details.
