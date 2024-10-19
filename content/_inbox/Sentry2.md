2024-04-29
Tags: #iam #bazaarvoice #aws 

#### Final Cause
- Managing access and permissions to “the cloud” is a difficult and complex task
- builders to customize specific roles and permissions around the _systems_ they’ve built
- provide a central interface to manage two types of entities - _**Groups**_ and _**Systems**_
#### Formal
- Sentry2 is an identity and access management orchestrator
- Is built to manage groups of BV users and their permissions to cloud services
- group users by their role and function in the business
	- permissions must be attached to these _groups_
#### Material
- Does use Okta as its identity provider
- Paths are owned by CODEOWNERS
- CODEOWNERS are files in the .git directory of a repo
- in the CODEOWNERS paths in the repo are defined next to a user
	- assumption is these are the code owners in a group and changes in that path need approval from owners
- Roles in Sentry2 relate to AWS IAM roles
- Can be used with terraform
#### Efficient
- Managed by cloud-engineering team

# Entities
- Groups and Systems are entities
- Entities can have a 1-1 owner/owned relationship with another entity
- Entities have roles and permissions
- Entities represent things outside of Sentry2 either BV teams or cloud resources
- Paths that can be modified

## Groups

##### Final 
- BV teams can register as groups to share cloud platform access
- Leads can directly manage team member access
##### Form
- central repository of group information (such as primary e-mail address, leads, etc)
- are Sentry2 entities
	- represent a set of individuals who have a common goal and function
- usually organised around a function or a project
- Can have multiple of something called Sentry2 group code owner
	- Sentry2 group code owners are able to approve changes

##### Material
- Synchronises groups with Okta to provide SSO
- Groups also equate to AWS principals/accounts
## Systems

##### Final
- Can be registered by BV teams
- Owners create and manage custom roles and permissions for system's access to the cloud
- Provides boundary for interacting with system's resources
- Modify ownership and access to systems
##### Form
- are Sentry2 entities
	- represent a set of cloud resources that serve a common function and are owned *by one group*
- Has something called a Sentry2 operator
	- Sentry2 operators approve changes
##### Material
- AWS resources associated with a system entity will be tagged with `bv:system`



---
# References

https://bazaarvoice.atlassian.net/wiki/spaces/DEV/pages/77883245247/Sentry2