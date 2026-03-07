# Subnetting-Project-in-Packet-Tracer
This simulated Subnetting lab was conducted in Cisco Packet Tracer, where I will show you which prefixes are most commonly used in each network. The main objective of this project is to show how to calculate the subnet manually and what it is used for.


First, I will show the visual part of the network topology built in the simulator.
![Network Logic Topology](01-Topology_Overview.png)

But why use subnetting and custom prefixes? The main reasons are:

- Network organization
- Minimizing IP waste on the network
- Reducing broadcast traffic (latency)


These are the main reasons for using subnetting, but which prefixes should be used and how can they be identified?

- The larger the network, the shorter the prefix. Here are the main prefixes:

Subnetting Table

```
Prefix (CIDR), |   Decimal Mask     |  Jump (Third Octet) | Jump (Fourth Octet) |  Capacity (Useful IPs)  |
    /22        |   255.255.252.0    |         4           |                     |          1022           |
    /23        |   255.255.254.0    |         2           |                     |          510            |
    /24        |   255.255.255.0    |         1           |                     |          254            |
    /27        |   255.255.255.224  |                     |          32         |          30             |
    /28        |   255.255.255.240  |                     |          16         |          14             |
    /29        |   255.255.255.248  |                     |          8          |          6              |
    /30        |   255.255.255.252  |                     |          4          |          2              |
```
Switch configuration:

![Network Logic Topology](02-SwitchConfig.png)

In this section, switch 1 was configured as a demonstration. The following was configured:

-VLAN
-Access port and trunk

I followed the same pattern for the other switches, configuring and creating the VLANs and access and trunk ports.



Pattern used:
````
VLAN 10 
name HR

VLAN 20
name finance

Port pattern:
interface fa0/1
switchport mode access
switchport access VLAN 10

interface fa0/2
switchport mode access
switchport access VLAN 20
````

I applied the above pattern to all four switches on the network, configuring from VLAN 10 to VLAN 48.

List of VLANs:
VLAN 10: HR
VLAN 20: FINANCE
VLAN 30: LAN
VLAN 40: MAN
VLAN 48: WAN

VLAN:  Logical segmented department, used to divide networks in an organized manner, maximizing security and organization.

![Network Logic Topology](03-Router1Config.png)

