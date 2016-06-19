# tinkermill-ansible

## Requirements
- Linux
- Ansible 2.0.0.2+
- Git 2.7.4+
- sshpass 1.05
- Access to the TinkerMill network, either local or VPN
- To check-in: SSH key configured in GitHub

All of the above Requirements are met on the shell server *GOLEM* at 10.2.0.54.

## Procedure to power on the test VMs
- In a web browser, power on the test VMs in ProxMox:
  - https://vmhost:8006/
- Find and power-on each VM ending in `-test`

## Procedure to check out Ansible from GitHub
- Connect to *GOLEM* via SSH, via PuTTY or command-line:
  - `ssh golem` or `ssh 10.2.0.54` if on VPN
- Make a working directory if needed:
  - `mkdir -p ~/git/projects`
- Change to the working directory:
  - `cd ~/git/projects`  
- Check out a working copy of the repository:
  - `git clone https://github.com/TinkerMill/tinkermill-ansible.git`
- Change into the newly downloaded directory:
  - `cd tinkermill-ansible`

## Procedure to run Ansible playbooks  
- Perform a "dry-run" and watch for errors or incorrect changes:
  - `ansible-playbook site.yml --check --diff`
- If all's well, perform an actual run on the testing inventory:
  - `ansible-playbook site.yml`
- If all's well, perform an actual run on the production inventory:
  - `ansible-playbook site.yml -i production.ini`
