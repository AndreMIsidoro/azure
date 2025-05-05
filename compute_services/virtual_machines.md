# Azure Virtual Machines

With Azure Virtual Machines (VMs), you can create and use VMs in the cloud. VMs provide infrastructure as a service (IaaS) in the form of a virtualized server and can be used in many ways. Just like a physical comp:uter, you can customize all of the software running on your VM.

VMs are an ideal choice when you need:

- Total control over the operating system (OS).
- The ability to run custom software.
- To use custom hosting configurations.


## Comparison with EC2

| Feature / Concept            | AWS EC2                                 | Azure Virtual Machines                        |
|-----------------------------|------------------------------------------|-----------------------------------------------|
| Compute service name        | EC2 (Elastic Compute Cloud)             | Azure Virtual Machines (VMs)                  |
| Preconfigured images        | AMIs (Amazon Machine Images)            | Azure Marketplace Images                      |
| Instance scaling            | Auto Scaling Groups (ASG)               | Virtual Machine Scale Sets (VMSS)             |
| On-demand pricing           | On-Demand Instances                     | Pay-as-you-go VMs                             |
| Spot/low-priority pricing   | EC2 Spot Instances                      | Azure Spot VMs                                |
| Reserved capacity           | Reserved Instances                      | Reserved Virtual Machines                     |
| Dedicated hardware          | EC2 Dedicated Hosts                     | Azure Dedicated Hosts                         |
| Metadata service            | EC2 Instance Metadata Service           | Azure Instance Metadata Service               |
| User data on launch         | User Data scripts                       | Custom Data (cloud-init)                      |
| Load balancing              | Elastic Load Balancer (ELB)             | Azure Load Balancer / Application Gateway     |
| Networking                  | VPC, Security Groups, Elastic IPs       | Virtual Network (VNet), NSGs, Public IPs      |
| CLI / SDK                   | AWS CLI, Boto3                          | Azure CLI, Azure SDK                          |



### Virtual machine scale sets

Scale sets allow you to centrally manage, configure, and update a large number of VMs in minutes. The number of VM instances can automatically increase or decrease in response to demand, or you can set it to scale based on a defined schedule. Virtual machine scale sets also automatically deploy a load balancer to make sure that your resources are being used efficiently.

### Virtual machine availability sets

Virtual machine availability sets are another tool to help you build a more resilient, highly available environment. Availability sets are designed to ensure that VMs stagger updates and have varied power and network connectivity, preventing you from losing all your VMs with a single network or power failure.

Availability accomplish these objectives by grouping VMs in two ways: update domain and fault domain.

- **Update domain**: The update domain groups VMs that can be rebooted at the same time. This setup allows you to apply updates while knowing that only one update domain grouping is offline at a time. All of the machines in one update domain update.
- **Fault domain**: The fault domain groups your VMs by common power source and network switch. By default, an availability set splits your VMs across up to three fault domains.


## Create An Azure VM

You can define and deploy VMs on Azure in several ways: the Azure portal, a script (using the Azure CLI or Azure PowerShell), or through an Azure Resource Manager template.

### Resources used in a Windows VM

When creating a Windows VM in Azure, you also create resources to host the VM. These resources work together to virtualize a computer and run the Windows operating system. These must either exist (and be selected during VM creation), or they'll be created with the VM.

- A virtual machine that provides CPU and memory resources.
- An Azure Storage account to hold the virtual hard disks.
- Virtual disks to hold the OS, applications, and data.
- A virtual network (VNet) to connect the VM to other Azure services or your own on-premises hardware.
- A network interface to communicate with the VNet.
- A public IP address so you can access the VM (this is optional).

Like other Azure services, you'll need a resource group to contain the VM (and optionally group these resources together for administration). When you create a new VM, you can either use an existing resource group or create a new one.

### Choose the VM Image

Selecting an image is one of the first and most important decisions you'll make when creating a VM. An image is a template that's used to create a VM. These templates include an OS and often other software, such as development tools or web-hosting environments.

### Size your VM

Just as a physical machine has a certain amount of memory and CPU power, so does a virtual machine. Azure offers a range of VMs of differing sizes at different price points. The size that you choose will determine the VM's processing power, memory, and max storage capacity.

VM sizes are grouped into categories, starting with the B-series for basic testing, and running up to the H-series for massive computing tasks. You should select the VM's size based on the workload you want to perform. It's possible to change a VM's size after it's been created, but the VM must be stopped first. So it's best to size it appropriately from the start if possible.

### Choose storage options

The next set of decisions revolves around storage. First, you can choose the disk technology. Options include a traditional platter-based hard disk drive (HDD) or a more modern solid-state drive (SSD). Just like the hardware you purchase, SSD storage costs more, but provides better performance.

### Map Storage to Disks


Azure uses virtual hard disks (VHDs) to represent physical disks for the VM. VHDs replicate the logical format and data of a disk drive, but are stored as page blobs in an Azure Storage account. You can choose on a per-disk basis what type of storage it should use (SSD or HDD). This allows you to control each disk's performance, likely based on the I/O you plan to perform on it.

By default, two virtual hard disks (VHDs) will be created for your Windows VM:

The Operating System disk: This is your primary or C: drive and has a maximum capacity of 2048 GB.

A Temporary disk: This provides temporary storage for the OS or any apps. It's configured as the D: drive by default and is sized based on the VM size, making it an ideal location for the Windows paging file.

You can store data on the C: drive along with the OS, but a better approach is to create dedicated data disks. You can create and attach additional disks to the VM. Each data disk can hold up to 32,767 gibibytes (GiB) of data, with the maximum amount of storage determined by the VM size you select.

### Network Communication

Virtual machines communicate with external resources using a virtual network (VNet). The VNet represents a private network in a single region on which your resources communicate. A virtual network is just like the networks you manage on-premises. You can divide them up with subnets to isolate resources, connect them to other networks (including your on-premises networks), and apply traffic rules to govern inbound and outbound connections.

Having Azure create the network together with the VM is simple, but it's likely not ideal for most scenarios. It's better to plan your network requirements up front for all the components in your architecture, and create the VNet structure you'll need separately. Then create the VMs, and place them into the already-created VNets.
