Communication is done with these IP-adresses:
Robot controller IP: 172.31.1.147
RSI Sensor IP: 192.168.1.100

For the example, use the TestServer located in the DOC folder extracted from the robot
On the controller, run the RSI_Ethernet program located in R1/Program on the controller.
Make sure it gets to the RSI_MOVECORR() command before you can actually read anything on the TestServer interface on your PC

In the example, whatever appears in the log of the GUI interface on the server on your PC is the actual XML formatted message that is sent/received to/from the robot controller

IPOC is a timestamp automatically generated by KUKA. When we want to use RSI, we first have to receive the timestamp and then send the data we want to send with the same timestamp.
The controller then automatically calculates the time difference between the message it sent and the message it received from the IPOC-ID. If it does not adhere to the cycletime
restrictions, then the message is invalid.

This communication is based on the [[RSI Interface]] and is here between [[KUKA Robot controller(con)|con]] and [[Computer(com)|com]]. where con is the client and com is the server. The con can be set to expect a response or not, and so the com can be set to either send and recieve or just recieve data. 
The com therefore needs to listen with its program before running the program on the con. This also makes sense when taking the IPOC verification system into account.

