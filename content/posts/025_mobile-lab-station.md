---
title: "The Mobile Remote Lab Station: Hardware Meets Software"
date: 2025-11-13T10:00:00+01:00
description: "How we built a portable, automated station hosting four remote embedded systems labs with intelligent lighting and camera control."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/mobile-lab-station/cover.jpg'
---

Remote labs need physical infrastructure somewhere. At TU Bergakademie Freiberg, we built a custom station that hosts four embedded systems labs in a portable, automated setup—demonstrating that remote lab hardware can be practical, space-efficient, and intelligent.

## The Design Challenge

We needed hardware infrastructure that could:

- Host multiple lab setups simultaneously
- Be relocatable (different rooms, events, demonstrations)
- Provide good camera angles for students watching remotely
- Minimize power consumption when labs aren't in use
- Manage cables and connections cleanly
- Support different Arduino and microcontroller configurations

The solution? A custom-built mobile station constructed from modular aluminum parts.

## Physical Construction

The station stands tall enough for good vertical organization, narrow enough to fit through doorways and position against walls.

**Key features**:

- **Modular aluminum frame**: Easy to assemble, modify, and maintain
- **Four wheeled casters**: Roll the entire setup to different locations
- **Four equipment shelves**: Each hosts one lab's hardware in a dedicated box
- **Cable management**: Integrated routing keeps connections organized
- **Compact footprint**: Maximizes lab density without consuming excessive floor space

The aluminum construction provides structural stability while remaining lightweight. We can reposition the entire station—four labs, cameras, computers, and all—in minutes.

## The Lab Configurations

Each of the four shelves hosts a different embedded systems lab:

1. **[Ultrasonic Distance Measurement](/blog/posts/021_remote-lab-distance-measurement)**: Arduino Uno with HC-SR04 sensor and LCD display
2. **[ADC Distance Scanner](/blog/posts/022_remote-lab-adc-scanner)**: Arduino Uno with Sharp infrared sensor and servo motor
3. **[Interrupt Motor Control](/blog/posts/023_remote-lab-interrupts-motor)**: Arduino Uno with stepper motor, Hall sensor, and NeoPixel LED ring
4. **[Calliope Mini MicroPython](/blog/posts/024_remote-lab-calliope-mini)**: Calliope mini educational microcontroller

Each lab's components are housed in a dedicated box on its shelf, keeping hardware organized and visible to the overhead camera.

## Intelligent Automation

Above each lab shelf sits a camera and a controllable LED light. Here's where software enhances the hardware setup:

**The problem**: Leaving lights running 24/7 wastes energy and generates unnecessary heat. But manually controlling them defeats the purpose of remote access.

**The solution**: Automatic station-aware lighting.

We built a custom system using:

- **Node.js server** running on the station computers
- **Smart lights** connected to the local network router (built into the station)
- **Custom Edrys module** using [Edrys.js](/blog/posts/019_edrys-js) to monitor station occupancy
- **Communication protocol** between the module and the Node.js server

When a student enters a station (joins that lab room in Edrys), the module detects the state change and sends a request to the Node.js server, which commands the corresponding light to turn on. When the last student leaves, the light turns off.

This creates an intelligent, responsive environment where:

- Students always have proper lighting for the camera feed
- Energy isn't wasted on empty stations
- The system operates automatically without manual intervention
- Station status is visually obvious (lit = in use, dark = available)

## Computational Setup

Two computers power all four stations:

- **Computer 1**: Runs Edrys stations for Labs 1 and 2
- **Computer 2**: Runs Edrys stations for Labs 3 and 4

Each computer runs the [PyxTerm.js Terminal Module](/blog/posts/010_module-pyxtermjs) in Docker containers, managing code uploads and serial communication with the connected hardware. The cameras feed live video through the [Streaming Module](/blog/posts/011_module-streaming).

This dual-computer architecture balances load while keeping the setup compact. If one computer needs maintenance, half the labs remain operational.

## Why This Matters

This physical setup demonstrates several principles for remote lab infrastructure:

**Portability**: Wheeled design means we can demonstrate labs at conferences, move between classrooms, or relocate for building maintenance.

**Scalability**: The modular design could easily accommodate more shelves, different lab configurations, or upgraded components.

**Automation**: Smart lighting shows how software can enhance hardware infrastructure, reducing operational overhead.

**Resource efficiency**: Two computers serving four labs proves remote infrastructure doesn't require one-to-one hardware-to-lab ratios.

**Visibility**: Overhead cameras with automatic lighting ensure students see hardware clearly regardless of ambient room conditions.

## Practical Benefits

From an operational perspective, the mobile station provides:

- **Flexibility**: Relocate labs for events, workshops, or classroom demonstrations
- **Maintenance**: Easy access to all components for hardware swaps or repairs
- **Expansion**: Add new labs by adding shelves and reconfiguring software
- **Demonstration**: Roll the station to different audiences to show physical hardware
- **Safety**: Centralized location allows monitoring and quick intervention if needed

The intelligent lighting system alone saves significant energy over a semester of continuous operation.

## Remote Labs Need Physical Infrastructure

While students access labs remotely, the hardware exists somewhere physical. Our mobile station shows that infrastructure can be:

- Compact enough to fit in limited space
- Portable enough to serve multiple locations
- Intelligent enough to manage itself
- Scalable enough to grow with demand

The combination of thoughtful physical design and smart software automation creates efficient, sustainable remote lab infrastructure.

Whether you're setting up one lab or dozens, thinking through the physical setup—mobility, organization, automation, resource efficiency—pays long-term dividends.

Ready to build remote lab infrastructure? Start with the hardware that matches your needs, then add intelligence through software.

Learn more about Edrys-Lite: [edrys-labs.github.io](https://edrys-labs.github.io)

Explore our labs: [github.com/edrys-labs/lab-tubaf-embedded-systems](https://github.com/edrys-labs/lab-tubaf-embedded-systems)
