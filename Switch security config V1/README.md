In this lab, I configured switch security, troubleshoot network connectivity, and performed device hardening.

SUMMARY OF LAB:
1. I checked the ip configurations of each device to make sure they are correct and matching with the vlan they are currently in. I also ensured each device is connected to the correct ports where vlans are configured.

2. I moved unused ports to a blackhole vlan and shut them down. I also configured SVI's on the switch and MLS.

3. Created a secure trunk by disabling DTP and instead set the trunks to be manually trunked. I also set the native vlan to
   be 100 since using the default vlan 1 can lead to switch attacks like VLAN tagging.
   
4. I configured port security on both switches. I made sure to set the port security static on the management port to make sure only the admin's pc is allowed while the client devices were configured to be sticky with a maximum address of 4 and restrict violation. I tested this solution by replacing the admin connection with a rogue pc. The rogue pc was not able to ping the other devices since only the admin's pc is allowed and the max mac address is 1. But when I connect the rogue to the client ports, I was able to communicate with them since the max mac address is 4 which counts the rogue as the 2nd device.

5. I configured dhcp snooping by setting the connection between switches and MLS as trusted while leaving the end devices as unstrusted. I also configured ip arp inspection on all vlans. I made sure that the ports that are trusted are also trusted for ip arp inspection.

6. Lastly, I enabled portfast and BPDU guard on the switches. 

Thats what I did for this lab and Im thinking of continuing this lab by adding a DHCP server and configuring it, adding redundancy by implementing etherchannel, and configuring spanning tree protocol by making one of the switches as the root bridge. 
