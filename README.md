# Asible BDE iPXE Server Automation
The purpose of this project is to use Ansible to automate the creation of an iPXE server that serves Blancco Driver Eraser ISOs.

On your target machine, it will deploy a dhcp server, a tftp server, a web server, and (optionally) route traffic from one network interface through the other if desired. It will also copy the necessary pxe files and create an iPXE menu from a template.

## Prerequisites
- Network
  - OPTION 1: VLAN with internet access, but no DHCP server
  - OPTION 2: VLAN with no internet access or dhcp server (will require 2 NICs on server)
- Server (currently only Debian supported)
- Ansible controller
- User on Server with passwordless sudo access
- SSH key access from Ansible controller to User on Server

## Setup:
1. Clone the repository onto your Ansible controller
2. Copy your ISOs into the ISO folder
3. Copy/rename vars-example.yml to vars.yml and set the variables appropriately
4. Copy/rename inventory-example.yml to inventory.yml and set your host ip/hostname and the name of the user on the server with passwordless sudo access

## Run:
- To fully setup the server, use the command `ansible-playbook -i inventory.yml pxeserver.yml`
- To skip checking server settings and just update the ISOs, use the command `ansible-playbook -i inventory.yml update-iso.yml`
- To undo the server setup and start over, use the command `ansible-playbook -i inventory.yml reset.yml`