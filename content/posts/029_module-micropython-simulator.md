---
title: "The MicroPython Simulator: Calliope mini and micro:bit in the Browser"
date: 2026-10-26T09:00:00+01:00
description: "Run MicroPython programs on a simulated Calliope mini 3 or BBC micro:bit v2 directly in Edrys, with working LEDs, buttons, sensors, sound and a serial terminal, and no hardware needed."
draft: false
author: "Jihad Hyadi"
cover: 'static/img/posts/module-micropython-simulator/cover.png'
---

Our [Calliope mini remote lab](/blog/posts/024_remote-lab-calliope-mini/) showed how approachable embedded programming becomes with MicroPython. But a remote lab station has one board, and only one student can run code on it at a time. The new **MicroPython Simulator Module** gives every student their own board: a simulated **Calliope mini 3** or **BBC micro:bit v2**, running real MicroPython right in the browser.

## What Is the MicroPython Simulator?

The module runs Python programs on a simulated board and shows its serial output (`print` output and tracebacks) in a terminal underneath. The simulated board behaves like the real one:

- **5×5 LED matrix** for images, text and animations
- **Buttons and pins** you can click directly on the board
- **Sound** from the speaker
- **Sensors** such as temperature, light, accelerometer and compass, controlled with sliders

Underneath, it uses the official simulators from the Calliope and micro:bit Python editors, which are MicroPython compiled to WebAssembly. The firmware is the same, so a program written for the simulator also runs on a physical board, as long as it imports the right board module: `from calliopemini import *` on the Calliope mini 3 or `from microbit import *` on the micro:bit.

## How It Works

Like the [AVR8js Simulator](/blog/posts/013_module-avr8js/), the module pairs with an editor. Students write code in an editor module such as [module-monaco-editor](https://github.com/edrys-labs/module-monaco-editor), click execute, and the program starts on the simulated board straight away. There is no flashing, no USB cable and no drivers to install.

The status badge in the header shows whether the board is `idle`, `running`, `stopped` or in `error`. **Stop** halts the program, and the ▶ button on the board runs it again from the beginning. When a program ends, the board drops into MicroPython's `>>>` prompt, so students can keep experimenting interactively: type `6*7`, get `42`.

## Serial Input and Output

The terminal works in both directions. Anything typed into the input field is sent to the board as if it came over the serial line, so programs can use `input()`:

```python
from calliopemini import *

while True:
    command = input("command (heart, happy, clear)? ")
    if command == "heart":
        display.show(Image.HEART)
    elif command == "happy":
        display.show(Image.HAPPY)
    elif command == "clear":
        display.clear()
    else:
        print("unknown command:", command)
```

Send `heart` and a heart appears on the LEDs. Send `hello` and the terminal answers with `unknown command: hello`. It's a small exercise, but it covers the core of serial communication, which students need on real hardware too.

## Sensors Without a Lab

Real sensors are hard to teach remotely: you can't warm up a temperature sensor through a webcam. In the simulator, a slider does the job. A single configuration line chooses which sensor controls appear below the board:

```yaml
board: calliope-mini-3
sensors: temperature:0:40, lightLevel
```

This adds a temperature slider (0 to 40 °C) and a light level slider. Students can then write a program that reacts to them:

```python
from calliopemini import *

while True:
    temp = temperature()
    light = display.read_light_level()
    print("temperature:", temp, "light:", light)
    if temp > 30:
        display.show(Image.SAD)
    elif light < 50:
        display.show(Image.ASLEEP)
    else:
        display.show(Image.HAPPY)
    sleep(1000)
```

Moving the sliders changes the face on the board instantly. Available sensors include temperature, light level, sound level, all three accelerometer axes, gestures (`shake`, `face up`, `freefall`, …), compass heading and the magnetic field. Use `sensors: all` to show every control.

## Configuration

The module only needs a handful of options:

```yaml
board: calliope-mini-3      # or microbit-v2
execute: execute            # message subject to run code from
sensors: temperature:0:40, lightLevel, gesture
synchronize: false
```

By default, each student runs only their own code on their own board. With `synchronize: true`, a program from anyone in the room starts on every peer. This is useful when a teacher wants to demonstrate something to the whole class. Each peer still runs its own simulation, so button presses and sensor values stay local, and students who join later or reload the page get the current program too.

The module also accepts multi-file projects from the monaco-editor: every file is placed on the board's filesystem and `main.py` runs, so students can split their code into modules just as they would on a real board.

## Private and Self-Contained

The simulators are bundled with the module, so it depends on no external site and **no code is sent to a server**: everything runs in the student's browser. That keeps the module reliable in class and simple to host, and it means a single static page can serve any number of students.

## Simulation and Real Hardware, Together

The simulator doesn't replace our physical Calliope mini lab; it prepares students for it. A natural workflow:

1. **Explore** MicroPython on the simulator, where everyone has a board and nothing can break
2. **Test** sensor logic with sliders before relying on real readings
3. **Move to hardware** with working code in a remote lab station with live [Streaming](/blog/posts/011_module-streaming/)

Students can also practise at home before or after a lab session, without needing their own hardware.

## Getting Started

Add the module to your Edrys-Lite lab with this URL:

```
https://edrys-labs.github.io/module-micropython-simulator/index.html
```

Combine it with an editor module that sends code with the subject `execute`, choose your board, and you're ready.

## Credits and Open Source

The module is built on the [micro:bit MicroPython simulator](https://github.com/microbit-foundation/micropython-microbit-v2-simulator) by the Micro:bit Educational Foundation and the [Calliope fork](https://github.com/calliope-edu/micropython-simulator) by Calliope gGmbH. Thanks to both teams for making their work open source.

The module itself is MIT-licensed and available on GitHub: [edrys-labs/module-micropython-simulator](https://github.com/edrys-labs/module-micropython-simulator)

Learn more about Edrys-Lite: [edrys-labs.github.io](https://edrys-labs.github.io)
