# topics_project (How to Reproduce simulation)
My project for topics 

This project involves the simulation of an RPL routing protocol in Ad-hoc networks which is done using Cooja. And within this Github directory contains the neccessary files to replicate the project. 

Step 1: Install InstantContiki3.0 which can be found here: https://sourceforge.net/projects/contiki/files/Instant%20Contiki/Instant%20Contiki%203.0/ and run it on a virtual machine of your choice. For my project, I decided to use VMware. 

Note: The password to access Contiki should be 'user'.

Step 2: Navigate to contiki/examples/ipv6/rpl-udp and replace the Makefile with the modified version in this Github. 

Step 3: Many of the required code to simulate an RPL network is built into Contiki. To open the simulator, naviagte to the home/user/contiki/tools/cooja then type 'ant run' and select UDGM as the radio medium.

Step 4: Click [file > new simulation] 

Step 5: Click [motes > add motes > create new mote types > Z1 mote > browse]

step 6: Select the mote from the contiki/examples/ipv6/rpl-udp which is any of the c program files. For example, the default files udp-client.c is a normal node and udp-server.c is a root node.

Step 7: Once the mote is selected, select clean then compile. You will be given the option to choose the position and quantity of motes to include. For project, the positioning was random. And the number of motes included is shown in my test scenarios in the paper. 

Step 8: Once the motes are in position, click start on the simulation and allow it to run. Additionally, to provide a better observation of the network simulation, the 'view' menu can be opened to enable the display of radio traffic, node ID, etc.

Step 9: To include a malcious mote which will act as a udp-client, add the malicious-udp-client-sinkhole.c and malicious-udp-client-sinkhole.h files into home/contiki/examples/ipv6/rpl-udp folder. Then replace the rpl-mhrof.c in the home/contiki/core/net/rpl folder with the modified version in this github.

Step 10: Follow steps 4-6 to include the malcious node in the simulation. The malicious will default as a normal node once the simulation is running. To activate the malicious node, right click the mote and click 'Click button on Z1' to initiate attack.

Step 11: To set up the IDS system, replace the rpl-icmp6.c and rpl-private.h in the home/contiki/core/net/rpl folder then include the udp-client-time-trust.c udp-server-time-trust.c files in home/contiki/examples/ipv6/rpl-udp along with their respective header files (Note that the header files may need to be renamed to match the line of code tht includes them).

Step 12: To reconstruct Sencarios 3-5 as seen in the research paper, repeat steps 4-6 for the new time-trust nodes. Where the non-malicious client and server nodes will be replaced in the simulation.

Step 13: To change characteristics of the IDS, simply edit components of the code in the udp-server-time-trust.c and udp-client-time-trust.c file. In this case, the line of code to modify the uncertainty threshold is around line 140 of the udp-server-time-trust.c file.

Step 14: Run all simulation scenarios for specific time frame and use tools such as Wireshark and Powertrace to observe.

