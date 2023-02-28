# Setting up Ansible
- Run `Vagrant up` to set up all 3 vm machines
- In each machine run the command `sudo apt update && upgrade -y` 
- `ssh` into your controller machine and install ansible. Below are the commands:
```
sudo apt-get install software-properties-common

sudo apt-add-repository ppa:ansible/ansible
# When running this, you might be prompted to ENTER mid-process. If so, pelase press ENTER

sudo apt-get update -y 

sudo apt-get install ansible -y

ansible --version
# to double-check the version of ansible
# although we did not install python, as it is one of the requirements for ansible, it installed it and it is using the default version (python 2.7)

cd etc/

cd ansible/

# this confirms that we have an Ansible Controller set up
```
- `ssh` into your web machine through your controller machine using the command `ssh vagrant@YOUR_IP`
- Exit back into your controller machine and go into the ansible folder `cd /etc/ansible/`
- Edit the `hosts` files to include the web and db ip addresses so when we ping them the controller can look for these in the host file.
- Save the new updated file and run the command `sudo ansible -m ping all`. This will check to see if a communication can be made between the controller and the other agent nodes.
![](./images/ping_pong.png)

## Potential blockers
- Sometime when trying to run the ping command and error may arise saying:
```
Using a SSH password instead of a key is not possible because Host Key checking is enabled and sshpass does not support this.  Please add this host's fingerprint to your known_hosts file to manage this host."
```
- In order to fix this we need to nano into the ansible.config file and include `host_key_checking = false`. After saving this change this will bypass the blocker and allow us to ping to the other agent nodes.