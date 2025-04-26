# Azure virtual networks

Azure virtual networks and virtual subnets enable Azure resources, such as VMs, web apps, and databases, to communicate with each other, with users on the internet, and with your on-premises client computers. You can think of an Azure network as an extension of your on-premises network with resources that link other Azure resources.

Azure virtual networking supports both public and private endpoints to enable communication between external or internal resources with other internal resources.

A VNet is the fundamental networking resource in Azure.

It defines a private network boundary in Azure for your resources (VMs, databases, app services, etc.).

It has:

- A name (e.g., learn-vnet)
- A location (e.g., East US)
- An address space (e.g., 10.0.0.0/16) — the IP range available inside the network.

A VNet is a top-level resource — it appears in the Resource Group directly.

## Compararison with AWS VPC


| Feature / Concept            | AWS VPC (Virtual Private Cloud)        | Azure VNet (Virtual Network)                 |
|-----------------------------|-----------------------------------------|----------------------------------------------|
| Network isolation           | VPC                                     | VNet                                          |
| Subnets                    | Subnets                                 | Subnets                                       |
| Route tables               | Route Tables                            | User-defined Routes (UDRs)                   |
| Security filtering         | Security Groups, NACLs                  | Network Security Groups (NSGs)               |
| Internet gateway           | Internet Gateway                        | Internet Gateway (default)                   |
| NAT                        | NAT Gateway, NAT Instances              | NAT Gateway                                   |
| VPN support                | AWS VPN                                 | Azure VPN Gateway                             |
| Private link/service       | VPC Endpoint, PrivateLink               | Private Endpoint, Private Link                |
| Peering                    | VPC Peering                             | VNet Peering                                  |
| DNS                        | AmazonProvidedDNS, Route 53             | Azure-provided DNS, Azure DNS                |
| IP addressing              | CIDR-based, IPv4/IPv6                   | CIDR-based, IPv4/IPv6                         |
| Hybrid connectivity        | Direct Connect                          | ExpressRoute                                   |


## Subnets

- A **Subnet** is a **child object** inside a VNet.
- Divides the VNet into smaller address spaces.
- Properties:
  - **Name** (e.g., `learn-subnet`)
  - **Address Prefix** (e.g., `10.0.1.0/24`)
- **Subnets are not top-level resources**.
  - You **view/manage them inside the VNet** (`Settings → Subnets`).
- **Inheritance:**
  - **Inherits** location from the VNet.
  - **Does not inherit** resource group name — must be manually provided.
