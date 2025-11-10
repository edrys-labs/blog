---
title: "The Survey Module: Gathering Insights from Your Students"
date: 2025-11-10T14:35:00+01:00
description: "Collect feedback, assess understanding, and visualize results - all within your remote lab environment."
draft: false
author: "Jihad Hyadi, Github Copilot"
cover: 'static/img/posts/module-survey/cover.png'
---

Teaching isn't just about delivering content - it's about understanding how students learn, what challenges they face, and whether your approach is working. The **Survey Module** brings powerful feedback collection and analysis directly into your Edrys-Lite labs, helping you make data-driven decisions about your teaching.

## What is the Survey Module?

The Survey Module transforms your Edrys-Lite lab into a feedback-gathering platform. Create custom surveys, collect student responses, and visualize results - all without leaving your classroom environment. Built on the powerful [SurveyJS](https://surveyjs.io/) framework, it handles everything from simple polls to complex multi-page questionnaires.

No external survey platforms, no separate tools, no data leaving your lab. Everything happens right where your students are already working.

## Why Integrated Surveys Matter

Using external survey tools breaks the learning flow. Students have to navigate away from their work, often losing context. The Survey Module keeps everything in one place:

- **Immediate feedback** - Ask questions right when topics are fresh
- **Contextual responses** - Students answer while still in the learning environment
- **Higher response rates** - No switching between platforms or losing links
- **Integrated workflow** - Surveys become part of the lab experience, not an interruption
- **Privacy preserved** - Data stays within your classroom

When feedback collection is seamless, you get better, more authentic responses.

## From Simple Polls to Deep Assessment

The Survey Module handles various feedback scenarios:

### Quick Understanding Checks
- "Did you understand this concept?"
- "Rate the difficulty of this exercise"
- "How confident do you feel about this topic?"

### Detailed Course Feedback
- Multi-question surveys about teaching methods
- Open-ended questions about challenges
- Rating scales for different aspects of the course

### Formative Assessment
- Self-assessment questions after exercises
- Reflection prompts after completing tasks
- Diagnostic questions to identify knowledge gaps

### Research and Data Collection
- Collect demographic information
- Gather project preferences
- Track learning progress over time

## Interactive Data Visualization

Raw survey data is just numbers. The Survey Module transforms it into insights:

- **Pie charts** - See distribution of categorical responses at a glance
- **Histograms** - Understand numerical data patterns
- **Real-time updates** - Charts refresh as new responses arrive
- **Multiple visualizations** - Each survey question gets appropriate chart types
- **Easy interpretation** - Visual patterns reveal what numbers hide

Teachers can spot trends, identify outliers, and understand their class better without being data analysts.

## Flexible Survey Design

The module supports rich question types powered by SurveyJS:

- **Text input** - Open-ended responses
- **Multiple choice** - Single or multiple selections
- **Rating scales** - Likert scales and star ratings
- **Dropdowns** - Organized option selection
- **Comments** - Longer written responses
- **Matrix questions** - Rate multiple items on the same scale
- **And more** - The full power of SurveyJS at your fingertips

Create surveys that match your assessment needs, from simple to sophisticated.

## Role-Based Access

The Survey Module respects classroom roles:

- **Students** take surveys and submit responses
- **Teachers** create surveys and view aggregated results
- **Station** stores data securely and generates visualizations

This separation ensures student privacy while giving teachers the insights they need.

## Data Privacy and Security

Survey responses are stored locally using IndexedDB, filtered by classroom ID. This means:

- **Isolated data** - Each class's responses stay separate
- **Local storage** - No external servers involved
- **Classroom control** - Data lives where you control it
- **Privacy first** - Responses don't leave your learning environment

Your students' feedback remains within your classroom ecosystem.

## Practical Use Cases

The Survey Module shines in various teaching scenarios:

### Mid-Lab Check-ins
Pause during complex exercises to gauge understanding. Adjust your teaching based on immediate feedback.

### Post-Session Reflection
After each lab, collect thoughts on what worked and what didn't. Improve your course iteratively.

### Peer Feedback
Students provide constructive feedback on group projects or presentations.

### Learning Preferences
Discover how your students prefer to learn - visual, hands-on, theoretical, etc.

### Self-Assessment
Students rate their own understanding, promoting metacognition and self-directed learning.

## Getting Started

Add feedback collection to your Edrys-Lite lab with this URL:

```
https://edrys-labs.github.io/module-survey/index.html
```

Configure your survey using simple JSON, defining questions, types, and flow. The module handles rendering, data collection, and visualization automatically.

Students see a clean, interactive survey interface. You see meaningful insights into their learning experience.

## Closing the Feedback Loop

The Survey Module isn't just about collecting data - it's about improving teaching. When you understand:

- What students find confusing
- Which exercises work best
- How confident they feel
- What pace suits them

You can adapt your teaching to serve them better. The Survey Module makes this feedback loop fast, seamless, and actionable.

Combined with other Edrys modules, it completes the picture: not just delivering content and providing tools, but understanding how well it all works.

The Survey Module is open source and ready to bring data-driven insights to your teaching.

Explore the module on GitHub: [edrys-labs/module-survey](https://github.com/edrys-labs/module-survey)

Ready to understand your students better? Add the Survey module and let data guide your teaching!