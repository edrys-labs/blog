---
title: "Remote Lab: Building a 180° Distance Scanner with ADC"
date: 2025-11-12T09:00:00+01:00
description: "A hands-on remote laboratory where students master analog-to-digital conversion by building a rotating infrared distance scanner with Arduino."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/remote-lab-adc-scanner/cover.png'
---

Most students use `analogRead()` without understanding what happens inside the microcontroller. Our **ADC Distance Scanner Lab** removes that abstraction, challenging students to configure the Analog-Digital Converter directly while building a rotating sensor system that sweeps 180 degrees and maps the environment.

## From Arduino Shortcuts to Register Control

The lab teaches register-level ADC programming by having students replace Arduino's convenient `analogRead()` function with direct manipulation of AVR registers. Students learn to:

- Configure reference voltages and prescaler settings in `ADMUX` and `ADCSRA` registers
- Trigger conversions and wait for completion using status flags
- Transform raw 10-bit values into meaningful distance measurements
- Structure code for reusability through proper function design

The practical application? A **Sharp GP2Y0A02 infrared distance sensor** mounted on a servo motor, scanning 180 degrees while measuring distances to obstacles. Real-time radar visualization shows what the sensor "sees."

## Learning Through Debugging

Before accessing real hardware, students work through a debugging exercise in the [**AVR8js simulator**](/blog/posts/013_module-avr8js). A deliberately broken program attempts to read a potentiometer, but contains common ADC configuration errors:

- Wrong reference voltage (external instead of internal 1.1V)
- Incorrect prescaler setting (ADC clock too fast)
- Invalid channel selection (non-existent channel 8)
- Faulty voltage calculation (using wrong reference)

Students must identify and fix these errors, building confidence with ADC configuration before touching physical hardware. The simulator provides immediate feedback without compilation delays.

## The Scanner Challenge

Students then tackle the real application: a rotating distance scanner using:

- **Arduino Uno** microcontroller
- **Sharp GP2Y0A02** infrared distance sensor (10-150 cm range) connected to analog pin A0
- **Servo motor** controlled via PWM on pin 9
- **Arduino Uno** microcontroller

The starter code works but uses Arduino shortcuts. Students improve it through three tasks:

**Task 0 - Refactoring**: Extract redundant scanning loops into a reusable `make_scan()` function.

**Task 1 - Register-Level ADC**: Replace `analogRead()` with direct register manipulation—configuring `ADMUX`, `ADCSRA`, triggering conversions, and reading results.

**Task 2 - Sensor Calibration**: Implement `calculate_dist_cm()` to convert voltage readings into centimeters using the sensor's datasheet specifications.

Students write code in the [**Editor Module**](/blog/posts/009_module-editor), upload via [**Terminal Module**](/blog/posts/010_module-pyxtermjs), and watch the servo sweep through live video ([**Streaming Module**](/blog/posts/011_module-streaming)). A custom radar visualization displays measurements in real-time, creating an instant visual map of the environment.

<div style="text-align: center; max-width: 60%; margin: 2em auto;">
    <video width="100%" controls>
    <source src="https://github.com/edrys-labs/lab-tubaf-embedded-systems/raw/refs/heads/main/media/task2-motivation.webm" type="video/webm">
    Your browser does not support the video tag.
    </video>
    <p style="font-style: italic; color: #666; margin-top: 0.5em;">Overview of the ADC scanner lab</p>
</div>

## Why It Matters

This lab teaches ADC fundamentals through practical application rather than abstract theory. Students learn:

- How microcontrollers sample and quantize analog signals
- Why configuration choices (reference voltage, prescaler) affect measurement accuracy
- How to transform raw sensor data into calibrated physical measurements
- When to use Arduino libraries versus direct hardware control

The skills transfer directly to real-world embedded systems development—from environmental monitoring and medical devices to industrial automation and IoT applications. The [**Code Logger Module**](/blog/posts/018_module-code-logger) anonymously captures student work, helping instructors identify common challenges and improve the curriculum.

The lab demonstrates how Edrys-Lite makes hands-on embedded systems education accessible without requiring students to own hardware or visit physical labs. Students at TU Bergakademie Freiberg complete these exercises remotely, gaining practical skills from anywhere with internet access.

Ready to teach ADC fundamentals through hands-on remote experimentation? Build your scanner lab with Edrys-Lite!

Explore the lab: [github.com/edrys-labs/lab-tubaf-embedded-systems](https://github.com/edrys-labs/lab-tubaf-embedded-systems)

Learn more about Edrys-Lite: [edrys-labs.github.io](https://edrys-labs.github.io)
