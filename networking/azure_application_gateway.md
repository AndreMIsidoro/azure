# Azure Application Gateway

## Overview

Azure Application Gateway is a layer 7 (HTTP/HTTPS) load balancer and application delivery controller that helps route traffic intelligently to your backend applications.

It goes beyond basic load balancing — it understands HTTP, HTTPS, URLs, cookies, headers, etc., and can make routing decisions based on that information.

## Key Features

1. Layer 7 Load Balancing
Can route traffic based on URL path, host name, query strings, etc.

Example: Route /jenkins to one backend pool, /nextcloud to another.

2. SSL Termination
You can upload SSL certificates to terminate HTTPS traffic at the gateway.

Offloads SSL decryption from backend servers (improves performance).

3. Web Application Firewall (WAF)
Optional tier that protects apps from common attacks (OWASP rules).

Includes protections like SQL injection, XSS, etc.

4. URL-based Routing (Path-based Routing)
Define routing rules based on the path of the URL.

Example: app.contoso.com/api/* → API backend, app.contoso.com/web/* → web frontend.

5. Host-Based Routing
Route requests by host header — e.g., jenkins.azurewebsites.net vs nextcloud.azurewebsites.net.

6. Session Affinity (Sticky Sessions)
Supports cookie-based affinity so clients stay connected to the same backend instance.

7. Autoscaling
Scales out/in automatically based on traffic volume (Standard_v2 and WAF_v2).


## Key Components

| Component                 | Description                                                    |
| ------------------------- | -------------------------------------------------------------- |
| **Frontend IP**           | Public or private IP that accepts traffic.                     |
| **Listener**              | Listens on a specific IP + port + protocol (e.g., HTTPS:443).  |
| **Backend Pool**          | Group of backend servers (VMs, containers, etc.).              |
| **HTTP Settings**         | How AG communicates with backend (HTTP/HTTPS, port, timeouts). |
| **Routing Rules**         | Logic that binds listener → backend pool via HTTP settings.    |
| **Probes**                | Health checks to decide if a backend is "up".                  |
| **WAF Policy (optional)** | Security policies to block malicious requests.                 |

## Common Use Cases

Hosting multiple apps under a single IP with domain/path routing.

Load balancing traffic across VMs, VMSS, containers.

Securing apps with WAF + HTTPS.

Central SSL certificate management.

Serving internal-only applications via private frontend IP.