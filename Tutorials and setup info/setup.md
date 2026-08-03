# Post Ansible machine initial setup

This will be the steps to walk thour after the first boot of the ansible machine. In this example it is the midgard server, but this can be replicated among the others:

1. login
2. Open Firefox to download the google chrome deb file
3. install Google Chrome using the .deb file
4. update the operating system:
    - sudo apt update
    - sudo apt udgrade
5. Install Ansible using the built in repo
    - sudo apt install ansible
6. (incomplete) build the users out for ansible on the ansible machine, this needs to be done manuallly on each of the target servers using the user setup file
7. (incomplete) build the ansible playbook for the shell modifications and plugins