🌐 Multi-Region IIS Web App Deployment on Azure
📖 Project Overview

This project demonstrates deploying a secure, highly available IIS-based web application using Microsoft Azure services.
It includes:

Primary & Secondary IIS VMs for hosting the web app

Azure Application Gateway for load balancing and WAF security

Azure Firewall (optional) for centralized filtering

Azure Bastion for secure VM access without exposing RDP ports

Azure Traffic Manager for global DNS-based failover between regions

🏗️ Architecture
[ User ]  
   |  
[ Azure Traffic Manager ]  
   |----> [ App Gateway + IIS VM (Primary Region) ]  
   |----> [ App Gateway + IIS VM (Secondary Region) ]  

⚙️ Steps to Deploy

Create Resource Groups for primary and secondary regions.

Deploy IIS VM (Primary) and install IIS role.

Deploy IIS VM (Secondary) with the same configuration.

Configure Bastion for secure access.

Deploy Application Gateway with Public IP and backend pointing to IIS VMs.

(Optional) Deploy Azure Firewall for traffic filtering.

Configure Azure Traffic Manager with priority routing (Primary = Priority 1, Secondary = Priority 2).

Test deployment by accessing the Traffic Manager DNS name in a browser.

✅ Features

High availability with automatic failover

Secure VM access via Azure Bastion

Global reach with Traffic Manager

Layer-7 protection with Application Gateway (WAF)

🔗 How to Test

Copy the DNS name from Traffic Manager.

Paste it into your browser.

The site should load from the Primary IIS VM.

If the Primary is down, Traffic Manager routes to the Secondary VM.

📌 Future Improvements

Add SSL/TLS Certificates

Enable Azure Monitor for real-time logging

Automate deployment with ARM templates or Terraform

👩‍💻 Author

Vanshika – Cloud & Security Enthusiast 🚀
