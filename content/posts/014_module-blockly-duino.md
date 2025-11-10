---
title: "The BlocklyDuino Module: Visual Programming for Everyone"
date: 2025-11-10T14:20:30+01:00
description: "Program Arduino with drag-and-drop blocks instead of code - perfect for beginners, accessible for everyone."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/module-blockly-duino/cover.png'
---

Not everyone learns programming the same way. For some students, typing code syntax is a barrier to understanding the concepts behind it. The **BlocklyDuino Module** removes that barrier by letting students program Arduino using visual blocks they can see, touch, and rearrange.

## What is BlocklyDuino?

The BlocklyDuino Module brings Google's Blockly visual programming environment to your Edrys-Lite labs, specifically tailored for Arduino development. Instead of writing text-based code, students drag and drop colorful blocks that snap together like puzzle pieces. Each block represents a programming concept - loops, conditions, sensor readings, LED control - and they only fit together in ways that make sense.

It's programming you can see and touch, making abstract concepts concrete and accessible.

## Why Visual Programming Matters

Text-based programming can be intimidating. Students struggle with syntax errors, missing semicolons, and cryptic compiler messages before they even understand what their program is supposed to do. Visual programming shifts the focus to the important part: **the logic**.

With BlocklyDuino, students can:

- **Focus on concepts** - Understand loops, conditions, and variables without syntax struggles
- **Build confidence** - Create working programs from day one
- **Learn progressively** - Start with blocks, transition to code when ready
- **Experiment freely** - Blocks only connect in valid ways, reducing errors
- **See the connection** - Watch how visual blocks translate to actual Arduino code

## Perfect for Diverse Learners

BlocklyDuino excels at meeting students where they are:

- **Beginners** get a gentle introduction to programming concepts
- **Young learners** can program without typing skills
- **Visual thinkers** see program structure at a glance
- **Students with disabilities** benefit from built-in accessibility features
- **Multi-language classrooms** work in their preferred language

The module supports keyboard navigation and accessibility helpers, making Arduino programming genuinely inclusive.

## From Blocks to Real Code

Here's the clever part: BlocklyDuino isn't just a toy - it generates real Arduino code. As students arrange blocks, they see the corresponding C++ code appear in real-time. This transparency helps students understand:

- How high-level concepts translate to actual code
- What the "magic" behind the blocks really does
- How to eventually write code themselves

Many students start with blocks and gradually transition to writing code directly, using BlocklyDuino as a bridge rather than a crutch.

## Rich Component Library

BlocklyDuino comes with blocks for dozens of Arduino operations:

- **Basic control** - Loops, conditions, delays, and logic
- **Pin operations** - Digital and analog read/write
- **Sensors** - Temperature, distance, light, motion, and more
- **Displays** - LEDs, LCD screens, and seven-segment displays
- **Communication** - Serial, I2C, and other protocols
- **Advanced functions** - Custom functions, arrays, and data structures

Students can build sophisticated projects without ever touching raw code.

## Seamless Integration

The BlocklyDuino Module works beautifully with other Edrys modules:

- Design your program with BlocklyDuino blocks
- Generate Arduino code automatically
- Send it to the [AVR8js Simulator](/blog/posts/013_module-avr8js/) for instant testing
- Or upload it via the [Terminal Module](/blog/posts/010_module-pyxtermjs/) to real hardware
- Watch results in the [Streaming Module](/blog/posts/011_module-streaming/)

Students get a complete visual programming experience from concept to execution.

## Multiple Arduino Boards

The module supports various Arduino boards with automatic pin configuration:

- Arduino Uno
- Arduino Mega
- Arduino Leonardo
- Arduino Nano
- Arduino Micro
- LilyPad Arduino
- And more

Choose your board, and BlocklyDuino adjusts available pins and features accordingly.

## Getting Started

Add visual programming to your Edrys-Lite lab with this URL:

```
https://edrys-labs.github.io/module-blockly-duino-v2/index.html
```

Students can start programming immediately - no Arduino IDE setup, no syntax memorization, no barriers. Just open the lab and start building.

## Real Learning, Visual Interface

BlocklyDuino isn't about avoiding "real" programming - it's about making programming accessible to everyone. Some students will use it as a stepping stone to text-based coding. Others will use it to build amazing projects they couldn't create otherwise. Both outcomes are equally valuable.

The module brings Arduino programming to students who might never have tried it otherwise, and it helps all students understand programming concepts more deeply by making them visible and tangible.

The BlocklyDuino Module is open source and ready to democratize Arduino education.

Explore the module on GitHub: [edrys-labs/module-blockly-duino-v2](https://github.com/edrys-labs/module-blockly-duino-v2)

Ready to make Arduino programming accessible to everyone? Add the BlocklyDuino module and watch students build what they imagine!