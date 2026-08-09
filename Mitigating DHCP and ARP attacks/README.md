This lab is about performing switch configurations to prevent ARP attacks and DHCP attacks. 
SUMMARY OF LAB:

1. Enable ip dhcp snooping globally first, then configure the trusted ports and untrusted ports by using ip dhcp snooping trust and ip arp inspection trust
2. Assign which vlans will have ip dhcp snooping enabled (in this labs, all vlans were included).

What I learned is that Ip dhcp snooping is used to prevent DHCP attacks by configuring which ports are trusted (allow dhcp responses) or untrusted. Trusted ones are usually not user devices connected to the switch like a router, or another switch. 
Now when someone sends a dhcp request, the router recieves it and gives them ip. The switch tracks that and keeps a record of the details like IP and mac to the DHCP binding table. 
This table is used in preventing ARP attacks since when a switch recieves a spoofed arp response, then the switch can just compare its mac and ip to see if it matches the dhcp binding table.
