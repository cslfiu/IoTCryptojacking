# A Lightweight IoT Cryptojacking Detection Mechanism in Heterogeneous Smart Home Networks
This repository contains the code and dataset we used on the academic paper, "A Lightweight IoT Cryptojacking Detection Mechanism in Heterogeneous Smart Home Networks", which is currenly under review in NDSS.

## 1. Data
We collected the ingoing and outgong network traffic from each device. Particularly, each dataset consists of the following seven columns: 1) Timestamp, 2) Source IP, 3) Destination IP, 4) Source MAC, 5) Destination MAC, 6) Protocol, and 7) Packet Length. Even though we collected the IP address and protocol information, we did not use them in our experiments. We share them here so that it can be useful to other researchers. 

We uploaded the dataset in a drive folder due to large file limitation of github. The dataset can found in the following link: https://drive.google.com/drive/folders/13kNRyCuGOoRZ2BrBXoNvRnSnivq6_y4h?usp=sharing

### Malicious Dataset
Malicious dataset is collected from four devices:

- Raspberry Pi
- LG Smart TV (WebOS)
- Laptop/Desktop
- Tower Server

For in-browser cryptojacking samples, we used a basic WordPress webpage containing a cryptomining script from the [webmine.io](http://webmine.cz/) and [WebminePool](https://www.webminepool.com). For the host-based cryptojacking, we used the cryptocurrency mining binary [MinerGate](https://www.minergate.com). In order to collect the network traffic from LG Smart TV, we used [Ettercap](https://www.ettercap-project.org/) to manipulate ARP protocol and forward the traffic to the data collection computer's IP address. 

### Benign Dataset-1

For our first set of experiments, we downloaded the network traffic data from a public repository: https://data.mendeley.com/datasets/5pmnkshffm/1
In this dataset, the fields in the csv files are the following columns: Timestamp, protocol, payload size, IP address source and destination, UDP/TCP port source and destination. The dataset consists of several user activities: Interactive, Bulk Data Transfer, Web Browsing, Video Playback, Idle Behaviour.  We used each dataset accordingly to obtain a balanced dataset with our malicious dataset.  

Note: If you use this dataset in your project, please go to the [original link](https://data.mendeley.com/datasets/5pmnkshffm/1) and cite it properly. 


### Benign Dataset-2 

For our second set of experiments, we collected our own benign dataset from the same set of the devices that we used for the malicious data collection.  We performed the following user activities: 

1) Idle Behavior, 
2) Web Browsing, 
3) Watching Video, 
4) Large File Download,
5) Interactive. 

We performed each activity on each device and collected the network traffic. We collected only watching video activity from LG Smart TV. Therefore, in total we collected 16 dataset (3 devices x 5 activities + LG Smart TV). 

## 2. Experiments 

### Malicious vs. Benign-1 
In this set of experiments, we tested the following cases:

- S0: Designing an IoT Cryptojacking Detection Mechanism
- Evaluation with Different Adversarial Behaviours 
    - S1: Server vs. Desktop vs. IoT
    - S2: Aggressive vs. Robust vs. Stealthy
    - S3: In-browser vs. Binary
- Adversarial  Models  of  Compromised  Device  Numbers  in Smart Home Network
    - S4: Fully comprimised (All)
    - S5: Partially compromised (Laptop + IoT)
    - S6: Single compromised (IoT)
    - S7: IoT compromised (IoT + IoT)

In these experiments, we used balanced datasets in terms of the packet count. 

### Malicious vs. Benign-2 
In this set of experiments, we tested the following cases:

- We repeated the same scenarios (S0-S7) as the first set of experiments with our own dataset (i.e., Benign-2). The code for all scenarios is as follows: [S0-S7](https://github.com/IoTcryptojacking/A_Lightweight_IoT_Cryptojacking_Detection_Mechanism_in_Heterogeneous_Smart_Home_Networks/blob/main/Code/Malicious_vs_Benign_2%20(All%20Scenarios).ipynb)
- We tested the performance of our classifier with imbalanced dataset. Particularly, we tested each device`s malicious data with its own benign data (raspberry vs. raspberry or server vs. server). The code and results are placed [here](https://github.com/IoTcryptojacking/A_Lightweight_IoT_Cryptojacking_Detection_Mechanism_in_Heterogeneous_Smart_Home_Networks/blob/main/Code/Imbalanced%20dataset%20experiments.ipynb).
- We also tested the transferability of the classifier.

## 3. Reproducibility

Steps for the reproducibility are as follows:

1. Download the data and code in the same directory. 
2. Set the local path for each dataset accordingly. 
3. Run all of the cells in jupyter notebook in order until the scenarios.
4. Run the cell containing a scenario.

Note: Jupyter Notebook and other python modules (e.g., tsfresh, pandas) needs to be installed before these steps.

















