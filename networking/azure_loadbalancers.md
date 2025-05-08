# Azure Load Balancers

## Backend Pool

A Backend Pool in Azure Load Balancer is a collection of resources (typically VMs or VMSS instances) that are targeted by the Load Balancer to route traffic to. These resources (VMs, VMSS) can be in different availability zones and can have private IPs or public IPs.


### How Does the Backend Pool Work?

Traffic Flow: When a client makes a request to the Load Balancer (via the frontend IP), the Load Balancer distributes that traffic to one of the VMs or instances in the backend pool based on the load balancing rules you've defined.

Health Probes: To ensure that traffic is only sent to healthy VMs, the Load Balancer regularly checks the health of the backend pool members using health probes. If a VM is determined to be unhealthy (e.g., it’s not responding to health probes), the Load Balancer will stop sending traffic to that VM until it becomes healthy again.

Scalability: Backend Pools allow the system to scale horizontally by adding more VMs or VMSS instances to the backend pool without changing the Load Balancer configuration.

## Load Balancer Rules

These rules define how the Azure Load Balancer will route incoming traffic to the backend pool based on certain conditions, such as the protocol and port.

For example, if you want to route HTTP traffic on port 80 to the backend pool, you would define a load balancing rule that specifies the frontend IP, frontend port, backend pool, and health probe.