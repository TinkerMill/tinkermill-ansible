# tinkermill-ansible

## Requirements to check-out and use this repository
- Linux
- Ansible 2.0.0.2+
- Git 2.7.4+
- sshpass 1.05
- Access to the TinkerMill network, either local or VPN

All of the above Requirements are met on the shell server *GOLEM* a.k.a. *10.2.0.54*.

## Requirements to check-in this repository
- All of the check-out requirements above
- SSH key configured and linked in GitHub
  - See [this link](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/) for instructions on creating your own SSH key
  - Ask the Executive Director to have your Github account linked

## Procedure to power on the test VMs
- Open a web browser
- Log into ProxMox via [hostname](https://vmhost2:8006/) or [IP address](https://10.2.0.19:8006/), with `root` credentials
- Find and power-on each virtual machine ending in `-test`

## Procedure to check out Ansible from GitHub
- Connect to *GOLEM* via SSH, PuTTY, or command-line:
  - `ssh golem` or `ssh 10.2.0.54` if on VPN
- Make a working directory if needed:
  - `mkdir -p ~/git/projects`
- Change to the working directory:
  - `cd ~/git/projects`  
- Check out a working copy of the repository:
  - `git clone https://github.com/TinkerMill/tinkermill-ansible.git`
- Change into the newly downloaded directory:
  - `cd tinkermill-ansible`
- Check the status of the repository:
  - `git status`

## Procedure to run Ansible playbooks
- Make sure each system in the testing inventory is online:
  - `ansible all -m ping`
- Make sure each system in the production inventory is online:
  - `ansible all -m ping -i production.ini`
- Perform a "dry-run" on the testing inventory:
  - `ansible-playbook site.yml --check --diff`
  - Watch for errors or incorrect changes
- If all's well, perform an actual run on the testing inventory:
  - `ansible-playbook site.yml`
- If all's well, perform an actual run on the production inventory:
  - `ansible-playbook site.yml -i production.ini`

## Explanation of Roles
- fwd-syslog: Reconfigure "rsyslog" to send syslogs to *GALATEA*
- install-cmkagent: Install the Check_MK agent
- install-omd: Install OMD/Check_MK RAW
- mkadmins: Set up important users and groups
- mksudo: Set up sudo for important users
- pmbauer.tarsnap: (from Ansible Galaxy) Install Tarsnap backup client
- shell-master: Configure a host to be a shell server
- syslog-receiver: Reconfigure "rsyslog" to receive syslogs
- tinkeraccess-server: Install TinkerAccess on a Raspberry Pi
- updates: Update APT packages 

Full details found in each role's README.md; for example `roles/fwd-syslog/README.md`
