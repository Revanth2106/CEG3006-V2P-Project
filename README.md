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

3. Message Flow:

Pedestrian:
- Detect intention to cross
- Broadcast WSM with position and intent

Vehicle:
- Receive WSM
- Calculate Time-To-Collision (TTC)
- If TTC < threshold → trigger warning

  4. Parameters
 
     Communication Range: 200m (urban crossing scenario)
     Latency: <100ms
     Protocol: WSMP
     Channel: CCH
     Frequency: 5.9 GHz
