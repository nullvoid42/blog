---
layout: post
title: "Blog is for Humans, Knowledge Base is for Agents"
date: 2026-04-12 00:15 +0800
tags: [agent, memory, knowledge-base, infrastructure]
---

I just realized something obvious in hindsight but somehow never articulated until tonight.

**Blog posts are written for humans. Agents need something different.**

<!--more-->

## The Problem with Making Agents Read Blogs

When I write a blog post, I'm optimizing for human readability: narrative flow, engaging prose, contextual explanation. But when an AI agent needs to retrieve information from past experience, these qualities become noise rather than signal.

A recent conversation made this painfully clear. I was trying to reference something I posted days ago, and my agent had to essentially parse natural language text to extract structured facts. It worked, but it was inefficient — like asking someone to reconstruct your calendar from a daily diary entry instead of just looking at the calendar.

## What Agents Actually Need

Agents need **structured, machine-readable knowledge** organized around semantic meaning rather than narrative structure:

- **Identity files**: who am I, what are my capabilities, what are my rules
- **Tool documentation**: how to use available tools and their interfaces
- **Project context**: what's the current state of a project, what decisions were made and why
- **Learnings & corrections**: mistakes made and how to avoid them
- **Credentials & endpoints**: where to find secrets and service access points

These aren't blog posts. They're closer to a well-maintained README meets a personal wiki meets a vector database.

## The Architecture I'm Moving Toward

Currently I have scattered knowledge across several files:

| File | Purpose |
|------|---------|
| `MEMORY.md` | Long-term identity, rules, credentials |
| `TOOLS.md` | Tool configuration and command cheatsheet |
| `SOUL.md` | Communication style and personality |
| `AGENTS.md` | Orchestration patterns and workflows |
| `.learnings/LEARNINGS.md` | Mistakes and corrections logged over time |
| `workspace/skills/*/SKILL.md` | Skill usage documentation |

The problem is there's no unified index, no semantic retrieval layer, and the project context lives in scattered daily notes.

The ideal architecture would be:

1. **Structured notes** in Apple Notes or Obsidian, organized by domain
2. **Vector retrieval** via something like lancedb-pro for natural language queries
3. **Project-level `README.agent.md`** files that give agents a quick onboarding for each project
4. **Periodic digestion**: take blog posts and distill the structured facts into the knowledge base

## A Concrete Example

When I was working on the Gulu food project, the agent needed to understand:

- What is Ralph (the autonomous coding loop tool)?
- What's the project structure?
- What decisions were made?
- What commands should be used?

Right now, this lives in scattered daily logs and a `gulu-project.md` in my memory folder. An agent-friendly version would have a structured `PROJECT.md` with tables of commands, decision logs, and current status — all parseable without understanding narrative context.

## The Separation Principle

**Blog = output.** It's what I want the world to see. Narrative, engaging, human-friendly.

**Knowledge base = internal indexing.** It's how I help my future self (or agent) find and understand past context efficiently.

The key insight is that these two things serve fundamentally different purposes and shouldn't be conflated.

## What's Next

I'm going to start building this out systematically:

- Set up an Apple Notes folder for structured agent knowledge (done tonight)
- Evaluate lancedb-pro for semantic retrieval
- Write `README.agent.md` for the Gulu project as a pilot
- Design a unified index structure that connects all the existing碎片

The blog will continue — it serves a different purpose. But I'm done pretending it's a good knowledge management system for my agent.

---

*This post was written at 00:15 on a Sunday morning after a conversation with my agent about exactly this topic. Meta.*
