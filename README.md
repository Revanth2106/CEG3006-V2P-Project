# CEG3006-V2P-Project
Smart Crossing System using DSRC based V2P safety system

It is a Vehicle to Pedestrian (V2P) safety system created to aid visually impaired people at signal crossings.

1. Project Overview

  The system uses:
  - IEEE 802.11p (DSRC) for low latency communication
  - IEEE 1609 for WAVE stack
  - WAVE Short Message Protocol for safety messaging
  - SAE J2735 for the message structure
  
  The aim of the project is to provide collision warnings in <100 ms latency

2. System Architecture:

  Pedestrian Unit (Smartphone + DSRC module) - IEEE 802.11p -> Vehicle OBU -> Vehicle CAN network -> Driver Warning System
  
  Safety messages are transmitted thru WSMP over the Control Channel, CCH.

  pedestrian device broadcasts safety message using dsrc -> the vehicle obu receives and processes the msg -> driver warning system alerts driver if theres collision risk

3. Message Flow:

  Pedestrian:
  - Detect intention to cross
  - Broadcast WSM with position and intent
  
  Vehicle:
  - Receive WSM
  - Calculate Time-To-Collision (TTC)
  - If TTC < threshold → trigger warning

  pedestrian device sends WSM with position & crossing intent thru button press -> vehicle gets msg, calculates TTC and if its < threhold than trigger warning

4. Parameters
 
     Communication Range: 200m (DSRC range in complex urban environments 100-300m)
     Latency: <100ms
     Protocol: WSMP
     Channel: CCH
     Frequency: 5.9 GHz


## Functions

![Functions Table](docs/functions_table.PNG)

1. OBU receives the state of the vehicle
2. The collision risk is computed relative to the pedestrian
3. Direction of the hazard is determined
4. Safety message is sent
5. Message is sent using IEEE802.11p
6. Pedestrian wearable gets the safety message
7. Corresponding vibration pattern is chosen
8. Vibrotactile actuators are activated
9. Pedestrian can evaluate the direction of hazard or if its safe to cross



