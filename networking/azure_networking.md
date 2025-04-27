# Azure Networking

## Network Security Groups (NSG)

- **Definition**: A **Network Security Group (NSG)** acts as a **firewall** for controlling inbound and outbound traffic at the **subnet** or **network interface (NIC)** level. It filters traffic based on rules you define.

- **Default Behavior**:
  - **Inbound traffic** is **denied** by default, unless explicitly allowed.
  - **Outbound traffic** is **allowed** by default, unless explicitly denied.

- **Rule Definition**: Each rule in an NSG specifies:
  - **Direction**: Inbound or outbound.
  - **Action**: Allow or Deny.
  - **Protocol**: TCP, UDP, etc.
  - **Port Range**: Specific ports (e.g., 22 for SSH).
  - **Source & Destination**: IP addresses or CIDR blocks


### Association of NSGs

- **NSG on Subnet**:
  - When you associate an NSG to a **subnet**, **all** the resources (VMs, NICs) inside that subnet inherit the NSG rules. This provides **broad control** over all resources in that subnet.
  - **Use Case**: Apply uniform security rules to all VMs in a subnet (e.g., allow SSH for all VMs).

- **NSG on Network Interface (NIC)**:
  - When you associate an NSG to a **NIC**, it only applies to **that specific NIC** (and the associated VM). This provides **fine-grained control** over specific VMs.
  - **Use Case**: Define different rules for different VMs, even within the same subnet (e.g., allow SSH for one VM, block it for another).

- **Both Together**:
  - **Subnet NSG + NIC NSG** = The traffic must pass through **both** NSGs (if both exist). **Both NSGs** are evaluated, and if either denies traffic, the packet is dropped.
  - **Layered Protection**: Subnet NSGs provide broad coverage, while NIC NSGs offer detailed protection.


### NSG Traffic Processing

- Traffic is evaluated first by the **Subnet NSG** (if one is assigned), and then by the **NIC NSG** (if one is assigned).
  - **Example Flow**:
    - **Internet → Subnet NSG → NIC NSG → VM** (if both NSG rules allow)
    - If **either** NSG denies the traffic, it is blocked.

### Azure Default NSG Outbound Rules
  
| Rule | Direction | Protocol | Source | Destination | Port | Action |
|:---|:---|:---|:---|:---|:---|:---|
| AllowVnetOutbound | Outbound | Any | VirtualNetwork | VirtualNetwork | Any | Allow |
| AllowInternetOutbound | Outbound | Any | VirtualNetwork | Internet | Any | Allow |
| DenyAllOutbound | Outbound | Any | Any | Any | Any | Deny |

- **Default behavior**: All outbound traffic is allowed unless explicitly denied.
