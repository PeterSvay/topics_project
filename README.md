# topics_project (How to Reproduce simulation)
My project for topics 

This project involves the simulation of an RPL routing protocol in Ad-hoc networks which is done using Cooja. And within this Github directory contains the neccessary files to replicate the project. 

Step 1: Install InstantContiki3.0 which can be found here: https://sourceforge.net/projects/contiki/files/Instant%20Contiki/Instant%20Contiki%203.0/ and run it on a virtual machine of your choice. For my project, I decided to use VMware. 

Note: The password to access Contiki should be 'user'.

Step 2: Many of the required code to simulate an RPL network is built into Contiki. To open the simulator, naviagte to the home/user/contiki/tools/cooja then type 'ant run' and select UDGM as the radio medium.

Step 3: Click [file > new simulation] then click [motes > add motes > create new mote types > Z1 mote > browse]

step 4: Select the mote from the contiki/examples/ipv6/rpl-udp which is any of the c program files. For example, the default files udp-client.c is a normal node and udp-server.c is a root node.

Step 5: Once the mote is selected, select clean then compile. You will be given the option to choose the position and quantity of motes to include. For project, the positioning was random. And the number of motes included is shown in my test scenarios in the paper. 

Step 6: To include a 

