- What is Cloud Computing?
- Azure vs AWS vs GCP
- Azure Regions, Availability Zones, Resource Groups
- Azure Subscriptions & Management Groups


### Cloud Computing

**Cloud computing** -  is the delivery of computing services over the internet. Because cloud computing uses the internet to deliver these services, it doesn’t have to be constrained by physical infrastructure the same way that a traditional datacenter is.

### Shared Responsibility Model

Physical security, power, cooling, and network connectivity are the responsibility of the cloud provider. At the same time, the consumer is responsible for the data and information stored in the cloud. The consumer is also responsible for access security, meaning you only give access to those who need it.

The shared responsibility model is heavily tied into the cloud service types: infrastructure as a service (IaaS), platform as a service (PaaS), and software as a service (SaaS).

## Types of Clouds

### Private Cloud

It’s a cloud (delivering IT services over the internet) that’s used by a single entity.  Private cloud provides much greater control for the company and its IT department. However, it also comes with greater cost and fewer of the benefits of a public cloud deployment.

### Public Cloud

A public cloud is built, controlled, and maintained by a third-party cloud provider. With a public cloud, anyone that wants to purchase cloud services can access and use resources. The general public availability is a key difference between public and private clouds.

### Hybrid Cloud

A hybrid cloud is a computing environment that uses both public and private clouds in an inter-connected environment. A hybrid cloud environment can be used to allow a private cloud to surge for increased, temporary demand by deploying public cloud resources. Hybrid cloud can be used to provide an extra layer of security. For example, users can flexibly choose which services to keep in public cloud and which to deploy to their private cloud infrastructure.

### Multi-Cloud

A fourth, and increasingly likely scenario is a multi-cloud scenario. In a multi-cloud scenario, you use multiple public cloud providers.

### Capital expenditure (CapEx)

CapEx is typically a one-time, up-front expenditure to purchase or secure tangible resources. A new building, repaving the parking lot, building a datacenter, or buying a company vehicle are examples of CapEx.

### Operational expenditure (OpEx)

OpEx is spending money on services or products over time. Renting a convention center, leasing a company vehicle, or signing up for cloud services are all examples of OpEx.

Cloud computing falls under OpEx because cloud computing operates on a consumption-based model. You pay for the IT resources you use. If you don’t use any IT resources this month, you don’t pay for any IT resources.

This consumption-based model has many benefits, including:

- No upfront costs.
- No need to purchase and manage costly infrastructure that users might not use to its fullest potential.
- The ability to pay for more resources when they're needed.
- The ability to stop paying for resources that are no longer needed.

### Benefits of high availability

When you’re architecting your solution, you’ll need to account for service availability guarantees. Azure is a highly available cloud environment with uptime guarantees depending on the service. These guarantees are part of the service-level agreements (SLAs).


### Benefits of Scalability

Scalability refers to the ability to adjust resources to meet demand. The other benefit of scalability is that you aren't overpaying for services. Scaling generally comes in two varieties: vertical and horizontal. Vertical scaling is focused on increasing or decreasing the capabilities of resources. Horizontal scaling is adding or subtracting the number of resources.

### Benefits of Reliability

Reliability is the ability of a system to recover from failures and continue to function. It's also one of the pillars of the Microsoft Azure Well-Architected Framework.

The cloud, by virtue of its decentralized design, naturally supports a reliable and resilient infrastructure. With a decentralized design, the cloud enables you to have resources deployed in regions around the world. With this global scale, even if one region has a catastrophic event other regions are still up and running.

### Benefits of Predictability

Predictability in the cloud lets you move forward with confidence. Predictability can be focused on performance predictability or cost predictability.