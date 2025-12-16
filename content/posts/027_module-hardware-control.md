---
title: "Remote Hardware Control: Bridging Virtual and Physical Interfaces"
date: 2025-12-16T10:00:00+01:00
description: "How the Hardware Control Module uses Digilent Analog Discovery 2 to enable remote button presses and potentiometer adjustments for embedded systems labs."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/module-hardware-control/cover.png'
---

Remote labs let students write code and see results via live video, but physical interaction—pressing buttons, adjusting potentiometers—traditionally requires being physically present. Our **Hardware Control Module** uses the [Digilent Analog Discovery 2](https://digilent.com/shop/analog-discovery-2-100ms-s-usb-oscilloscope-logic-analyzer-and-variable-power-supply/) to enable remote button presses and potentiometer adjustments through a web interface.

## Inspired by THM's MICRO Team

During our collaboration with the [MICRO](https://micro.mni.thm.de/en) team from Technische Hochschule Mittelhessen, we discovered their impressive remote lab platform that already featured hardware control through the Analog Discovery 2. Their implementation demonstrated how professional test equipment could enable genuine physical interaction in remote labs—not just observation, but actual button presses and voltage adjustments.

This inspired us to develop our own hardware control module for Edrys, adapting the concept to work within the Edrys architecture. While the MICRO team's solution was built for their specific platform, we wanted to create a modular component that could integrate seamlessly with the existing Edrys modules.

## How It Works

The **Digilent Analog Discovery 2 (AD2)** is a versatile USB device combining oscilloscope, logic analyzer, and programmable voltage source. We use its digital I/O pins to simulate button presses and analog outputs to emulate potentiometer voltage.

Three components work together:

1. **Frontend Module**: Provides buttons and sliders in the web interface
2. **Backend Server**: Flask server communicating with the AD2 via REST API
3. **Physical Hardware**: Microcontroller connected to the AD2

When a student clicks a button, the module sends a message via Edrys. Only the station (where hardware exists) executes the command, activating the appropriate AD2 pin. The microcontroller detects the input change, and results appear in the code output and live video feed. All users see synchronized UI state.

## Configuration Example

Adding hardware control requires minimal configuration:

```json
{
  "serverUrl": "http://localhost:5005",
  "components": [
    {"type": "button", "name": "Button 1", "pin": 4},
    {"type": "button", "name": "Button 2", "pin": 5},
    {"type": "potentiometer", "name": "Voltage Control", "channel": 0}
  ]
}
```

This creates two remote buttons connected to AD2 digital pins 4 and 5, plus a potentiometer controlling analog output channel 0 (W1).

## Backend Server

The server runs locally on the station computer with the AD2 connected via USB:

```bash
docker run -it -p 5005:5005 --device=/dev/bus/usb:/dev/bus/usb \
  edryslabs/module-hardware-control-server:latest
```

The Flask backend exposes REST endpoints for button presses, releases, and voltage adjustments, using the `pydwf` library to communicate with the AD2.

## Real-Time Synchronization

Multiple students can join simultaneously. The module synchronizes UI state across all connected users—when one student presses a button, everyone sees it pressed. Commands execute only on the station, preventing conflicts while maintaining shared awareness.

## Why This Matters

This module demonstrates that **remote labs can provide genuine hands-on interaction, not just observation**. The AD2 integration shows how existing professional test equipment can enhance remote lab capabilities without additional hardware purchases.

The module works alongside other Edrys components—[Editor](/blog/posts/009_module-editor), [Terminal](/blog/posts/010_module-pyxtermjs), and [Streaming](/blog/posts/011_module-streaming)—creating a complete remote lab experience where students control hardware, write code, and see real-time results.

## Open Source and Extensible

The module and backend server are open source, available on the [Edrys Labs GitHub](https://github.com/edrys-labs/module-hardware-control). The architecture supports extensions for additional component types, other programmable hardware, and enhanced UI elements.

Ready to add hardware interaction to your remote labs? The module is available now.

Explore the module: [github.com/edrys-labs/module-hardware-control](https://github.com/edrys-labs/module-hardware-control)

Learn more about Edrys-Lite: [edrys-labs.github.io](https://edrys-labs.github.io)
