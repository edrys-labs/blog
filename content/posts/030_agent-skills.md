---
title: "Agent Skills for Edrys-Lite: Let Your AI Assistant Build Labs and Modules"
date: 2026-10-27T09:00:00+01:00
description: "Two Agent Skills teach AI coding assistants like Claude Code, GitHub Copilot and Cursor how Edrys-Lite works, so they can build classroom configurations and write new modules that actually load, validate and run."
draft: false
author: "Jihad Hyadi"
cover: 'static/img/posts/agent-skills/cover.png'
---

Building an Edrys-Lite lab means knowing which modules exist, which config keys each one reads, which message subjects connect an editor to a runner, and where each module belongs: Lobby, room or station. Writing a new module means learning the `edrys.js` API, meta tags, roles and shared state. AI assistants are good at this kind of work, but on their own they know little about Edrys and will guess: a made-up module URL, a config key that does nothing, an editor whose **Execute** button sends a message nobody listens to.

To fix that, we've published [**edrys-labs/skills**](https://github.com/edrys-labs/skills): two [Agent Skills](https://agentskills.io) that give an AI assistant what it needs to build labs and modules correctly.

## What Are Agent Skills?

An Agent Skill is a folder with instructions, reference files, examples and helper scripts. Agents such as **Claude Code**, **GitHub Copilot**, **Cursor**, **Gemini CLI** and [many others](https://agentskills.io/clients) load a skill on demand: when a request matches the skill's description, the agent reads its instructions and follows them. Nothing changes in how you work. You describe what you want in plain language, in English or German, and the right skill activates on its own.

The repository contains two skills:

| Skill | For |
|-------|-----|
| **edrys-lab** | Teachers and lab authors: build a classroom from existing modules |
| **edrys-module** | Developers: write a new module |

## edrys-lab: From an Idea to a Ready-to-Import Lab

Ask for a lab, and the skill guides the agent through the same steps an experienced lab author would take:

1. **Gather** what the request leaves open: the subject, the hardware, whether a station computer is available, group rooms or one Lobby, individual or shared work.
2. **Pick modules** from a catalog of the published edrys-labs modules: Markdown, Monaco editor, terminal, streaming, serial, the [AVR8js](/blog/posts/013_module-avr8js/) and [MicroPython](/blog/posts/029_module-micropython-simulator/) simulators, whiteboard, survey, [hardware control](/blog/posts/027_module-hardware-control/) and more. Each module has its own catalog file with its URL, config schema, defaults and pitfalls.
3. **Lay out rooms**: the task description in the Lobby, hardware tools at the station, simulations where students work.
4. **Write role content** in `config`, `studentConfig`, `teacherConfig` and `stationConfig`, including setup instructions for whoever runs the station.
5. **Validate** the result with a script that fetches every module and checks each config against that module's own schema.
6. **Deliver** the YAML file, plus the `docker run` line and setup steps for a station lab, or, on request, a complete lab repository with a README and a deploy button.

A prompt like this one:

> *Build a remote lab for an Arduino Uno: students write code in an editor, it is compiled and uploaded at the station, and they watch the board through a webcam.*

produces a classroom file with a shared editor, a camera stream and a terminal at the station that compiles and uploads the sketch, wired together so that Execute actually reaches the board. Prompts like *"Make an Arduino lab without hardware for 30 students"* or *"Erstelle ein Edrys-Labor für einen Linux-Kurs mit einer gemeinsamen Shell"* work the same way.

The skill also helps with debugging. Paste your classroom file and ask *"Students press Execute and nothing happens. Why?"*, and the agent checks subjects, rooms and `showInCustom` against the catalog instead of guessing.

The skill ships with four tested example labs the agent starts from rather than writing a blank file:

- **avr8js-simulation**: no station, each student runs their own simulated Arduino
- **terminal**: a shared Linux shell from a station
- **arduino**: a real Arduino with a shared editor, camera and compile-and-upload terminal
- **micropython-web-serial**: a board's REPL over Web Serial, with no server at the station

## edrys-module: Writing New Modules

When no existing module does the job, the second skill takes over. It covers everything a module needs:

- the **`edrys.js` API**: `onReady`, `sendMessage`, `onMessage`, `getState`, awareness and streams
- **meta tags** and the `module-config` schema that generates the settings form in Edrys
- **roles and stations**: who sees the module, and how a station module talks to hardware via Web Serial, a camera or a local server
- **when to use what**: messages for events, shared Yjs state for documents that late joiners must see, streams for video
- a **consistent look** shared with the other edrys-labs modules
- **testing** with several peers and with [edrys-module-tests](https://github.com/edrys-labs/edrys-module-tests), and **publishing** on GitHub Pages

The skill also tells the agent to check first whether a module is needed at all. Often an existing module, or an existing web tool embedded in the iframe module, is enough.

Four tested example modules serve as starting points: a **minimal** skeleton, a **countdown** written as a single YAML file, a **shared checklist** using Yjs state and awareness, and a **serial bridge** that forwards Web Serial input and output from the station to the room. A check script reviews the finished module, and a small dev server lets you add it to a real classroom at `http://localhost:8080/` and test it with a second browser window as a student.

## Installation

The quickest way is the [`npx skills`](https://github.com/vercel-labs/skills) CLI, which detects the agents you have installed and puts the skills in the right place:

```bash
# Install both skills
npx skills add edrys-labs/skills

# Or just one of them
npx skills add edrys-labs/skills --skill edrys-lab

# For a specific agent
npx skills add edrys-labs/skills -a claude-code
```

You can also copy the folders by hand, for example into `.claude/skills/` for Claude Code or `.agents/skills/` for Copilot, Cursor and Gemini CLI.

### On claude.ai

No local setup? The skills also work on [claude.ai](https://claude.ai). Download [edrys-lab.zip](https://github.com/edrys-labs/skills/releases/latest/download/edrys-lab.zip) and [edrys-module.zip](https://github.com/edrys-labs/skills/releases/latest/download/edrys-module.zip) from the latest release, upload them under *Customize → Skills* and switch them on (code execution must be enabled).

This is a good option for teachers who build labs from existing modules. For developing modules or setting up stations, a local agent is the better choice, because testing with several peers, the dev server and the hardware all need your own machine.

## A Word of Caution

The skills give an agent knowledge and checks it would otherwise lack, but they don't guarantee a correct result. Agents still make mistakes, especially on complex tasks such as labs with several stations or new hardware. Before using anything an agent produced in class:

- load the lab or module in a real classroom, with a second browser as a student and, if needed, the station
- check that the hardware, ports and wiring match the configuration, since the validators can't see them
- read any code the agent wrote before running it at a station that controls real devices

## Open Source

The skills are open source and available on GitHub: [edrys-labs/skills](https://github.com/edrys-labs/skills). If an agent gets something wrong, or a module is missing from the catalog, open an issue or a pull request. Every fix makes the next lab better for everyone.

Learn more about Edrys-Lite: [edrys-labs.github.io](https://edrys-labs.github.io)
