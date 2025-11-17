---
title: "Remote Lab: Interrupt-Driven Stepper Motor Control"
date: 2025-11-12T09:10:00+01:00
description: "A hands-on remote laboratory where students learn interrupt programming by building a visual stepper motor position tracker with LED feedback."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/remote-lab-interrupts-motor/cover.png'
---

Most embedded systems students learn about polling—constantly checking for events in a loop. But real-time systems need interrupts to respond instantly to external events. Our **Interrupt Motor Control Lab** teaches interrupt programming by building a stepper motor controller with visual position feedback on a 24-LED ring.

## From Polling to Interrupt-Driven Design

The lab teaches interrupt-based programming by having students replace inefficient polling with hardware interrupts. Students learn to:

- Configure interrupt service routines (ISR) for external pin events
- Use `volatile` keyword for variables shared between main code and ISRs
- Implement edge-triggered interrupt detection (falling edge)
- Synchronize motor position with visual LED feedback
- Map motor position (2048 steps/rotation) to LED ring positions (24 LEDs)

The practical application? A **28BYJ-48 stepper motor** with a magnetic pointer that triggers a Hall sensor. As the motor rotates, a LED ring displays the pointer's position in real-time—synchronized through interrupts.

## Learning Through Debugging

Before accessing real hardware, students work through a debugging exercise in the [**AVR8js simulator**](/blog/posts/013_module-avr8js). A broken program attempts to toggle an LED using button interrupts, but contains common errors:

- Missing pull-up resistor configuration
- Incorrect `attachInterrupt()` function arguments
- Wrong initial LED state
- Missing debouncing logic in ISR
- LED control logic outside the interrupt (should be inside ISR)

Students must identify and fix these errors, building confidence with interrupt configuration before working with physical hardware. The simulator provides immediate feedback with a virtual button and LED.

## The Motor Control Challenge

Students then tackle the real application: an interrupt-driven motor position tracker using:

- **Arduino Uno** microcontroller
- **28BYJ-48 stepper motor** (2048 steps per rotation) controlled via pins 8, 9, 10, 11
- **ULN2003 motor driver** for power management
- **Hall sensor** (magnetic sensor) on pin 2 to detect pointer position
- **Adafruit NeoPixel LED ring** (24 LEDs) on pin 3 for visual feedback

The starter code uses inefficient polling—constantly checking `digitalRead(2)` to detect the sensor. Students improve it through three tasks:

**Task 1 - Interrupt Configuration**: Implement an ISR triggered on falling edge of the Hall sensor. The ISR resets a global `volatile int position` variable to 0 when the magnet passes.

**Task 2 - Replace Polling**: Remove the `if (digitalRead(2) == 0)` polling logic and rely entirely on the interrupt-driven position reset.

**Task 3 - LED Visualization**: Map the motor's position (0-2048 steps) to the LED ring (0-23 LEDs), displaying the pointer's angular position as it rotates through 3 full revolutions.

Students write code in the [**Editor Module**](/blog/posts/009_module-editor), upload via [**Terminal Module**](/blog/posts/010_module-pyxtermjs), and watch live video of the motor spinning with synchronized LED feedback through the [**Streaming Module**](/blog/posts/011_module-streaming).

<div style="text-align: center; max-width: 60%; margin: 2em auto;">
    <video width="100%" controls>
    <source src="https://github.com/edrys-labs/lab-tubaf-embedded-systems/raw/refs/heads/main/media/task3-motivation.webm" type="video/webm">
    Your browser does not support the video tag.
    </video>
    <p style="font-style: italic; color: #666; margin-top: 0.5em;">Overview of the interrupt motor control lab</p>
</div>

## Why It Matters

This lab teaches interrupt fundamentals through practical application. Students learn:

- Why interrupts are more efficient than polling for event-driven systems
- How to properly share data between main code and interrupt handlers (`volatile`)
- Implementing precise position tracking without missing events
- Combining multiple peripherals (motor, sensor, LEDs) in synchronized operation

The skills apply directly to robotics, industrial automation, user interfaces, and any system requiring immediate response to external events. The [**Code Logger Module**](/blog/posts/018_module-code-logger) anonymously captures student work, helping instructors identify common challenges and improve the curriculum.

The lab demonstrates how Edrys-Lite makes hands-on embedded systems education accessible without requiring students to own hardware or visit physical labs. Students at TU Bergakademie Freiberg complete these exercises remotely, gaining practical skills from anywhere with internet access.

Ready to teach interrupt programming through hands-on remote experimentation? Build your motor control lab with Edrys-Lite!

Explore the lab: [github.com/edrys-labs/lab-tubaf-embedded-systems](https://github.com/edrys-labs/lab-tubaf-embedded-systems)

Learn more about Edrys-Lite: [edrys-labs.github.io](https://edrys-labs.github.io)
