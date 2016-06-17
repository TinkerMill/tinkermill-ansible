# tinkermill-ansible

## Requirements
- Linux
- Ansible 2.0.0.2+
- Git 2.7.4+
- sshpass 1.05
- Access to the TinkerMill network, either local or VPN
- To check-in: SSH key configured in GitHub

## Procedure to run Ansible
- In a web browser, power on the test VMs in ProxMox:
  - https://vmhost:8006/
  - Find and power-on `talos-test` and `galatea-test`  
- On your local Linux system, verify the application versions:
  - `ansible --version`
  - `git --version`
  - `sshpass -V`
- Check out a working copy of the repository:
  - `git clone https://github.com/TinkerMill/tinkermill-ansible.git`
- Change into the newly downloaded directory:
  - `cd tinkermill-ansible`
- Verify that the testing inventory is visible:
  - `ansible-playbook site.yml --list-hosts`
- Verify that the testing inventory is visible:
  - `ansible-playbook site.yml --list-hosts`
- Verify credentials to remote systems, and add remote SSH host key:
  - `ssh galatea-test`
  - `ssh talos-test`  
- Generate a local SSH key:  
  - `ssh-keygen -i ~/.ssh/id_rsa`
- Copy the local SSH key public data to each remote host:
  - `ssh-copy-id -i ~/.ssh/id_rsa galatea-test`  
  - `ssh-copy-id -i ~/.ssh/id_rsa talos-test`  
  - `ssh-copy-id -i ~/.ssh/id_rsa galatea`  
  - `ssh-copy-id -i ~/.ssh/id_rsa talos`  
  - `ssh-copy-id -i ~/.ssh/id_rsa vmhost`
  - ...  
- Perform a "dry-run" and watch for errors or incorrect changes:
  - `ansible-playbook site.yml --check --diff`
- If all's well, perform an actual run on the testing inventory:
  - `ansible-playbook site.yml`
- If all's well, perform an actual run on the production inventory:
  - `ansible-playbook site.yml -i production.ini`
