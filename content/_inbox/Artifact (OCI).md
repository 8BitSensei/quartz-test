2023-02-17
#technology #containerisation 

> Utilizing the [[Image (OCI)#Image Manifest|manifest]] and [[Image (OCI)#Image Index|index]] definitions, new artifacts, such as the [Singularity project](https://github.com/sylabs/singularity), can be stored and served using the [distribution-spec](https://github.com/opencontainers/distribution-spec/).

> A unique artifact type is similar to defining a file extension. Defining a unique artifact allows various tools to know how to uniquely work with the type. It allows a registry to display the type and tooling, such as vulnerability scanners, a means to know if and how they should interact with the contents.

> For computer processing, artifacts are defined by setting the [[Media Types (OCI)|media type]] to a globally unique value.

All OCI compliant resources are artifacts, [[Image (OCI)]] is just a specialised artifact.

See [[Media Types (OCI)]] for more information on defining your own media type for a custom artifact.

> Some artifacts may be represented as a single file, such as a config artifact representing a deployment details for an application. While other artifacts may include a config object, and a collection of binaries compressed as yet another layer.



---
# References

https://github.com/opencontainers/artifacts

https://github.com/opencontainers/artifacts/blob/main/artifact-authors.md