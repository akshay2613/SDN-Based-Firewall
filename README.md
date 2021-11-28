# SDN_Firewall
============

SDN Firewall Project is about implementation of Firewall on SDN Controller by running bunch of Controller Application.

This repository consists of few Ryu Applications which are just python scripts written for running firewall functionality on Ryu controller. You need to have Ryu and Mininet installed on your device in order to run these Ryu applications. The Ryu applications are capable of ICMP, TCP and UDP firewall rules. 

Efficient Firewall:
This application uses Flow tables to store flow table entries on switch so that next time packets from that flow won't be forwarded to the controller. The switch will take decision based upon Flow table entries to forward to appropriate port or to reject the packet. Therefore, this applications are efficient in terms of packet exchange.

The two versions of firewalls are : Stateful & Stateless. 

1) Stateful firewall:
In this type of firewall, the states of the packets that passed through controller, are remembered. These states are maintained in order to detect the flow of the packet exchange between two communicating parties. The next time when a packet is received by the controller, it will check the packet with the maintained states to match the packet with particular ongoing connection. This way, the firewall keeps track of the connections itself.

2) Stateless Firewall:
This case implements traditional firewall which only checks each  arriving packet. It does **not** maintain any states like Stateful Firewall. That is, it does not keep track of ongoing connection. Rather, it simply takes each packet as individuatl and tries to check the packet with the given firewall rules. Upon matching firewall rule, it carries out associated actions, like forwarding to particular port or discarding the packet. 


