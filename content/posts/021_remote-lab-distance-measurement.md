---
title: "Remote Lab: Ultrasonic Distance Measurement with Arduino"
date: 2025-11-12T08:27:00+01:00
description: "A hands-on remote laboratory for learning embedded systems programming through ultrasonic sensor distance measurement."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/remote-lab-distance-measurement/cover.png'
---

Learning embedded systems programming shouldn't require physical access to hardware. Our **Ultrasonic Distance Measurement Lab** provides real Arduino hardware accessible through a web browser, where students write code, upload to actual microcontrollers, and see real sensor measurements—all remotely.

## Two Learning Tracks

The lab offers differentiated instruction through parallel tracks based on experience level:

**Track A - Fundamentals**: Students implement low-level sensor control from scratch. They learn to:
- Generate trigger pulses using GPIO pins
- Measure echo duration with microsecond precision (`pulseIn()` function)
- Convert time measurements to distance using the speed of sound
- Display results on LCD screens and serial output

This track builds foundational understanding of how ultrasonic sensors communicate through timing signals.

**Track B - Library Integration**: Experienced students work with the NewPing library, focusing on:
- Object-oriented sensor interfaces
- User configuration systems (unit selection, measurement ranges)
- Input validation and error handling
- Advanced LCD menu design

Both tracks use the same hardware but approach the problem from different technical angles, ensuring appropriate challenge levels.

## Simulation Before Hardware

Before accessing real equipment, students practice in the [**AVR8js simulator**](/blog/posts/013_module-avr8js):

**Track A**: Timing exercises using virtual buttons to understand pulse duration measurement—the same principle used by ultrasonic sensors.

**Track B**: LCD interface development, designing user menus and display layouts without hardware constraints.

The simulator provides immediate feedback, allowing students to debug logic errors and iterate quickly before working with physical components.

## The Hardware Challenge

Students then access the real setup using:

- **Arduino Uno** microcontroller
- **HC-SR04 ultrasonic sensor** (trigger and echo pins)
- **16x2 LCD display** with I2C interface

They write code in the [**Editor Module**](/blog/posts/009_module-editor), upload via [**Terminal Module**](/blog/posts/010_module-pyxtermjs), and watch live video of the sensor responding to objects through the [**Streaming Module**](/blog/posts/011_module-streaming). Real-time serial output shows distance measurements as they happen.

They write code in the [**Editor Module**](/blog/posts/009_module-editor), upload via [**Terminal Module**](/blog/posts/010_module-pyxtermjs), and watch live video of the sensor responding to objects through the [**Streaming Module**](/blog/posts/011_module-streaming). Real-time serial output shows distance measurements as they happen.

<div style="text-align: center; max-width: 60%; margin: 2em auto;">
    <video width="60%" controls>
    <source src="https://github.com/edrys-labs/lab-tubaf-embedded-systems/raw/refs/heads/main/media/task1-motivation.webm" type="video/mp4">
    Your browser does not support the video tag.
    </video>
    <p style="font-style: italic; color: #666; margin-top: 0.5em;">Overview of the distance measurement lab</p>
</div>

## Why It Matters

This lab teaches embedded systems fundamentals through practical application. Students learn:

- How sensors communicate through timing signals
- Implementing time-critical measurements in code
- Working with peripheral devices (LCD displays)
- Choosing between low-level control and library abstractions

The skills apply directly to robotics, automation, parking assistance systems, and countless other embedded applications. The [**Code Logger Module**](/blog/posts/018_module-code-logger) anonymously captures student work, helping instructors identify common challenges and improve the curriculum.

The lab demonstrates how Edrys-Lite makes hands-on embedded systems education accessible without requiring students to own hardware or visit physical labs. Students at TU Bergakademie Freiberg complete these exercises remotely, gaining practical skills from anywhere with internet access.

Ready to teach ultrasonic sensor fundamentals through hands-on remote experimentation? Build your distance measurement lab with Edrys-Lite!

Explore the lab: [github.com/edrys-labs/lab-tubaf-embedded-systems](https://github.com/edrys-labs/lab-tubaf-embedded-systems)

Learn more about Edrys-Lite: [edrys-labs.github.io](https://edrys-labs.github.io)
