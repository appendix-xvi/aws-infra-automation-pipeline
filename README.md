# AWS Infrastructure Automation Pipeline

A DevOps lab for practicing AWS infrastructure automation with Terraform, Ansible, and GitLab CI/CD.

This repository is intended as a portfolio project, but it is still a lab baseline rather than a production-ready AWS landing zone. The goal is to show a repeatable infrastructure delivery flow without committing real credentials or account-specific configuration.

## What this project demonstrates

- Terraform-based AWS infrastructure provisioning
- Ansible-based EC2 configuration workflow
- GitLab CI/CD stages for planning and configuration
- Basic monitoring stack positioning with Prometheus and Grafana
- Documentation for safe lab usage and future hardening

## Architecture flow

```text
GitLab CI/CD
  -> Terraform init/plan
  -> manual Terraform apply
  -> Ansible inventory/configuration
  -> monitoring validation
```

## Repository structure

```text
aws-infra-automation-pipeline/
├── README.md
├── .gitlab-ci.yml
├── terraform/
├── ansible/
└── docs/
```

The exact folder contents should be kept in sync with the repository. Do not document files that are not committed.

## Prerequisites

- AWS account for lab usage
- AWS credentials with limited lab permissions
- Terraform installed locally or available in the CI runner
- Ansible installed locally or available in the CI runner
- GitLab project with CI/CD enabled

## Local validation

From the repository root:

```bash
cd terraform
terraform init -input=false
terraform plan
```

Run Ansible only after Terraform has produced reachable EC2 targets or after you have prepared an inventory file:

```bash
cd ../ansible
ansible-playbook -i aws_ec2_inventory.py site.yml
```

## GitLab CI/CD behavior

The pipeline should be treated as a controlled infrastructure workflow:

1. `terraform_plan` generates a Terraform plan.
2. `terraform_apply` must be manual before it changes AWS resources.
3. `ansible_configure` should run only after infrastructure is available.

Production-style automation should never auto-apply infrastructure from every commit.

## Required CI/CD variables

Use GitLab protected/masked variables where possible:

```text
AWS_ACCESS_KEY_ID
AWS_SECRET_ACCESS_KEY
AWS_DEFAULT_REGION
```

For real usage, prefer short-lived credentials or OIDC federation instead of long-lived static access keys.

## Validation checklist

Before showing this repository as portfolio work, verify:

- Terraform formatting passes.
- Terraform plan runs without local-only assumptions.
- Apply is manual in CI.
- Ansible inventory source is documented.
- No real credentials, private keys, or account-specific secrets are committed.

## Current limitations

- This is a lab repository, not a hardened production AWS baseline.
- IAM policies, network exposure, state backend, and secret handling need review before real usage.
- Remote state and state locking should be added before shared-team usage.

## Future improvements

- Terraform remote state with S3 and DynamoDB locking
- Separate dev/staging/prod inputs
- CI checks for `terraform fmt`, `terraform validate`, Checkov, and Ansible lint
- OIDC-based GitLab-to-AWS authentication
- More explicit monitoring validation steps

## License

MIT
