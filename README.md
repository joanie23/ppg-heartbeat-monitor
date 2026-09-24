# PPG Heartbeat Monitor

An analog heartbeat detection circuit that uses photoplethysmography (PPG) to detect pulse-related changes in blood volume, filter and amplify the signal, and provide a visible heartbeat indication using an LED.

## Project Overview

The goal of this project was to design and build an analog circuit capable of detecting a heartbeat signal using a TCRT1010 reflective optical sensor.

Because the raw sensor signal contains a DC component and unwanted noise, the circuit uses multiple signal-conditioning stages before producing the final output.

The system was designed to operate over a human heart-rate range of approximately **50–200 BPM (0.83–3.33 Hz)**.

## System Architecture

The circuit consists of the following stages:

**TCRT1010 PPG Sensor → AC Coupling / High-Pass Filter → Low-Pass Filter → Amplifier → LED Output**

Each stage conditions the heartbeat signal before it reaches the final LED indicator.

## My Design Work

My design work included:

- Designing the analog signal-conditioning circuit
- Selecting resistor and capacitor values for the filters
- Designing the high-pass filtering / AC-coupling stage
- Designing the low-pass filtering stage
- Designing the signal amplification stage
- Implementing the LED output stage
- Simulating the circuit before hardware implementation
- Building the circuit on a breadboard
- Testing the design using an oscilloscope
- Comparing simulated and measured performance
- Troubleshooting component and gain differences between simulation and hardware

## Signal Conditioning

### PPG Sensor

A TCRT1010 reflective optical sensor was used to detect changes associated with the heartbeat.

The sensor detects changes in reflected infrared light caused by variations in blood volume.

### AC Coupling / High-Pass Filtering

The AC-coupling stage removes the large DC component from the sensor output while allowing the changing pulse signal to pass through the circuit.

### Low-Pass Filtering

A low-pass filter was used to reduce unwanted higher-frequency noise while preserving frequencies within the expected human heart-rate range.

### Amplification

The filtered heartbeat signal is relatively small, so an op-amp amplification stage was used to increase its amplitude before driving the output stage.

### LED Output

The final stage drives an LED so that the detected pulse can be observed visually.

## Simulation

The circuit was simulated before hardware implementation to verify the filter behaviour, amplification, and LED response.

The simulation showed that:

- The filters preserved signals within the desired heart-rate range
- The amplifier increased the signal without significant distortion
- The LED responded at the expected pulse frequency

## Hardware Implementation

After simulation, the circuit was constructed and tested on a breadboard using laboratory equipment.

Oscilloscope measurements were used to observe the signal and evaluate the performance of the physical circuit.

## Results

The completed circuit successfully produced an LED response at the detected pulse frequency.

The physical circuit did not exactly match the simulated performance. The intended amplifier gain was approximately **10×**, while the measured hardware produced approximately **7× gain**.

Differences between ideal simulation components and physical resistor/op-amp behaviour contributed to the difference.

Despite this, the circuit remained functional and produced the expected LED pulse indication.

## Hardware and Components

- TCRT1010 reflective optical sensor
- Operational amplifiers
- Resistors and capacitors
- LED
- Breadboard
- Oscilloscope
- Function generator
- DC power supply

## Engineering Skills Demonstrated

- Analog circuit design
- Signal conditioning
- Active and passive filtering
- Operational amplifier circuits
- Photoplethysmography (PPG)
- Circuit simulation
- Breadboard prototyping
- Oscilloscope measurements
- Simulation-to-hardware comparison
- Circuit troubleshooting

## What I Learned

This project demonstrated the difference between ideal circuit simulation and physical hardware.

Although the simulated amplifier achieved the expected gain, the measured circuit produced a lower gain due to real component behaviour and component-value differences.

Troubleshooting these differences provided practical experience in analog circuit testing and signal conditioning.

## Future Improvements

Possible improvements include:

- Improving heartbeat detection consistency
- Refining filter component values
- Improving sensor placement and stability
- Testing the circuit with a larger set of measurements
- Adding digital heart-rate calculation and BPM display
