---
date: 2023-07-17
draft: false
tags:
  - CI/CD
  - technology
  - DesignPattern
---
Blue-Green is a deployment method where you run two identical production environments, one named Blue, the other Green. Only the Blue environment is live, serving production traffic, the Green environment is used for staging and testing changes. Once we are happy with the stability of the Green environment, are router switches to the Green environment, serving production traffic to that environment.

The benefit of this is that it almost completely eliminates downtime, as well as providing us with the option to quickly roll back to the Blue environment if the Green environment fails. An issue with this style of deployment is when your service uses a relational database, this can lead to discrepancies between your Blue and Green databases during an update. It is recommended, that to avoid this you configure a single database for backward and forward compatibility.

Once you have switched over to your Green deployment, Blue can now be used for staging and testing changes. In this way we can continually cycle between the two deployments.


---
# References
- https://docs.cloudfoundry.org/devguide/deploy-apps/blue-green.html
- https://martinfowler.com/bliki/BlueGreenDeployment.html