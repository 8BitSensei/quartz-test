2023-12-19
Tags: #cloud #azure

The primary factors that you need to account for when figuring out how much your OpEx will be on Axure are:
- **Resource types**: Different resources have different costs, and different tiers or configurations in the same resource can change the cost, for example the more memory and cores you use in a VM will increase it's cost
- **Consumption**: Azure uses a pay-as-you-go cost model, the more compute and storage you use, the more costs you will incur. Azure however, does have the option to '*reserve*' resources, meaning you commit to a certain amount of usage over a certain time, but you get a discount, and default to pay-as-you-go if you go over that amount
- **Maintenance**: It's important to maintain and manage your cloud environment to avoid run away costs, such as resources you forgot about
- **Geography**: Deploying to different regions incurs different charges, some regions are just more expensive to use than others. There is also network traffic charges, which themself vary by region; usually ingress is free, but egress is charged based on the location.
- **Subscription type**: Some subscription types have savings included, such as free trials, or the sandbox. You may also have credits applied to your subscription as a part of a deal with Azure
- **Azure Marketplace**: Azure Marketplace lets you purchase Azure-based solutions and services from third-party vendors

To get an idea of cost, look at the [[Azure Pricing calculator]] and the [[Azure Total Cost of Ownership (TCO) Calculator]]

---
# References

https://learn.microsoft.com/en-gb/training/modules/describe-cost-management-azure/2-describe-factors-affect-costs-azure