# Asible BDE iPXE Server Automation
The purpose of this project is to use Ansible to automate the creation of an iPXE server that serves Blancco Driver Eraser ISOs.

On your target machine, it will deploy a dhcp server, a tftp server, a web server, and route traffic from one network interface through the other. It will also copy the necessary pxe files and create an iPXE menu from a template.

## Prerequisites
- Network
- Server
- Ansible controller

## S