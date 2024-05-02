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

| Property Name    | Type   | Description                                                  |
| ---------------- | ------ | ------------------------------------------------------------ |
| ml:boundary_type | string | **REQUIRED**. Whether the boundary is for a field, ownership parcel, hedge, or other boundary |
| ml:creation_date | date   | **REQUIRED**. Date collection was created or published       |
| ml:verified_from | date   | **REQUIRED**. The first date for which the boundary is verified to be present on ground (e.g. through ground-truth or remote sensing image verification) |
| ml:author        | string | **REQUIRED**. Name of individual or organization who created this. |
| ml:country_code  | string | **REQUIRED**. ISO 3166-1 alpha-3 country code. Three-letter country code for the country that contains the field, e.g. `SDN` for Sudan. Can be found at <https://www.iso.org/obp/ui/#search> under the Alpha-3 code column. |
| ml:admin1        | string | **REQUIRED**. Modified ISO 3166-2 codes for identifying the principal subdivisions (e.g., provinces or states) of a country (i.e. admin1) that contains the field. The feature only contains the second part of the ISO 3166-2 code, to reduce redundancy. |
| ml:admin2        | string | A unique admin2 (county) name for the administrative region that contains the field. The feature contains the last part of the HASC 2 codes. The HASC 2 codes can be found [here](https://data.apps.fao.org/catalog/dataset/hasc-codes/resource/76ec426d-deac-4bc4-b558-3095bb89c805). |

> [!NOTE]  
> Country Code, admin1 and admin2 can be derived from [GADM boundaries](https://geodata.ucdavis.edu/gadm/).

Additionally, the following properties from the core specification from the
[core specification](https://github.com/fiboa/specification/blob/main/core/README.md)
are relevant for AI usecases:

| Property Name          | Type   | Description                                                  |
| ---------------------- | ------ | ------------------------------------------------------------ |
| determination_method   | string | **REQUIRED**. The boundary creation method                   |
| determination_datetime | string | **REQUIRED**. The first date for which the boundary is verified to be present on ground |

For more details and the full specification of these fields, please see the [determination properties defined in core specification](https://github.com/fiboa/specification/blob/main/core/README.md#determination-properties).

## Contributing

See the [contributing guideline](CONTRIBUTING.md) for more details.
