---
title: "CrossLab Project Meeting: Collaborative Remote Labs in Action"
date: 2025-12-16T09:00:00+01:00
description: "Showcasing cross-institutional collaboration at the Dortmund project meeting where Edrys powered a joint remote lab between TU Freiberg and Technische Hochschule Mittelhessen."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/crosslab-meeting-dortmund/cover.jpg'
---

From December 2-4, 2025, remote lab enthusiasts from multiple universities gathered in Dortmund for a **CrossLab project meeting**. Some institutions are formal project partners, others independent researchers—all united by interest in making laboratory education accessible beyond physical boundaries.

## The Meeting Context

The CrossLab project brings together universities exploring remote laboratory infrastructure. Our three-day meeting in Dortmund provided space for:

- **Demonstrating current solutions**: Each institution showcased their remote lab approaches
- **Sharing technical challenges**: Discussing implementation hurdles and solutions
- **Exploring collaboration opportunities**: Finding synergies between different platforms
- **Cross-institutional experiments**: Testing whether different universities' hardware can work with shared software

The atmosphere combined academic conference with technical workshop—presentations followed by hands-on demonstrations and collaborative problem-solving.

## Our Demonstration: Edrys Platform + Mobile Station

<div style="text-align: center; max-width: 60%; margin: 2em auto;">
  <img src="https://raw.githubusercontent.com/edrys-labs/blog/refs/heads/main/content/static/img/posts/crosslab-meeting-dortmund/edrys+station.jpg" alt="Edrys and Mobile Lab Station" style="max-width: 50%; border: 1px solid #ddd; border-radius: 4px;" />
  <p style="font-style: italic; color: #666; margin-top: 0.5em;">Edrys and Mobile Lab Station</p>
</div>

We showcased two key components of our remote lab infrastructure:

### 1. The Edrys Platform

We demonstrated the [Edrys-Lite](https://edrys-labs.github.io/) platform's capabilities:

- **Rapid lab deployment**: Creating new lab configurations in minutes
- **Modular architecture**: Combining [Editor](/blog/posts/009_module-editor), [Terminal](/blog/posts/010_module-pyxtermjs), [Streaming](/blog/posts/011_module-streaming), and other modules
- **Flexible room structures**: Supporting different learning pathways within single labs
- **Student management**: Self-assignment, room navigation, code logging

Attendees saw how the platform handles the software orchestration that makes remote experimentation practical.

### 2. The Physical Infrastructure

We presented our [mobile lab station](/blog/posts/025_mobile-lab-station)—the custom-built frame hosting four embedded systems labs:

- **Portability**: Demonstrated by literally wheeling it to the meeting venue
- **Intelligent automation**: Smart lighting responding to station occupancy
- **Multi-lab hosting**: Four complete labs served by two computers
- **Organized cabling**: Clean integration despite multiple peripherals per lab

The physical station answered a key question: "Where does the hardware actually live?" Our solution shows that remote lab infrastructure can be compact, mobile, and intelligently managed.

## The Collaboration: AVR128DB48 Lab with THM

<div style="text-align: center; max-width: 60%; margin: 2em auto;">
  <img src="https://raw.githubusercontent.com/edrys-labs/blog/refs/heads/main/content/static/img/posts/crosslab-meeting-dortmund/AVR128DB48_lab.jpg" alt="AVR128DB48 Lab" style="max-width: 50%; border: 1px solid #ddd; border-radius: 4px;" />
  <p style="font-style: italic; color: #666; margin-top: 0.5em;">AVR128DB48 Lab Overview</p>
</div>

The meeting's highlight was demonstrating **cross-institutional collaboration** through a jointly developed remote lab. We partnered with the [MICRO](https://micro.mni.thm.de/en) team from **Technische Hochschule Mittelhessen (THM)** to create a comprehensive embedded systems lab using their AVR128DB48 hardware setup.

The MICRO project develops innovative teaching materials for microcontroller education, and their AVR128DB48 board includes LEDs, RGB systems, sensors (photoresistor, color sensor), I2C display, and servo motor—perfect for demonstrating professional embedded development beyond Arduino-level programming.

We configured Edrys modules ([Editor](/blog/posts/009_module-editor), [Terminal](/blog/posts/010_module-pyxtermjs), [Streaming](/blog/posts/011_module-streaming)) to provide complete remote access. The terminal handles the full AVR toolchain—`avr-gcc` compilation with device packs and `pymcuprog` uploads via the `nedbg` interface.

Students progress through five tasks (I/O control, PWM, ADC, I2C, servo) culminating in an environmental monitoring integration project. This proves key concepts:

- **Platform independence**: Edrys adapts to any hardware (Arduino, Calliope, AVR128DB48)
- **Institution-agnostic**: THM's hardware + our software infrastructure work seamlessly
- **Shared maintenance**: THM maintains hardware, we provide software platform
- **Knowledge transfer**: Each institution contributes expertise

## Reactions and Impact

The demonstration sparked productive conversations about technical implementation (toolchain handling, video synchronization, security), pedagogy (simulation-to-hardware transitions, student feedback, assessment integration), and collaboration opportunities (cross-platform compatibility, shared expensive equipment).

The discussions revealed both solution maturity and areas for development—key questions about bandwidth requirements, institutional network challenges, and backup strategies for lab availability.

## Why This Matters

The THM collaboration demonstrates a future where hardware expertise stays with specialized institutions, software platforms provide standardized remote access, and expensive equipment serves students across multiple universities. Instead of duplicating identical labs everywhere, institutions specialize and share access through platforms like Edrys.

The AVR128DB48 lab proves that remote lab infrastructure can genuinely connect universities, share resources, and expand access to hands-on learning. The partnership with THM's [MICRO team](https://micro.mni.thm.de/en/team) continues beyond the meeting, refining the AVR128DB48 lab and exploring advanced topics. 

## Building Bridges, Not Silos

The CrossLab meeting reinforced that remote labs succeed through collaboration, not competition. Each institution brings unique strengths—hardware expertise, software platforms, pedagogical innovation, diverse student populations. Combining these across institutional boundaries creates laboratory education that's more accessible and sustainable than isolated efforts.

The Dortmund gathering catalyzed ongoing collaborations in cross-platform lab sharing, assessment frameworks, and instructor dashboards for multi-institutional management.

Ready to explore cross-institutional remote lab collaboration? The platform is ready, the examples exist—now it's about building partnerships.

Learn more about Edrys-Lite: [edrys-labs.github.io](https://edrys-labs.github.io)

Learn more about CrossLab: [cross-lab.org](https://cross-lab.org)
