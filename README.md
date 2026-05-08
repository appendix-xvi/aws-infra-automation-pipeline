# 🛠️ Automation DevOps Lab

![Terraform Fmt](https://img.shields.io/badge/Terraform-formatted-623CE4?logo=terraform)
![Ansible Verified](https://img.shields.io/badge/Ansible-tested-darkgreen?logo=ansible)
![CI Pipeline](https://img.shields.io/badge/GitLab%20CI-pass-blueviolet?logo=gitlab)
![Open to Work](https://img.shields.io/badge/Open--to--Work-Yes-brightgreen?style=flat-square)

## 🚀 DevOps Automation Lab

This repository showcases **real DevOps automation** in a hybrid infrastructure setup, combining Infrastructure as Code, automated provisioning pipelines, configuration management, and observability — all tied together with deployable code.

> 🎯 Designed for hiring managers, engineers, and teams evaluating real-world DevOps skill sets

---

## 🔧 Key Features

| Capability                    | Tech Used                            |
|------------------------------|--------------------------------------|
| Infrastructure Provisioning  | Terraform (VPC, EC2, S3, RDS)         |
| Configuration Management     | Ansible (Nginx, Prometheus, Grafana) |
| Dynamic Inventory            | Ansible + Boto3 (EC2 sync)           |
| IaC Automation Pipeline      | GitLab CI/CD                         |
| Monitoring & Visualization   | Prometheus + Grafana                 |
| Documentation                | Markdown + Diagrams                  |

---

## 🆕 Feature 2026 Update (Reviewed)

This repository has been reviewed and updated with a practical **2026 feature direction** focused on production readiness:

- Add Terraform remote state + state locking (S3 + DynamoDB)
- Add environment separation (`dev`, `staging`, `prod`) with reusable modules
- Add security checks in CI (`tfsec`/`checkov`, `ansible-lint`)
- Add containerized monitoring stack option (Prometheus + Grafana via Docker Compose)
- Add GitOps-ready deployment path for Kubernetes expansion

> Goal for 2026: move from portfolio lab to a reusable baseline for team infrastructure delivery.

---

## 📁 Project Structure

```text
automation-devops-lab/
├── README.md
├── .gitlab-ci.yml
├── terraform/
│   ├── main.tf
│   ├── vpc.tf
│   ├── rds.tf
│   ├── s3.tf
│   └── variables.tf
├── ansible/
│   ├── site.yml
│   ├── prometheus_grafana.yml
│   └── aws_ec2_inventory.py
├── images/
│   ├── infra-deploy-flow.png
│   └── grafana-ui.png
```

---

## ⚙️ Use Case: End-to-End Infra Automation
This lab emulates a production-like flow:

- Code pushed → GitLab CI pipeline triggers
- Terraform provisions VPC, EC2, S3, and RDS
- Ansible installs Nginx, Prometheus, Grafana on EC2
- Dynamic Inventory auto-syncs EC2 IPs

---

## 🖥️ Live Output

| Tool       | Output Snapshot                                |
|------------|-------------------------------------------------|
| Terraform  | ✅ Applied Successfully (see outputs.tf)         |
| Ansible    | ✅ Configured Nginx, Prometheus, Grafana         |
| Grafana UI | ![grafana-ui](images/grafana-ui.png)            |

---

## 👀 Who Is This For?

- DevOps engineers/job seekers needing real, provable infrastructure work
- Recruiters who want to see hands-on, not just theory
- Anyone building a portfolio with live AWS/automation examples

---

## 🚀 Quick Start

### Prerequisites
- AWS Account & IAM Credentials
- Terraform / Ansible installed
- GitLab runner (self-hosted or SaaS)

### Commands
```bash
# Clone the repo
git clone https://github.com/Nuntin/automation-devops-lab.git
cd automation-devops-lab

# Terraform: provision infra
cd terraform
terraform init
terraform apply -auto-approve -var-file="terraform.tfvars"

# Ansible: configure EC2
cd ../ansible
chmod +x aws_ec2_inventory.py
ansible-playbook -i aws_ec2_inventory.py site.yml
ansible-playbook -i aws_ec2_inventory.py prometheus_grafana.yml
```

---

## ✅ Status
- Infrastructure: ✔️ Terraform-based (VPC, EC2, S3, RDS)
- Configuration: ✔️ Ansible Playbooks + Dynamic Inventory
- Monitoring: ✔️ Prometheus + Grafana auto-deploy
- IaC Pipeline: ✔️ GitLab CI (Terraform stages)
- Diagram: ✔️ draw.io visualized
- README: ✔️ English, structured, copyable

---

## 🎯 Why I Built This Lab
This project was built during a personal reset period — not to learn DevOps, but to rebuild it from first principles.

I didn't just write Terraform, Ansible, and CI pipelines — I verified each commit by applying it on real infrastructure.

It's my way of proving that even outside of a job, I never stopped building.

---

## 👤 About Me – DevOps Engineer (Open to Work)
Hi, I'm Nuntin – a DevOps / Infrastructure Engineer from Thailand 🇹🇭
Currently looking for new opportunities in the field of DevOps and Cloud Infrastructure.

- Terraform, Ansible, GitLab CI/CD, Docker, Kubernetes
- AWS: EC2, S3, IAM, RDS, VPC, CloudFront, Route53
- Real use-case demo → see this repo!

📦 GitHub: [github.com/Nuntin](https://github.com/Nuntin)

💼 LinkedIn: [linkedin.com/in/nuntin-padmadin-97b708145](https://www.linkedin.com/in/nuntin-padmadin-97b708145/)

📧 Email: nuntin.p@gmail.com

---

**SEO Keywords:**  
`devops portfolio`, `terraform ansible automation`, `gitlab ci k8s pipeline`, `real aws infrastructure`, `cloud automation`, `open to work devops`, `grafana monitoring lab`
---
