# Twisted String Actuator Test Apparatus
A mechatronics test platform designed to characterize the relationship between
actuator contraction and the electrical resistance of conductive thread in a
twisted string actuator (TSA).

The system combines mechanical actuation, position sensing, electrical
resistance measurement, embedded control, and automated data logging.

## Project Overview

The system uses a DC motor to twist the string while an Arduino simultaneously
records actuator position and electrical resistance. The resulting data can be
used to investigate whether the conductive string itself can provide useful
position feedback for a soft/wearable robotic actuator.

## Demonstration

[![TSA Test Apparatus Demo](media/Labelled_testing_apparatus.png)](media/TSA_Demo.mp4)

**Click the image to view the demonstration video.**

## CAD (Fusion 360) Designs

### Motor mount
![Motor Mount CAD](media/CAD_motor_mount.png)

### Motor attachment
![Motor Attachment CAD](media/CAD_motor_attachment.png)

### T-nut
![T-nut CAD](media/CAD_T_Nut.png)

## System Architecture

The apparatus integrates:

- Arduino Uno for control and data acquisition
- TB6612FNG motor driver
- DC motor for twisting the actuator
- VL53L0X time-of-flight sensor for position measurement
- Conductive thread as the actuator/sensing element
- Voltage-divider circuit for resistance measurement
- Rotating electrical contact for maintaining conductivity during rotation
- Custom mechanical components designed in Fusion 360 and manufactured using
  3D printing and aluminum extrusion

## Resistance Measurement

The Arduino does not measure resistance directly.

The conductive thread and a known resistor form a voltage divider. The Arduino
measures the voltage at the junction using analog input A0.

As the resistance of the conductive thread changes, the measured voltage also
changes. The resistance is then calculated using the voltage-divider equation:

R_unknown = R_known × V_out / (V_in - V_out)

Resistance from the wiring and rotating electrical contacts is measured
separately and subtracted from the calculated value.

## Position Measurement

A VL53L0X time-of-flight sensor measures the position of the moving carriage.
The initial position is recorded and contraction is calculated as:

Contraction = Starting Distance - Current Distance

This allows thread resistance to be plotted directly against actuator
contraction.

## Data Acquisition

During a trial, the system records:

- Trial time
- Distance
- Total measured resistance
- Estimated conductive-thread resistance

Resistance measurements are sampled repeatedly while the motor is operating,
allowing resistance and contraction to be correlated throughout each trial.

## Engineering Challenges

Development of the apparatus required solving several practical problems,
including:

- Maintaining reliable electrical contact with a rotating conductive string
- Electrically isolating the sensing circuit from the aluminum frame
- Selecting an appropriate voltage-divider resistor for different conductive
  materials
- Reducing noise in resistance and distance measurements
- Designing mechanically robust string attachment points
- Automating synchronized position and resistance data collection


