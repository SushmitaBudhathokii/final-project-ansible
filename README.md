# Two-Tier Web Application Automation with Terraform, Ansible, and GitHub Actions
## Ansible Component

This directory contains **Ansible configurations** used to install and configure `httpd` (Apache) on EC2 webservers that are provisioned using Terraform.

---

## Prerequisites

Before running the Ansible playbook, ensure the following are ready:

1. **EC2 Instances Provisioned with Terraform**  
   - Ensure that your network and webserver infrastructure have already been deployed using Terraform (as detailed in the Terraform component README).

2. **Ansible Installed**  
     ```bash
     sudo yum install -y ansible  # On Amazon Linux
     
3. **Inventory Configuration**  
   - If you are using a static inventory file like `aws_ec2.yaml`, ensure it points to the correct tag of the webservers.


## Playbook Overview

The `playbook.yaml` installs and configures Apache on the target EC2 instances.


## How to Run the Ansible Playbook

Run the playbook using the inventory file:

```bash
ansible-playbook -i aws_ec2.yaml playbook.yaml
```

---

## Post-Deployment

Once the playbook completes:
- Visit the DNS of Application load balancer in your browser:  
  `http://<public-ip>`  
  You should see the Apache custom page`index.html`.

---

## Cleanup Instructions

After infrastructure validation:
- You can tear down the EC2 infrastructure using the **Terraform destroy** commands.
- No cleanup is required for Ansible itself.

