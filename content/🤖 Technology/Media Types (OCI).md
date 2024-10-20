---
date: 2023-02-28
draft: false
tags:
  - technology
  - containerisation
---
The `mediaType` property in OCI specifications describes the type of file or element that is being described. This allows software processing that file or element to process it correctly according to the OCI specifications.

The following media types are described in the OCI specifications:
- `application/vnd.oci.descriptor.v1+json`
- `application/vnd.oci.layout.header.v1+json`
- `application/vnd.oci.image.index.v1+json`
- `application/vnd.oci.image.manifest.v1+json`
- `application/vnd.oci.image.config.v1+json`
- `application/vnd.oci.image.layer.v1.tar`
- `application/vnd.oci.image.layer.v1.tar+gzip`
- `application/vnd.oci.image.layer.v1.tar+zstd`
- `application/vnd.oci.artifact.manifest.v1+json`

The following format is used to define a media type:
`application/[registration-tree].[org|company|entity].[objectType].[optional-subType].[version]+[optional-configFormat]`

-   **`registration-tree`** - represents an IANA root tree. See [iana registration trees](https://tools.ietf.org/html/rfc6838#section-3) for public and private tree options.
-   **`org|company|entity`** - represents an open source foundation (`oci`, `cncf`) or a company (`microsoft`, `ibm`) or some unique entity.
-   **`objectType`** - a value representing the short name of the type.
-   **`optional-subType`** - provides additional extensibility of an `objectType`
-   **`version`** - provides artifact authors the ability to revision their schemas and formatting, enabling tools to identify which format they will process.
-   **`optional-configFormat`** - while `config.mediaType` represents the unique identifier of an artifact, providing a config object is optional. If a config object is provided, `.json`, `.yaml` or other standard textual formats are preferred. By utilizing standard text formats, registry operators MAY parse the contents to provide additional context to users. If the config object is null, the `optional-configFormat` MUST be empty.

A media type has to be a globally unique value.


---
# References

https://github.com/opencontainers/artifacts/blob/main/artifact-authors.md