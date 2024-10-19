2023-07-14
Tags: #containerisation #oci

- a new field named `artifactType` can be set on an image manifest as a first-class mechanism to define an OCI Artifact
- `subject` which allows you to point to another object which has already been published to the registry
- new endpoint has been added to the registry API to query/discover them as well

- `data` field in the descriptor
- non-distributable layers are deprecated
- zstd compression support
- extension support in distribution-spec
- support for resuming chunked blob push
- anonymous blob mount support in distribution-spec
- a `Warning` header for surfacing user-facing client warnings

---
# References

- https://www.chainguard.dev/unchained/oci-announces-upcoming-changes-for-registries
- https://opencontainers.org/posts/blog/2023-07-07-summary-of-upcoming-changes-in-oci-image-and-distribution-specs-v-1-1/