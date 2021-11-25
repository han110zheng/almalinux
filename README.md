# almalinux-deploy
An EL to AlmaLinux migration tool.

# Usage
In order to convert your EL8 operating system to AlmaLinux do the following:

# Make a backup of the system. We didn't test all possible scenarios so there is a risk that something goes wrong. In such a situation you will have a restore point.
## Download the almalinux-deploy.sh script:
$ curl -O https://raw.githubusercontent.com/AlmaLinux/almalinux-deploy/master/almalinux-deploy.sh
##Run the script and check its output for errors:
$ sudo bash almalinux-deploy.sh
  ...
  Migration to AlmaLinux is completed
Ensure that your system was successfully converted:
# check release file
$ cat /etc/redhat-release 
AlmaLinux release 8.4 (Electric Cheetah)

# check that the system boots AlmaLinux kernel by default
$ sudo grubby --info DEFAULT | grep AlmaLinux
title="AlmaLinux (4.18.0-305.el8.x86_64) 8.4"
Thank you for choosing AlmaLinux!
Roadmap
 CentOS 8 support.
 Write debug information to a log file for failed migration analysis.
 Oracle Linux 8 support.
 RHEL 8 support.
 Rocky Linux 8 support.
 DirectAdmin control panel support.
 cPanel control panel support.
 Plesk control panel support.
 Cover all common scenarios with tests.
 Add OpenNebula support to Molecule test suite.
Get Involved
Any contribution is welcome:

Find and report bugs.
Submit pull requests with bug fixes, improvements and new tests.
Test it on different configurations and share your thoughts in discussions.
Technology stack:

The migration script is written in Bash.
We use Bats for unit tests.
Functional tests are implemented using Molecule, Ansible and Testinfra. Virtual machines are powered by Vagrant and VirtualBox.
To run the functional tests do the following:

Install Vagrant and VirtualBox.
Install requirements from the requirements.txt file.
Run molecule test --all in the project root.
License
Licensed under the GPLv3 license, see the LICENSE file for details.
