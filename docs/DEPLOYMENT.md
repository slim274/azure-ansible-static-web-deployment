# Setup and deployment workflow

**Project:** Azure Multi-Play Static Website Deployment with Ansible

The workflow below summarizes the **actual steps described in the Week 12 report**. This package does not supply complete Terraform resources or Ansible playbooks; use the source files already present in your original project, check the provider version and variable values, and review planned changes prior to running against a cloud account.

### 1. Prepare the project

Create `inventory.ini`, `site.yml`, `README.md` and `files/index.html` in the local static website project.

### 2. Prepare content

The recorded lab downloaded `index.html` from the upstream Azure Static Website project; preserve attribution if reusing it.

### 3. Write the multi-play playbook

Play 1 installs/configures Nginx; Play 2 deploys static HTML using `copy`; Play 3 checks HTTP service availability with `uri`.

### 4. Run and verify

Activate the Ansible environment and run `ansible-playbook -i inventory.ini site.yml`. Test both web server URLs.

## Before rerunning

1. Confirm current credentials, SSH public key and intended cloud account/region.
2. Replace the historical public IPs with fresh Terraform outputs and update the Ansible inventory.
3. Do not place database passwords, tokens or private keys inside files committed to GitHub.
4. Run appropriate linting/syntax checks and validate configuration before applying changes.
5. Destroy unused lab cloud resources after collecting necessary proof to prevent unplanned charges.
