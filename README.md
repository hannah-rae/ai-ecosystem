# AI Ecosystem Extension Specification

- **Title:** AI ecosystem
- **Identifier:** <https://fiboa.github.io/ai-ecosystem/v0.1.0/schema.yaml>
- **Property Name Prefix:** ml
- **Extension Maturity Classification:** Proposal
- **Owner**: @hannah-rae @subash-khanal @yanglexie @jacobsn @eddiechoi00

This document explains the AI Ecosystem Extension to the
[Field Boundaries for Agriculture (fiboa) Specification](https://github.com/fiboa/specification).

This extension adds support for properties useful for integrating field boundary data with the AI/ML ecosystem.

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
| ml:boundary_type | string | **REQUIRED**. whether the boundary is for a field, ownership parcel, hedge, or other boundary |
| ml:creation_date | datetime  | **REQUIRED**.[Auto-added] Date collection was created or published |
| ml:verified_from | datetime | **REQUIRED**. the first date for which the boundary is verified to be present on ground (e.g. through ground-truth or remote sensing image verification) |
| ml:author | string | **REQUIRED**. Name of individual or organization who created this |
| ml:country_code | string | **REQUIRED**. ISO 3166-1 alpha-3 country code. Three-letter country code for the country that contains the field, e.g. `SDN` for Sudan. Can be found at <https://www.iso.org/obp/ui/#search> under the Alpha-3 code column. |
| ml:admin1 | string | **REQUIRED**. ISO 3166-2 codes for identifying the principal subdivisions (e.g., provinces or states) of a country (i.e. admin1) that contains the field. |
| ml:admin2 | string | **REQUIRED**. a unique admin2 (county) name for the administrative region that contains the field - can auto-generate from [GADM boundaries](https://geodata.ucdavis.edu/gadm/) |

*Note: Country Code, admin1 and admin2 could be derived from [GADM boundaries](https://geodata.ucdavis.edu/gadm/).*

## Contributing

See the [contributing guideline](CONTRIBUTING.md) for more details.
