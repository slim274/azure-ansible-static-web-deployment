# Security and safe GitHub publication

This repository is intended as a public portfolio of a historical lab. The included images have been extracted from a Word document and **require an additional privacy review before publication**.

## Files to exclude from source control

```gitignore
# Terraform
.terraform/
*.tfstate
*.tfstate.*
*.tfvars
*.tfvars.json
*.tfplan
crash.log

# Credentials / local environment
.env
.env.*
*.pem
*.key
id_rsa
id_ed25519
*.p12
*.pfx
.venv/
venv/
__pycache__/

# Common application build artifacts
node_modules/
dist/
```

Terraform `.terraform.lock.hcl` is normally safe and useful to commit. Local `ansible.cfg`, playbooks, template files and Ansible inventories require review for credential content, public IPs and assumptions about network access.

## Before pushing

1. Inspect local Terraform/Ansible/application source and staged Git content for hardcoded passwords and access keys.
2. Inspect screenshots for cloud account/subscription IDs, email addresses, authentication tokens and user-specific secrets. Obscure sensitive details without altering claims of deployment success.
3. Remove any accidentally tracked state files and private keys from the index; if a secret was ever published, rotate it and assess Git history exposure.
4. Prefer Terraform variables and secret managers for passwords. Marking a value `sensitive = true` does not remove it from Terraform state.
5. Use the original repository for application attribution; do not imply that an upstream training app was authored by the deployment implementer.
6. Do not paste historical IP addresses into reusable production commands. Verify new endpoints each time.

## Limitations

The reported training lab's description does not by itself demonstrate encryption at rest, HTTPS, high availability, backups or independent production security testing.
