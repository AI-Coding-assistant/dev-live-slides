---
title: Coding Agent Showdown
sub_title: From Vibe to Enterprise Standard
author: Neeraj Garg (@garg)
theme:
  name: dark
options:
  end_slide_shorthand: true
---

# And AI says hi to you

```bash +exec
./copresenter --new "Say hi to the Noida Developers Day Live audience"
```

---
# Not just any kind of AI

```banner +animate:rainbow +loop
Agentic
```
---

# What

- Smarter autocomplete
- Chat with your code base, ask questions
- Agents in your IDE
- __Standalone agents in your CLI__ (we are here)
- Standalone agents in the cloud

---

```ascii
┌──────────────────────────────────────────────────────────┐
│                        CLOUD                             │
│                  ┌──────────────────┐                    │
│                  │   Claude Model   │                    │
│                  │   (Sonnet 4.5)   │                    │
│                  └────────▲─────────┘                    │
└───────────────────────────┼──────────────────────────────┘
                            │ API calls
┌───────────────────────────┼──────────────────────────────┐
│                  LOCAL ENVIRONMENT                       │
│                  ┌────────▼─────────┐                    │
│                  │  Agent Harness   │                    │
│                  │ (orchestration)  │                    │
│                  └────────┬─────────┘                    │
│         ┌─────────────────┼─────────────────┐            │
│         │                 │                 │            │
│    ┌────▼─────┐     ┌─────▼─────┐      ┌────▼─────┐      │
│    │ File I/O │     │   Bash    │      │   MCP    │      │
│    │  Tools   │     │   Tools   │      │ Servers  │      │
│    └────┬─────┘     └─────┬─────┘      └────┬─────┘      │
│         └─────────────────┼─────────────────┘            │
│                   ┌───────▼─────────┐                    │
│                   │  Your Codebase  │                    │
│                   │  & Environment  │                    │
│                   └─────────────────┘                    │
└──────────────────────────────────────────────────────────┘
```

---

# Standards & Configuration

```banner +animate:rainbow +loop
STANDARDS
```

---

# Standards & Configuration

- **MCP** - Model Context Protocol for extending agent capabilities
- **AGENTS.md** - Project-specific agent instructions
- **AgentSkills** - On-demand skill modules

These standards help agents understand your codebase and workflows

---
# MCP

```banner +animate:matrix +loop
MCP
```
---

```bash +exec
./copresenter "Remind me what MCP stands for"
```

---

# AGENTS.md

```banner +animate:matrix +loop
AGENTS.md
```

---

```ascii +animate:typewriter +once
┌────────────────────┐          ┌────────────────────┐
│                    │          │                    │
│    ~/AGENTS.md     │          │    ./AGENTS.md     │
│~/.claude/CLAUDE.md │          │    ./CLAUDE.md     │
│                    │          │                    │
└────────────────────┘          └────────────────────┘
           │                               │
           │                               │
           └────injected into (almost) ────┘
                     every  prompt
                          │
                          ▼
                     ┌─────────┐
                     │ Coding  │
                     │  Agent  │
                     └─────────┘
```

---

> Agents.md in AEM project: https://github.com/adobe/helix-website/blob/main/AGENTS.md


```bash +exec
./copresenter "why should we use Agents.md while working with coding agents, answer in bullet points ?"
```






---

# AgentSkills

```banner +animate:matrix +loop
AgentSkills
```

---

```ascii +animate:matrix
         ┌────────────────────────────────────┐
     ┌───│  .claude/skills/search/SKILLS.md   │
     │   └────────────────────────────────────┘
     │       ┌────────────────────────────────────┐
     ├───────│   .claude/skills/test/SKILLS.md    │
     │       └────────────────────────────────────┘
     │           ┌────────────────────────────────────┐
     ├───────────│    .claude/skills/pr/SKILLS.md     │
     │           └────────────────────────────────────┘
     │
     ▼
┌─────────┐
│ Coding  │ list skills at start of
│  Agent  │ session, load on demand
└─────────┘
```

---

# What skills can do

- make your agent more __skilled__
- are used on-demand
- don't consume *context* by default
- turn multi-step tasks into consistent workflows

<!--

Note: context is the hard currency of coding agents. you want to preserve them,
protect them, and use them wisely.

-->
---

```bash +exec
./copresenter "Which coding agents currently support AgentSkills"
```

---

# Advanced Tools & Techniques

```banner +animate:rainbow +loop
POWER USER
```

---

# Advanced Tools & Techniques

- **`--dangerously-skip-permissions`** - Skip safety prompts (YOLO mode)
- **Multitasking** - Run multiple agents in parallel
- **Git Worktrees** - Isolated workspaces for parallel development

Unlock the full potential of coding agents

---

# `--dangerously-skip-permissions`

```banner:block +animate:matrix +loop
YOLO
```

---

```ascii +animate:fire +loop
  /\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\
  ////////////////////////// DANGER ZONE ////////////////////////
  /\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\
                                /\
                               /!!\
                              /!!!!\
                             /!!!!!!\
                            /!!!!!!!!\
                            \!!!!!!!!/
                             \!!!!!!/
                              \!!!!/
                               \!!/
                                \/
  /\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\/\
  ///////////////////////////////////////////////////////////////
```

Skips all permission prompts for file operations (and this is where the _fun_ begins)

---
## Normal operations

The agent will ask for permission for any potentially sensitive, or destructive operation.

## How you will feel

