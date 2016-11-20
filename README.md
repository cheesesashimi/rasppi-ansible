# rasppi-ansible

These are just my Ansible playbooks for configuring Raspberry Pis, nothing special.

## Goal

Transform an out-of-the-box Raspbian image into something a bit more secure. To do this, I've elected to use Ansible since it was the best fit for my needs.

## Getting Started

1. Install Ansible on your platform of choice. On Mac:
   `$ brew install ansible`

2. Clone this repo:
   `$ git clone https://github.com/cheesesashimi/rasppi-ansible.git`

3. Install the upstream roles using Ansible Galaxy:
   `$ ansible-galaxy install -r requirements.yml`

4. Run the playbook! In this example, I'm supplying an IP address, but feel free to use an inventory file. I've elected to omit my inventory file because reasons:
   `$ ansible-playbook main.yml -i '192.168.1.100,' -k`

**Note:** You'll need the `-k` option for the initial run because your Raspbian installation does not yet have your SSH key installed, so you'll need to supply the default password for the `pi` user.

## Roles Used

My playbook makes extensive use of pre-existing Ansible roles available from Ansible Galaxy. Check out the repos below if you'd like more info:

- [mikolak.raspi-config](https://galaxy.ansible.com/mikolak/raspi-config/)
- [spk.ssh-secure](https://github.com/spk/ansible-ssh-secure)
- [ryanlelek.sshd](https://github.com/ryanlelek/ansible-role-sshd)
- [nickjj.fail2ban](https://github.com/nickjj/ansible-fail2ban)
