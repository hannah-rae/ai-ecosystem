# AI Ecosystem Extension Specification

- **Title:** AI ecosystem
- **Identifier:** <https://fiboa.github.io/ai-ecosystem/v0.1.0/schema.yaml>
- **Property Name Prefix:** ml
- **Extension Maturity Classification:** Proposal
- **Owner**: @hannah-rae @subash-khanal @yanglexie @jacobsn @eddiechoi00

This document explains the AI Ecosystem Extension to the
[Field Boundaries for Agriculture (fiboa) Specification](https://github.com/fiboa/specification).

This extension adds support for properties useful for integrating field boundary data with the AI/ML ecosystem.

- Examples: [TODO]
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
| ml:creation_method | ENUM | how the label was created e.g. field walk, image-annotated, ML generated |
| ml:creation_method_detail | string | additional details about the creation method, including potentially a link to the algorithm |
| ml:boundary_type | ENUM | Whether the boundary is for a field, ownership parcel, hedge, or other boundary |
| ml:creation_date | datetime  | [Auto-added] Date collection was created or published |
| ml:verified_from | datetime | the first date for which the boundary is verified to be present on ground (e.g. through ground-truth or remote sensing image verification) |
| ml:verified_until | datetime | 	the last date for which the boundary is verified to be present on ground (e.g., through ground-truth or remote sensing image verification) |
| ml:author | string | Name of individual or organization who created this |
| ml:quality | ENUM | the level of quality control applied to this polygon |
| ml:confidence | float	| a value between zero and one that represents the confidence in a generated polygon (higher value = higher confidence) |
| ml:machine_generated | boolean | Indication of machine-generated boundaries or not |
| ml:country_code | string | [Auto-added] three-letter country code for the country that contains the field, e.g. SDN; Can be found https://www.iso.org/obp/ui/#search under the Alpha-3 code column |
| ml:admin0 | string | [Auto-added] a unique admin0 (country) name for the administrative region that contains the field - can auto-generate from [GADM boundaries](https://geodata.ucdavis.edu/gadm/) |
| ml:admin1 | string | [Auto-added] a unique admin1 (state) name for the administrative region that contains the field - can auto-generate from [GADM boundaries](https://geodata.ucdavis.edu/gadm/) |
| ml:admin2 | string | a unique admin2 (county) name for the administrative region that contains the field - can auto-generate from [GADM boundaries](https://geodata.ucdavis.edu/gadm/) |
| ml:crop_type | ENUM | the type of crop e.g. maize |
| ml:crop_category | ENUM | high-level crop category e.g. cereal (e.g. [FAO]([url](https://unstats.un.org/unsd/classifications/Family/Detail/1002))) |

## Contributing

All contributions are subject to the
[fiboa Code of Conduct](https://github.com/fiboa/specification/blob/main/CODE_OF_CONDUCT.md).
For contributions, please follow the
[fiboa contributing guideline](https://github.com/fiboa/specification/blob/main/CONTRIBUTING.md).

### Running tests

You'll need to install [nodejs and npm](https://nodejs.org/en/download/) to run the tests.
Alternatively, you can also use [yarn](https://yarnpkg.com/) instead of npm.
In this case replace all occurrences of `npm` with `yarn` below.
Additionally, you need Python >= 3.9 installed.

Afterwards, navigate to the root of the specification repository.
Now, install the required test software: `npm install` and `npm run init`

Finally, you can run all tests or subset of them:

- To run all tests: `npm test`
- To check the markdown run: `npm run check-docs`
- To check the examples run: `npm run check-examples`
