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
| ml:creation_method_detail | string |  additional details about the creation method, including potentially a link to the algorithm |
| ml:boundary_type | ENUM | **REQUIRED**. whether the boundary is for a field, ownership parcel, hedge, or other boundary |
| ml:verified_from | datetime | **REQUIRED**. the first date for which the boundary is verified to be present on ground (e.g. through ground-truth or remote sensing image verification) |
| ml:verified_until | datetime | **REQUIRED**. the last date for which the boundary is verified to be present on ground (e.g., through ground-truth or remote sensing image verification) |
| ml:author | string | **REQUIRED**. Name of individual or organization who created this |
| ml:confidence | float	| a value between zero and one that represents the confidence in a generated polygon (higher value = higher confidence) |
| ml:crop_type | ENUM | the type of crop e.g. maize |
| ml:crop_category | ENUM | high-level crop category e.g. cereal (e.g. [FAO]([url](https://unstats.un.org/unsd/classifications/Family/Detail/1002))) |
| ml:split_name | ENUM | Type of split, e.g., train, val, test. |
| ml:split_idx | uint16 | Integer indexing of splits, e.g., 1, ... ,10 used for cross-validation. |

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
