2024-04-15
Tags: #kubernetes #deployment


### Rolling Deployment
Default Deployment
Slowly one-by-one updates Pods in a node replacing them with a new version. 
Uses a readiness probe to check if a new pod is ready before starting the next pod.
Optional parameters in the *spec:strategy*
- **MaxSurge**: Max number of pods a deployment is allowed to create at one time, default value is %25
- **MaxUnavailable**: Max number of pods allowed to be unavailable during the rollout. 
### Recreate (Big-Bang) Deployment
Simply killing the old pods and starting them up again with a new image!
Can be set in *strategy:type*
### Blue-Green Deployment
Maintain two versions of a deployment
Blue is the current version
Green is the new one

Use Kubernetes services to manage traffic between the two, route to Green and if there is an issue switch back to Blue. We should also be able to do this weighted, say 10% of traffic goes to Green and this ramps up.
### Canary Deployment
We deploy a single instance of a new version of a Pod or a Service amongst a group of older known-good versions, and watch for errors! Slowly start increasing the new version deployments, and if errors begin appearing rollback.

We can redirect a small section of users to our new version, and increase the number of users with the number of new versions, these are our canaries.

### Shadow Deployment
Deploy a new version of a service alongside the old version, and duplicate incoming traffic to this new version. This new version will not return any data to the user, allowing us to test it and see how it behaves without affecting the user.


---
# References
