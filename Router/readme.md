# Router

1. This file should be implemented with Switchyard environment, see the readme.md in the root folder to find the link to Switchyard.

2. The router will function in the following way:
  a) If the incoming packet's destination IP address is for the router itself, do nothing.
  b) If the incoming packet's destination is in the IP pool of the router interfaces, get the MAC address if not in the ARP table, and send it to the corresponding MAC address
  c) All other incoming packets should be forwarded to NextHop address according to the given forwarding table. Similarly, make ARP request if needed.
  d) Upon receiving an ARP request, answer if the IP address in doubt is our own IP address, else ignore it.
  e) Keep a table for ongoing ARP request, and try asking 5 times after timeout. If still cannot get the answer, give up and drop the packet.
  f) If receiving an ARP response, check the ARP request table, and send the corresponding packet towards the answered MAC address.
 
  

