# A Lightweight IoT Cryptojacking Detection Mechanism in Heterogeneous Smart Home Networks
This repository contains the code and dataset used on the academic paper, "A Lightweight IoT Cryptojacking Detection Mechanism in Heterogeneous Smart Home Networks".

We collected the network ingoing and outgong network traffic from each device. Particularly, each dataset consists of the following six columns: Timestamp, Source IP, Destination IP, Source MAC, Destination MAC, and Packet Lenght. 

## Malicious Dataset: 

Malicious dataset is collected from four devices:

- Raspberry Pi,
- LG Smart TV,
- Laptop,
- Tower Server.

For the in-browser cryptojacking samples, we used a basic WordPress webpage containing a cryptomining script. For the host-based cryptojacking, we used the cryptocurrency mining binary MinerGate. In order to collect the network traffic from LG Smart TV, we used better to manipulate ARP protocl and forward the traffic to the data collection computer's IP address. 

## Benign Dataset-1: 

For our first set of experiments, we downloaded network traffic from a public repository: https://data.mendeley.com/datasets/5pmnkshffm/1
In this dataset, the fields in the csv files are the following columns: Timestamp, protocol, payload size, IP address source and destination, UDP/TCP port source and destination. The dataset consists of several user activities: Interactive, Bulk Data Transfer, Web Browsing, Video Playback, Idle Behaviour.  We used each dataset accordingly to obtain a balanced dataset with our malicious dataset.  
Note: If you use this dataset, please go to the original link and cite it properly. 


## Benign Dataset-2: 

For our second set of experiments, we also collected our own benign dataset from the same set of the devices that we collected malicious dataset.  We performed the following activities: 1) Idle, 2) Web Browsing, 3) Watching Video, 4) Large Download, and 5) Interactive. We performed each activity on each device and collected the network traffic. We only collected Video activity dataset from LG Smart TV. 











