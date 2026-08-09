This lab is about configuring HSRP on packet tracer. 

LAB SUMMARY:
1. test connectivity between devices first
2. Set R1 as active router, r2 as the standby. Enable preemp on R1 and have both routers on a group
3. Set the virtual gateway on both routers.
4. Change the end device's default gateway to the virtual gateway
5. Test the solution

What I learned:

HSRP is a cisco proprietary protocol that uses a virtual router for redundancy. The way it works is that you
configure routers to have a virtual router. You then configure or choose which router will be active by giving them a higher
value. When the active router fails, the standby takes place as the active until the active is back on (if preemp is enabled). 
enabling preemp allows routers to switch back to the active when the active router is back on or when a router with highest
value joins. 

In the perspective of end devices, the virtual router is real and is not virtual. So when a traffic is outside the network, they
send it to their default gateway which is the virtual one. Physically speaking, the traffic goes to the active router
which in this case, the R1. R1 is basically saying "I am virtual router, this is my ip and my mac" while r1 still has its own 
mac and ip which is used to identify when a device does traceroute. Which is why when you perform traceroute on an end device,
the result of the hop shows it went to R1 IP(the active) and not the virtual router IP. 

But how does switches and devices know which device is the active or where the virtual router is?
It is done by doing ARP. The device asks where the default gateway mac is, active router replies here my virtual ip and mac, 
switch stores something like port1 = virtual_mac so now any traffic intended for the virtual router goes to that port,
if the port goes down, then switch just changes port2 = virtual_mac. 

When a traffic is being sent, the virtual mac is the destination instead of the active routers mac. 
