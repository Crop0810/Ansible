# Setup the Ansible user

Setup a new user for ansible to use, this needs to be done on all target machines plus the ansible host if the host needs to be updated

sudo adduser $username

Add the gorup that will be used for the sudo commands on each of the machines as well

sudo groupadd $Groupname

Update the sudo file by typing in

sudo visudo

Add the below lines to the sudo file

# Allow provisioning group to execute any command without password
%$groupname ALL=(ALL) NOPASSWD:ALL


The password will need updating for bitwarden, but for now, just create a password

Create a SSH key so it can connect:

ssh-keygen -t ed25519 -C "Ansible Key" -f ~/.ssh/id_ed25519_ansible

Edit the SSH config file

sudo nano ~/.ssh/config

Add in lines for the connection to use the specifc user to connect to each server

Start the SSH Agent

eval $(ssh-agent)

Copy the SSH key across to each of the servers

ssh-add $key location
ssh-copy-id -i ~/.ssh/id_ed25519_ansible $username@$server