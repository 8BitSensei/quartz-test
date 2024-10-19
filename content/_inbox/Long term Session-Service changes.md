2023-08-29
Tags: #polystream 

There are two types of entities that come together to create a session container, the base image, and then artifacts which are applied on top of the image.

We have distinguished two types of artifacts which are hard coded into the Session-Service

1) Application artifact, which contains all the contents of an application to be streamed
2) Runtime artifact, which contains the streamer runtime and provides the command to start the stream on a container

We have been asked to provide a way to now append a third artifact that contains the debugger. This presents an issue with the Session-Service, adding another artifact with extra tooling for containers requires a significant code change, and causes bloating of the session-service code.

Instead of providing the quick fix for this problem which will only exasperate the previously stated issues, we should invest in re-working the container session launch process to be extensible for any number of artifacts and additional tools.

The way we apply artifacts to the base image is very standard between artifacts and is easily applied to any artifact:
- Information about the artifact is applied to the _ContainerInformation_ model as an _ApplicationInformation_ model and passed to ContainerRunner
- A Volume and VolumeMount is added for each Artifact (currently hard-coded)
- The VolumeMount path is merged with the WorkingDirectory, Executable, and Arguments on the Artifact
- Add ServerConfig from each Artifact to CSI
- Validate Application mount paths (currently only the application)
- Add artifact log directories
- Append commands from artifact to container (currently only the runtime)
- Expand variables from artifacts

I propose that in the short term we:

1) Update the session start request to contain a `DebuggerVersion` property from which we can generate an image in the same manner that we do the `StreamerVersion`. 
3) Add a friendly name label to Artifacts, this will be needed for the volume mount and expanded variables
4) Rename the `ApplicationInformation` model to `ArtifactInformation`
5) Change the `Application` and `Runtime` properties on the `ContainerInformation` model to a single `List<ApplicationInformation> Artifacts` property
6) Update the `SessionQueueJob` to take the `applicationId`, `debuggerVersion`, and `streamerVersion` and append those the the `Artifacts` property 
7) Add a new class `KubernetesContainerProducer` which takes the `ContainerInformation` and produces a `V1Pod` object, which can be passed to the `KubernetesContainerRunner` to launch
8) Process each Artifact provided to the `KubernetesContainerProducer` in the following way:
	1) Add a Volume and `VolumeMount` to the pod spec for each artifact with the name and `MountPath` property set to the provided friendly name on the Artifact
	2) Open a container port for the application as defined in the PORT statement
	3) Update the `WorkingDirectory`, `Executable`, and `Arguments` properties on each `ArtifactInformation` to be merged with their respective mount paths
	4) Add any supplied `ServerConfig` key value pairs to the config CSI
	5) Validate and apply any provided mount paths
	6) Apply any provided log directories
	7) Use `/bin/bash  -c` as an entrypoint for the container with the following commands appended from the artifact, this means commands will respect the order that artifacts are passed, meaning the streamer runtime should always be supplied last:
		1) `cd %working directory%` 
		2) `%executable% %args%`
9) Update the `ExpandObjectVariables` method to use the friendly name when an `ArtifactInformation` object is provided as the root of the variable 
10) Update the session start response to include added ports

In the long term, it would be beneficial if the `StartSessionRequest` simply included a list of artifact ids to append to the streaming container, which would include the application, server, debugger, and any future tools.



No friendly name, for internal usage we can just have a guid e.g. volume names

The sessionQueueJob can just take a list of artifacts, thus the Gateway needs to convert the client request into a valid list

Use the executable only from the last artifact

We don't want to know the name of the other artifacts, variables should just be sourced from the last artifact

multiple stacked runtimes




---
# References
