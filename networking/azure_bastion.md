# Azure Bastion

## Overview

Azure Bastion is a fully managed Platform-as-a-Service (PaaS) by Microsoft that allows you to securely access virtual machines (Linux/Windows) using your browser over HTTPS, without exposing public IPs or SSH/RDP ports.

Instead of opening port 22 (SSH) or 3389 (RDP) on your VMs: Azure Bastion deploys into a dedicated subnet inside your VNet (AzureBastionSubnet). It uses a public IP to expose a web-based SSH/RDP interface through the Azure Portal and connects to your private VMs over the internal VNet network