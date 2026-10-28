# Personal portfolio deployment with Ansible

Historical 2018 project for provisioning a DigitalOcean droplet and deploying a personal portfolio website in an Nginx Docker container.

`start.yml` creates a CentOS 7 droplet in London, adds it to the in-memory `online` inventory, and applies the EPEL, pip, Docker, and container roles. The bundled portfolio is under `roles/container/files/site/`. `digitalocean.yml` is an alternative provisioning-only playbook.

## Credentials

Supply a DigitalOcean token through the `DO_API_TOKEN` environment variable in the shell running Ansible. Obtain it from a local secret manager or enter it locally; never put it in a playbook, committed file, or command example. SSH authentication uses your local `~/.ssh/id_rsa` key; only its public key is registered with DigitalOcean.

Previously committed credentials and backup HTML were removed from branch history during the October 2026 cleanup. Revoke the exposed DigitalOcean token and review the Google Maps key previously included in the template backup. Removing a credential from Git does not revoke it or remove copies held elsewhere.

## Project status

This is historical example code, not a current deployment recipe. Review the operating system, Ansible modules, dependencies, and Nginx configuration before using it. The website copy task is commented out, the container port mapping contains `433` instead of `443`, and the Nginx configuration references PHP and TLS files that this playbook does not provision. Running the playbooks can create billable cloud resources.
