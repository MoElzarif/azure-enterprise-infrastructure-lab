# Lessons Learned

This project helped me practice building and documenting a small enterprise-style infrastructure environment in Microsoft Azure.

The lab included networking, virtual machines, subnet segmentation, Network Security Groups, monitoring, and backup.

---

## 1. Resource Organization

I learned why it is important to keep related Azure resources inside a dedicated resource group.

Using a single resource group made it easier to:

- Track all project resources
- Understand the full environment
- Review costs
- Manage dependencies
- Clean up the lab when finished

This is important because cloud environments can become difficult to manage if resources are spread across different locations without clear organization.

---

## 2. Virtual Network Planning

I learned how to design a virtual network with multiple subnets for different workload types.

The lab used separate subnets for:

- Web workloads
- Server workloads
- Management workloads

This helped me understand how subnet segmentation improves security and organization.

Instead of placing every virtual machine in the same subnet, each subnet should have a clear purpose.

---

## 3. Subnet Placement Matters

One of the most important lessons from this lab was that the actual Azure build must match the architecture design.

The Linux web server belongs in the web subnet because it hosts the public Nginx site.

The Windows Server VM belongs in the management subnet because it is used for administration and server management.

This made the final design cleaner and more realistic.

---

## 4. Network Security Groups

I learned how Network Security Groups control traffic to Azure resources.

The lab used NSGs to:

- Allow HTTP traffic to the Linux web server
- Restrict SSH access to an admin IP
- Restrict RDP access to an admin IP
- Separate security rules by subnet

This helped me understand the principle of least privilege.

Only the required ports should be exposed, and administrative access should not be open to everyone.

---

## 5. Public and Private IP Addresses

This lab helped me understand the difference between public and private IP addresses.

Private IP addresses are used for communication inside the virtual network.

Public IP addresses allow access from the internet.

I also learned that public IPs should be used carefully because they increase exposure if security rules are not configured correctly.

---

## 6. Linux Web Server Deployment

I learned how to deploy a Linux virtual machine and install Nginx to host a simple web page.

This helped me connect multiple cloud concepts together:

- Linux VM deployment
- Subnet placement
- Public IP access
- HTTP traffic
- NSG rules
- Web server testing

Seeing the Nginx website load in a browser confirmed that the web server, public IP, and NSG rule were working together.

---

## 7. Windows Server Deployment

I learned how to deploy a Windows Server VM in Azure and place it inside a management subnet.

This helped me understand how Windows Server can be used in cloud administration environments.

I also learned that RDP should be restricted to a trusted admin IP instead of being open to the public internet.

---

## 8. Monitoring

I learned how Azure Monitor can be used to track virtual machine performance.

The high CPU alert helped me understand how administrators can detect performance issues before they become bigger problems.

Monitoring is important because cloud resources need visibility, especially when they are running production workloads.

---

## 9. Backup and Recovery

I learned how Azure Backup protects virtual machines using a Recovery Services Vault.

The backup configuration helped me understand:

- Backup policies
- Protected items
- Recovery points
- Backup status
- Restore readiness

This is important because administrators need to plan for failure and recovery.

---

## 10. Documentation

I learned that building the environment is only part of the project.

Good documentation is what makes the project understandable to other people.

For a portfolio project, screenshots, explanations, and clear deployment steps are important because they prove what was built and why it was built.

---

## 11. Professional Portfolio Presentation

This project helped me understand that a GitHub portfolio should not only show screenshots.

It should also explain:

- The goal of the project
- The architecture
- The security design
- The deployment process
- The proof/evidence
- The lessons learned
- Future improvements

This makes the project easier for recruiters, hiring managers, and technical reviewers to understand.

---

## Summary

This lab improved my understanding of Azure administration, networking, security, monitoring, backup, and technical documentation.

The biggest lesson was that a cloud project should be built correctly, documented clearly, and supported with evidence.
