# Grain Trucks Multimodal Terminal Simulation
### Final Assignment for the Introduction to Agent-Based Models Course

<p align="center">
  <img alt="License" src="https://img.shields.io/static/v1?label=license&message=MIT&color=8257E5&labelColor=000000">

 <img src="https://img.shields.io/static/v1?label=GTMTS&message=1.0&color=8257E5&labelColor=000000" alt="GTMTS 1.0" />
</p>

<h1 align="center">
  <img alt="GTMTS 4.0" title="Grain Trucks Multimodal Terminal Basic Simulation" src="https://github.com/juliocslima/introduction-to-abms-final-assignment/blob/main/images/grain_terminal_basic_simulation.png" />
</h1>

Teacher: [Eric Araújo, PhD](https://orcid.org/0000-0003-4263-9075)[^1]

Student: [Julio C. S. Lima](http://lattes.cnpq.br/2520521178972799)[^2]

## Overview

This NetLogo model simulates the flow and processing of grain trucks through a multimodal terminal, llustrating the First-In-First-Out (FIFO) process from arrival to departure. The model includes various states and checkpoints such as entrance gate, sampling, classification, first weighing, unloading, second weighing, and exit gate. The purpose is to study the impact of processing times and truck movement on the overall efficiency of the terminal.

## Model Description

### Agents

- **Trucks**: Represent grain trucks moving through the terminal.
- **Checkpoints**: Represent different processing stages within the terminal.

### States and Checkpoints

- **Start**: The truck scheduled for unloading arrives at the terminal.
- **Entrance Gate**: The first checkpoint where truck documentation is processed and checked for entry into the terminal.
- **Sampling**: The second checkpoint where a sample of the cargo is taken for the classification and analysis stage to meet quality requirements.
- **Classification**: In this state, the sample taken from the cargo is analyzed to meet quality requirements. The truck waits for the result before proceeding to the first weighing. Trucks can keep moving but cannot enter the next checkpoint until the classification process is complete.
- **First Weighing**: The third checkpoint where the gross weight of the truck is measured.
- **Unloading**: The fourth checkpoint where the truck unloading process occurs.
- **Second Weighing**: The fifth checkpoint where the tare weight of the truck is measured. After this process, the net weight of the product unloaded at the terminal is calculated.
- **Exit Gate**: The sixth and final stage of the unloading process where the truck receives a ticket with the measured weights and information about the quality of the product. After printing the document, the truck transitions to the "end" state, completing the process in the simulator.
- **End**: The final state in the simulation.

### Properties

- **Trucks**:
  - `state`: Current state of the truck.
  - `gross-weight`: Initial gross weight of the truck.
  - `tare-weight`: Initial tare weight of the truck.
  - `net-weight`: Unloading weight of the truck.
  - `speed`: Average speed of the truck.
  - `processing-start-time`: Time when processing started at the checkpoint.
  - `start-time`: Truck processing start time
  - `end-time`: Truck processing end time
  - `classification-done`: Indicates if the classification process is done.
  
- **Checkpoints**:
  - `check-point?`: Indicates if the patch is a checkpoint.
  - `automated-process?`: If true indicates processes that require no human intervention (Methods not implemented)

### How It Works

Trucks move horizontally along the x-axis, transitioning from one state to another based on the processing times at each checkpoint. During the classification state, trucks keep moving but cannot enter the next checkpoint until classification is complete.

## How to Use the Model

### Interface Elements

- **Length of Time Period slider:** Sets the amount of ticks thats represents a shift time
- **Entrance Gate Time Slider:** Sets the processing time at the entrance gate.
- **Period of Simulation in Days slider:** Sets the stop criteria in days (1 day = 1,440 ticks)
- **Gate Processing Time Slider**: Sets the processing time at the entrance and exit gate.
- **Sampling Processing Time Slider**: Sets the processing time at the sampling checkpoint.
- **Classification Processing Time Slider**: Sets the processing time for the classification state.
- **Weighing Processing Time Slider**: Sets the processing time at the first and second weighing checkpoint.
- **Unloading Processing Time Slider**: Sets the processing time at the unloading checkpoint.
- **Setup Button**: Initializes the simulation, setting up the patches and creating the trucks.
- **Go Button**: Starts the simulation, making the trucks move through the checkpoints.

### Steps to Run the Model

1. Open the `grains_multimodal_terminal.nlogo` file in NetLogo.
2. Click the **Setup** button to initialize the model.
3. Adjust the sliders to set the processing times at each checkpoint.
4. Click the **Go** button to start the simulation.

## Things to Notice

- Observe the movement of trucks along the x-axis and their transitions between checkpoints.
- Note the delays at each checkpoint, reflecting the processing times set by the sliders.
- Trucks keep moving during the classification state but wait for the classification process to complete before entering the first weighing checkpoint.

## Things to Try

- Adjust the sliders for processing times at various checkpoints and observe the effects on overall flow and delays.
- Increase the number of trucks and see how the model handles higher traffic.
- Experiment with different average speeds for the trucks to see the impact on the simulation.

## Extending the Model

- Add more checkpoints or states to simulate a more complex terminal process.
- Include random delays or processing times to simulate more realistic and variable conditions.
- Introduce interactions between trucks, such as overtaking or waiting for each other at certain points.
- Implement different types of trucks with varying capacities and speeds to see how diversity affects the overall process.

## NetLogo Features

- Utilizes patch and turtle primitives to represent checkpoints and trucks.
- Demonstrates agent-based modeling with state transitions and movement along a defined path.
- Employs global and turtle variables to manage state and processing times.
- Uses conditional logic to handle state transitions and processing time checks.

## Related Models

- **Traffic Simulation**: Similar models in the NetLogo library that simulate traffic flow and vehicle interactions.
- **Logistics and Supply Chain Models**: Models focusing on supply chain management and logistics processes.

## Credits and References

- Model developed by Julio C. S. Lima.
- Inspired by real-world multimodal terminal operations.
- For more information and related resources, visit my [Github](https://github.com/juliocslima/introduction-to-abms-final-assignment).

[^1]: Associate Professor - Federal University from Lavras - UFLA, Brazil.
[^2]: Master's degree in Systems and Automation Engineering - Federal University of Lavras, UFLA, Brazil.
