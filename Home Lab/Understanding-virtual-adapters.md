# Virtual adapters

## Overview 

There are normally three types of virtual adapters. NAT, bridged, and Host-only

**Bridged**
Bridged adapters connect 'directly' to the same network that your host is connected to. Think of it like plugging an ethernet cable into the VM. If you want to be able to access services on the VM without port-forwarding and need the VM to have an internet connection, you should choose this method. A physical adapter is required for this option to work. 

Recommended for:
- General VM usage.
- VMs that have web services.
- VMs you want to ssh into. 

**NAT**
NAT or Network Address Translation shares your host computer's IP address and creates a virtual network. To connect to services on the VM you would need to port-forward the required port and access them with your host computer's IP. EG: http://<YOUR COMPUTER IP>:<FORWARDED PORT>. If you do not need to access services on the VM or need to share a VPN connection that your host is connected to, then choose this method. A physical adapter is required for this option to work.

Recommended for:
- Sharing host VPN connection
- Using a VM desktop environment
- VMs with no need to access services on them.


**Host-only**
Host-only creates a virtual network between the connected VMs and your computer. The VMs can communicate with each other but will not be able to access the internet. If you are testing software/malware or you want the vm to be isolated from your network then choose this option. If you are testing virtual networking (router, openvswitch, etc...) this is also the best option. This option does not require any physical adapter to work. 

Recommended for:
- Testing software / programs
- Forensics / Malware
- Firewall, router, virtual switch software testing. 

****

# Virtual Box

## Manage Virual Box Networks / Adapters

1. Open Virtual Box
2. Go to 'File' > 'Host Network Manager...'

In the Host Network Manager you will be able to configure virtual adapters and their related networks. You can configure a DHCP server for an adapter that will automaticly give VMs connected to that adapter an IP address. Otherwise you will need to manually assign IP addresses inside your VMs. 

When you select 'Host-only Adapter' the settings here will be used.

## Manage Virtual Box NAT Adapters

1. Open Virtual Box
2. Go to 'File' > 'Prefrences...'
3. Click the 'Network' tab

To configure port-forwarding, NAT addresses, and DHCP for Virtual Box NAT adapters use this. When you choose the 'NAT Network' option as your VM network adapter, it will use the settings that you configure here.

For the 'NAT' adapter you can configure the port forwarding on the VM settings page.


## Assing Adapters to a Virtual Box VM

Once you create a VM you can assign up to 4 network adapters to it. 

1. Open Virtual Box
2. Select a VM
3. Click 'Settings'
4. Click the 'Network' tab



# VMware Workstation 