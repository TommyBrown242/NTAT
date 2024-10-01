# NTAT
Network Traffic Analysis Tool


This is an application that allows the user to monitor the traffic going through their machine in a network. Specifically, it looks for individual, or groups of, packets that seem suspicious.

The application does this by recording characteristics of previous analysises, i.e. time period of analysis, average rate of traffic, total number of captured packets. Additionally, the traffic is analysed for attack signatures of known attacks.

Both the frontend of the application is written in Java, whereas the backend packet capture is written in Python.

The packet-capture.py file contains all of the functions relating to the capture and analysis of the packets going through the machine. These functions include:
  - detectDDOS:               		Searches for source IP addresses of captured packets, suggests if a DDoS attack may be occurring.
  - detectMaliciousIPAddress: 		Matches source IP addresses against predefined list of malicious IPs.
  - createIPDict:             		Create dictionary containing number of packets from each address.
  - getControlValues:         		Get values from control file to be used in context analysis.
  - getContextValues:         		Get values from context file to be used in context analysis.
  - updateControlFile:        		Updates file with information about the most recent packet capture.
  - createContextFile:        		Creates file to store information on latest packet capture.
  - analysisPCAPFile:         		Contains analysis of the .pcap file created by the running of the application.
  - createCapturename:        		Creates the formatted name for the files created for this specific packet capture and analysis.
  - captureNetworkTrafficWithMin:	Capture packets for specified time period and until a minimum number of packets have been captured.
  - captureNetworkTrafficWithoutMin:	Capture packets for specified time period.

The Main.java file controls the user interface of the application and calls packet-capture.py to begin packet captures.
