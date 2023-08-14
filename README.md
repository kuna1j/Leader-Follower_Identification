# Leader-Follower Identification 
## Project Overview
The Vehicle Leader-Follower Detection and Analysis project is aimed at developing a system that detects and analyzes leader-follower pairs among vehicles in video data. The project utilizes computer vision techniques, including object detection and tracking, to identify vehicles and establish relationships between them based on their positions and movements.
## Table of Contents
- Project Overview
- Features
- Criteria for Leader-Follower Pair
- Installation
- Usage
- Results
- Contributing
## Features
- **Object Detection**: Utilized a custom-trained YOLOv8 model to detect and track vehicles in video frames.
- **Object Tracking**: Implemented BYTESORT tracking algorithm in the YOLOv8 model to follow the movements of detected vehicles across frames.
- **Leader-Follower Pair Identification**: Analyzed vehicle positions and movements to identify leader-follower pairs based on defined criteria.
- **Data Visualization**: Visualize the detected leader-follower pairs and their relative positions over time.
- **Metrics Calculation**: Compute metrics such as time gaps and distances between leader-follower pairs for further analysis.

## Criteria for Leader-Follower Pair
The criteria for a pair to be leader-follower is:

LT = 0.5*(wLv+wFv) + LCFv    
LG = YLv - YFv

where,     
LT = lateral threshold,     
Yi = lateral position of vehicle i on the carriageway,        
w = width of the vehicle,       
Lv and Fv = leading vehicle and following vehicle, respectively,        
LCi = lateral clearance of vehicle i (height/2, in our case),    
LG = lateral gap     

Conditions:

i. XLv + lLv > XTv    
ii. LG < LT 

where,     
Xi = longitudinal position of vehicle i on the carriageway,     
lLv = length of the leading vehicle (width, in our case)

## Installation
1. Clone this repository to your local machine.     
   git clone https://github.com/kuna1j/leader-follower-identification    
   git cd leader-follower_identification

## Usage
1. Prepare your video data or use the video file provided in the directory.

2. Run the main script to perform vehicle detection, tracking, and leader-follower analysis.

3. The script will generate an output CSV file containing leader-follower pairs and ids of vehicles near the leader vehicle.

## Results
The results of the analysis will be saved in a CSV file that contains information about the identified leader-follower pairs among vehicles. Each record in the CSV file includes the frame number of the detected pairs, leader vehicle id, follower vehicle id, and the detected vehicle's positions near the leader vehicle. This information can be used for further analysis and insights into traffic dynamics.

## Contributing
Contributions are welcome! If you have any ideas for improvements or additional features, please feel free to submit a pull request.
# 
By implementing the Vehicle Leader-Follower Detection and Analysis project, we aim to gain insights into traffic behavior and vehicle interactions, which can have applications in traffic management, safety assessment, and urban planning.