Assured, and bored.

## Escape the sandbox


---

# Multitasking/Multi-Clauding

```banner:ogre +animate:fire +loop
PARALLEL
```

---

```ascii +animate:matrix
┌─────────────────┐  ┌─────────────────┐  ┌─────────────────┐
│   Terminal 1    │  │   Terminal 2    │  │   Terminal 3    │
│                 │  │                 │  │                 │
│  $ claude       │  │  $ codex        │  │  $ gemini       │
│  Building...    │  │  Testing...     │  │  Documenting... │
│                 │  │                 │  │                 │
│  [████░░] 60%   │  │  ✓ 47 passed    │  │  Writing API    │
│                 │  │  ⚠ 2 warnings   │  │  docs...        │
└─────────────────┘  └─────────────────┘  └─────────────────┘
         │                    │                    │
         └────────────────────┼────────────────────┘
                              │
                    ┌─────────▼──────────┐
                    │   Same Codebase    │
                    │  Different Tasks   │
                    └────────────────────┘
```

---

# Why run multiple agents?

- **Different tasks in parallel**: Build, test, document simultaneously
- **Different branches**: Work on features while fixes run in main
- **Context isolation**: Each instance focuses on one specific task
- **Faster iteration**: Don't wait for one task to finish before starting another

---

# Git Worktrees

```banner:small +animate:matrix +loop
WORKTREE
```
---

![Firefly_Gemini Flash_Create a pixel-art illustration (8-bit) of a forest of little trees](worktrees.png)

---

```ascii +animate:matrix
                    main repo (.git)
                          │
            ┌─────────────┼─────────────┐
            │             │             │
         claude-1      codex-2        gemini-3
         (main)        (feature-a)   (feature-b)
            │             │             │
         ┌──▼──┐       ┌──▼──┐       ┌──▼──┐
         │ 📁  │       │ 📁  │       │ 📁  │
         │ src │       │ src │       │ src │
         └─────┘       └─────┘       └─────┘
           │             │             │
        claude         codex        gemini
       instance 1    instance 2    instance 3
```

---

# What are Git Worktrees?

Multiple working directories attached to the same repository
- Each worktree can check out a different branch
- Share the same `.git` database (efficient!)
- Work on multiple features/branches simultaneously

# Why They're Perfect for Agents

- Run multiple agents on different branches
- No context switching or stashing required
- Agents can work in parallel without conflicts
- Test features independently while keeping main clean

# Automatic Worktree Detection in **AEM**

`aem up` automatically detects when it's launched in a Git worktree and will pick a non-conflicting port: run as many dev servers as you have worktrees.

---

# Guardrails/Attribution/Transparency

```banner +animate:breathe +loop
SAFETY
```
---

# Guardrails/Attribution/Transparency

```ascii +animate:matrix
┌────────────────────────────────────────┐
│                                        │
│                 GitHub                 │
│                                        │
└─────────▲─────────────────────▲────────┘
          │                     │
┌─────────┴───────┐    ┌────────┴────────┐
│    ┏━━━━━━━━┓   │    │    ┏━━━━━━━┓    │
│    ┃        ┃   │    │    ┃       ┃    │
│    ┃   gh   ┃   │    │    ┃  git  ┃    │
│    ┃        ┃   │    │    ┃       ┃    │
│    ┗━━━━━━━━┛   │    │    ┗━━━━━━━┛    │
│  ai-aligned-gh  │    │ ai-aligned-git  │
└─────────────────┘    └─────────────────┘
         ▲                      ▲
         │                      │
         │     ┌─────────┐      │
         │     │ Coding  │      │
         └─────│  Agent  │──────┘
               └─────────┘
```

---

## Guardrails/Attribution/Transparency

When making changes on github.com (commits, comments, pull requests), attribute them to AI.

This helps reviewers not waste their "Herzblut" on your vibe-coded output.

- https://github.com/trieloff/ai-aligned-gh
- https://github.com/trieloff/ai-aligned-git


---

## Coding Agents: Strengths & Limits

<!-- column_layout: [1, 1] -->
<!-- column: 0 -->

### ✅ Where They Excel

<!-- incremental_lists: false -->

- **Source code** - Natural playground
- **CLI commands** - Fluent & reliable
- **CLI background tasks** - Emerging (Claude leads)

<!-- column: 1 -->

### ⚠️ Where They Struggle

<!-- incremental_lists: false -->

- **Text UIs (TUI)** - Early days, buggy
- **Image inputs** - Eats context space
- **GUI Apps** - Not supported (yet)

<!-- reset_layout -->

---

```banner:epic +animate:matrix +once
STOP
DEMO
TIME
```

---

```bash +exec
./copresenter "Finally What's the key takeaway for developers to successfully building with AI coding agents ?"
```
---

```banner:epic +animate:rainbow +loop
THANK YOU
```

<!-- column_layout: [1, 1] -->
<!-- column: 0 -->
<!-- jump_to_middle -->

## Neeraj Garg

<!-- column: 1 -->

```ascii
     ┌─────────────┐
     │    ╔═══╗    │
     │    ║ ◉ ║    │
     │    ╚═══╝    │
     │             │
     │   ┌─────┐   │
     │   │ 010 │   │
     │   │ 101 │   │
     │   └─────┘   │
     │             │
     │  ┌───────┐  │
     │  │  AI   │  │
     │  └───────┘  │
     └─────────────┘
```

<!-- reset_layout -->

