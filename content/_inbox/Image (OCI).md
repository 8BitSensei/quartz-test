2023-02-27
#containerisation #technology 

Container Images were invented in the early days of containerisation (process isolation) at dotCloud (now Docker). They developed a method to package application code and dependencies in a way that resolved some of the memory and automation issues seen when setting up [[virtual machines]]. This package was a Container Image. [^1]

This Container Image is an immutable package of OS files, application code, and dependencies made up of re-usable layers. [^1]

The Container Image relied on a Linux construct call the [[Union File System (Linux)|Union File System]] (UnionFS) which allows merging file systems.  [^1]

The OCI Spec [^3] defines an image of consisting of three parts, the **image manifest**, an (optional) **image index**, a set of **filesystem layers**, and a **configuration**. 

##### Image Index

> The Image Index is a higher-level manifest containing file descriptors to architecture-specific image manifests (eg: amd64, arm, x86, etc.). It can be thought of as a [Merkle tree](https://en.wikipedia.org/wiki/Merkle_tree) that contains different versions of the same image
> ...
> With the help of the Image Index, a container manager such as _Docker_ or _Containerd_ could retrieve the contents of a given container image for the host's current CPU architecture and derive a container bundle from them. [^6]

`schemaVersion` : *int*
	Specifies the image manifest schema version, currently must be `2` (?)

`mediaType` : *string*
	Contains the media type (e.g. *image, artifact*), usage differs from the `config.mediaType`, so don't confuse them.

`manifests` : *array of objects*
	An array of descriptor objects referring to the manifests for specific platforms. It describes the mediaType, the size, the platform, and provides the digest.

##### Image Manifest

> an image manifest provides a configuration and set of layers for a single container image for a specific architecture and operating system [^3]

`schemaVersion` : *int*
	Specifies the image manifest schema version, currently must be `2` (?)

`mediaType` : *string*
	Contains the media type (e.g. *image, artifact*), usage differs from the `config.mediaType`, so don't confuse them.

`config` : *descriptor*
	References a configuration object for a container, by digest. A *descriptor* describes the disposition of the targeted content, it includes the type of the content, am identifier (a *digest*), and the byte-size of the raw content. [^5]

`layers` : *array of descriptors*
	Each item in the array is a *descriptor*, the **base layer must be at index 0**. Subsequent layers must follow stack order (?). 

`subject` : *descriptor* (optional)
	Specifies a *descriptor* of another manifest, indicates a relationship to the specified manifest using the *[[referrers API]]*.

`annotaions` : *string-string map* (optional)
	Arbitrary data for the image manifest, must use the *annotation rules*.


##### Image Configuration

##### Filesystem Layers


---
# References

[^1]: https://ravichaganti.com/blog/2022-10-18-understanding-container-images-the-fundamentals/

https://ravichaganti.com/blog/2022-10-28-understanding-container-images-oci-image-specification/

[^3]: https://github.com/opencontainers/image-spec/blob/main/spec.md

https://github.com/opencontainers/image-spec/blob/main/manifest.md

[^5]: https://github.com/opencontainers/image-spec/blob/main/descriptor.md

[^6]: https://blog.quarkslab.com/digging-into-the-oci-image-specification.html