# T6.3 - Welding Process Inspector

## General Description
This solution aims to predict/estimate the presence of defects during the welding process using process parameters monitored in real time. The goal is to reduce the production time and waste when a defective weld occurs. 

It is deployed in two stages. First, several sensors are selected and integrated on the welding torch to obtain a comprehensive monitoring of the welding process. The sensors will look at different process parameters like welding speed, wire feed rate, welding electrical signals, thermal info of bead and base plate… The system will synchronize the data temporally and spatially, creating valuable and comprehensive datasets. 

On a second stage, this data is analyzed and correlated with NDT data to create data models capable to detect high probability of defect appearence in real time. The model is deployed following an edge computing paradigm.

## Top Ten Functionalities

   1. Welding process monitoring system.
   2. Enables implementation of AI-based quality assurance algorithms.
   3. Early detection of defects: time and scrap reduction in rework tasks.
   4. Flexibility: monitoring system covers a great variety of sensors and communication protocols (e.g., TCP/IP or Profibus).
   5. Scalability: Ease of adding new sensors.
   6. Adaptability: monitoring system adaptable to any metallic welding process.
   7. It contributes to the digitization of the industry.
   8. Set an alarm to stop the process when out of quality limits.
   9. Enables process control.
   10. Provides thermal info form welding bead and base plates.

## Architecture Diagram

![image](./images/architecture-diagram.jpg "architecture diagram")

- **Internal modules**:
    - *Main*: Synchronizes data acquisition from the different sensors, data storage and defect detection algorithms.
    - *GigE IR cam*: This module enables connection to cameras following GigE/genie cam protocols/standards.
    - *DAQ board*: Data Acquisition Board. Acquire digital and analogue signals, e.g., pyrometers.
    - *Oscilloscope*: Retrieves high speed signal, i.e., voltage and current of each welding torches.
    - *Laser line*: retrieves the geometrical data scanned by the laser line. 
    - *Pose Logger*: Retrieves the position of the welding torches regarding the whole part.
    - *Defect Detection Algorithm*: Analise data stream from sensors and warns when anomalies are identified.
    - *Storage*: Data is storage locally in a custom format.
- **GUI**: Graphical User Interface. Allows the user to configure the monitoring system and check the correct operation of the system during welding.
- **API**: SW interface to the monitoring system  

## Image Overview
The present section addresses the user interfaces envisioned to interact with the Welding Process Monitoring solution. Two GUIs are defined, one for configuring all devices involved in the data acquisition which also provides some features for online visualization and another one for offline analysis of the recorded data. 

![image](./images/online-mockup.png "Online GUI (mockup)")

Above figure is a design for the GUI in charge of the HW configuration of ZDZW Welding Inspector the and a subsampled online visualization of the welding process (a.k.a. *recorder app*). On the left side you can see the 3 different formats for the visualization of the data that is being recorded, while the right side is reserved for the configuration of the system and to start/stop the recording. The online visualization includes an image viewer for the IR camera and graph and scalar viewers which allow the user to plot desired parameters. The “configuring input/output interfaces” contains the settings of the sensors that are being used for monitoring the welding process. The “Recorded params” section links the process parameters with the sensor that is being used to get their values. The “metadata” section contains relevant logistic information. The GUI allows the user to enable/disable a defect detection model and to load different models. Finally, the GUI offers a couple of buttons to start and stop the recording manually.

![image](./images/offline-mockup.png "Offline GUI (mockup)")

Above figure shows the mockup of the GUI for the offline visualization (a.k.a. *visualizer app*). While the *recorder app* offers a restricted, but online, visualization of the monitored data from the welding process, the *visualizer app* allows skilled personnel to analise the recorded data aand visualize it in different formats. The *recorder app* allows the operator to detect disturbances on the welding process or possible mistakes in the configuration of the monitored system, while the *visualizer app* allows a deeper analysis of the recorded data. In addition to the image and graph viewers already available in the *recorder app*, the *visualizer app* also provides a 3D representation of the process parameters.


## Hardware Components
[*Add a description of the hardware components required for the applications to work*]

## Computation Requirements

|    | **minimum** | **recommended** |
| -- | ----------- | --------------- |
**cpu** | 2.60GHz × 6 (i5 11G) | 2.30GHz × 16 (i7 11G)
**ram** | 16 Gb | 32 Gb
**storage**| 512 Gb | > 1 Tb





## Installation Procedure
[
*Step by step on how to install the application:*
* *Standalone*
* *In the Kubernetes platformm using helm charts: description of the different options*
]

Not available yet.

## How To Use
[*Step by step on how to use the application*]

TBD

## Additional Learning Materials
[*Links to other learning materials like youtube tutorials or work from WP10*]

TBD
