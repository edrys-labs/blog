---
title: "The Code Logger Module: Understanding How Students Code"
date: 2025-11-10T14:40:00+01:00
description: "Track student coding activity in real-time - helping you provide better support and understand learning patterns."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/module-code-logger/cover.png'
---

Teaching programming means understanding not just what students produce, but how they work. Do they iterate quickly or get stuck? Do they experiment or follow patterns? When do they need help? The **Code Logger Module** gives teachers visibility into student coding activity, enabling better support and deeper insights into learning patterns.

## What is the Code Logger Module?

The Code Logger Module is a teaching tool that tracks code execution in your Edrys-Lite labs. When students run code in the [Editor Module](/blog/posts/009_module-editor/), the Code Logger quietly records it. Teachers can then view this history to understand student work patterns, identify struggles, and provide timely assistance.

It's like having a window into your students' coding process without looking over their shoulders.

## Why Track Code Execution?

In traditional classrooms, teachers can walk around and observe students working. In remote labs, that visibility disappears. The Code Logger restores it:

- **Understand work patterns** - Observe how students approach problems
- **Spot common errors** - Notice mistakes appearing across multiple students
- **Track progress** - Watch how student code evolves over time
- **Provide targeted support** - Base your assistance on actual work, not guesses

Instead of waiting for students to ask for help, you can proactively offer it when you see they need it.

## Real-Time Activity Monitoring

The Code Logger captures code execution as it happens:

- Every time a student clicks "execute" in the editor, their code is logged
- Timestamps show when students are actively working
- Sequential logs reveal the progression of their thinking
- Inactivity becomes visible, flagging potential stuck points

This real-time stream helps teachers stay connected to the classroom's pulse, even remotely.

## Privacy-Respecting Design

The Code Logger is designed for education, not surveillance:

- **Anonymous submissions** - Code is logged without identifying individual students
- **Teacher-only access** - Only teachers see logged code in their station view
- **Purpose-specific** - Tracks executed code, not every keystroke
- **Local storage** - Data stored in IndexedDB, not sent to external servers
- **Classroom-isolated** - Each class's logs remain separate

The goal is pedagogical insight, not intrusive monitoring.

## Understanding Learning Patterns

The Code Logger reveals valuable teaching insights:

- **Common mistakes** - Spot errors appearing across multiple students
- **Stuck points** - Notice when activity drops, signaling difficulty
- **Iteration patterns** - See how students approach problem-solving
- **Progress tracking** - Watch code evolve during lab sessions

This anonymous data helps you identify where to focus your teaching without singling out individuals.

## Complementing Other Modules

The Code Logger works seamlessly with the [Editor Module](/blog/posts/009_module-editor/):

- Students write and execute code normally in the editor
- The logger captures execution events automatically
- Teachers view logs in their station interface
- No student workflow disruption

It's an invisible teaching assistant, providing insights without interfering with learning.

## Getting Started

Add code monitoring to your Edrys-Lite lab with this URL:

```
https://edrys-labs.github.io/module-code-logger/
```

Once added to your lab, the module automatically begins logging code execution from the Editor Module. Teachers access logs through their station view, where they can browse student activity and search through code history.

No configuration needed - it just works.

## Teaching with Data, Not Guesswork

The Code Logger Module transforms teaching from reactive to proactive. Instead of wondering why students struggle or who needs help, you see it directly. Instead of guessing at common problems, you identify them from actual student work.

This visibility makes remote teaching feel less remote. You regain the awareness that comes from walking around a physical classroom, adapted for the digital environment.

Combined with modules like the [Survey Module](/blog/posts/017_module-survey/) for explicit feedback and the Code Logger for behavioral data, you get a complete picture of how your students learn.

The Code Logger Module is open source and ready to bring insight to your programming instruction.

Explore the module on GitHub: [edrys-labs/module-code-logger](https://github.com/edrys-labs/module-code-logger)

Ready to understand how your students code? Add the Code Logger module and see learning in action!