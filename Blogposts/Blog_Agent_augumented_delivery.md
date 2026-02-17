## Agent augumented software delivery methods
Outline and list alternative ai augumented delivery methods/practices <br>

(not covered Openspec, Kiro,  )

## Ralph Wiggum

Description<br>

A bash looping method, which runs the same prompt every time. It prioritizes vertical completeness before picking up the next feature. A context window serves one given goal in the plan.md. 

Strengths
- Open source
- Iterative loops
- Great leveraged of context window
- Light and simple

Weeknesses
- Some context content can be lost in compaction
- Many Ralph versions

Example
- https://github.com/frankbria/ralph-claude-code<br>
- https://github.com/michaelshimeles/ralphy<br>

## Spec driven development "kit" (SDD) Specify
Description

"Spec-Driven Development flips the script on traditional software development. For decades, code has been king — specifications were just scaffolding we built and discarded once the "real work" of coding began. Spec-Driven Development changes this: specifications become executable, directly generating working implementations rather than just guiding them." <br>

Process
- /Specify (Specify the feature you want to build)
- /Plan (Plan how to implement the specified feature)
- /Task (Break down the plan into executable tasks)

Strengths
- Open source
- Project produces accurate documentation
- Present documentation leveraged
- Similar practices to Test driven development (TDD)

Weeknesses
- Demands early, rigid documentation
- Can be rigid or stiff
- Possibly weaker on UX design

Weight of methodology
- Lighter than BMAD, similar in process, and being in IDE. 

Additional information <br>
https://github.com/github/spec-kit/blob/main/spec-driven.md

## OpenSpec by Fission-AI

Description
- Lighweight spec driven development "kit". 


- /openspec-apply (implement an approved OpenSpec chnage and keep tasks in sync)
- /openspec-archive (Archive a deployed OpenSpec change and update specs)
- /openspec-proposal (scaffold a new OpenSpec change and validate strictly
- /

Run by: openspec init

Strengths
- Open source
- Lightweight

Weeknesses

Additional content


## Spec-coding-MCP (KevinLin)
Description
- Spec driven development workflow which can be used in any IDE
- Preferrably used by Claude Code
- The spec-coding.md skill implements a comprehensive 5-stage workflow for feature development:
    1. Goal Confirmation - Clarify and confirm feature goals
    2. Requirements Gathering - Create EARS-format requirements
    3. Design Documentation - Develop technical design
    4. Task Planning - Generate implementation checklist
    5. Task Execution - Execute tasks incrementally
Strengths
- Open source
- Lightweight
- Trusted source of code ;)

Weeknesses

Additional content
https://github.com/kevinlin/spec-coding-mcp

## Vibe-Kanban
Description
- Multi agent kanban platform. 

Strengths
- Open source

Weeknesses

Additional content

- https://github.com/BloopAI/vibe-kanban


## BMAD-Method
Description
The BMAD method is more like a set of predefined agents as in a team

2 Paths
- Simple path for quick fixes
- Full planning path (BMad method)

- /product-brief — define problem, users, and MVP scope<br>
- /create-prd — full requirements with personas, metrics, and risks<br>
- /create-architecture — technical decisions and system design<br>
- /create-epics-and-stories — break work into prioritized stories<br>
- /sprint-planning — initialize sprint tracking<br>
- Repeat per story: /create-story → /dev-story → /code-review<br>


Strengths
- Open source
- Iterative process for creating clarity in
- Extensive planning phase
- Versioned releases of methodology

Weaknesses
- Token heavy by default
- 
Additional information<br>
- https://github.com/bmad-code-org/BMAD-METHOD
<br>
<br>
<br>

---
## Recognized patterns in the methods
- *Careful planning*- The importance of planning and even iterating on plans before execution is clear in agentic software development
(Supported by study by Anthropic on Plan mode increasing agent output quality)
- *The quality of the requirements*- determine to a higher degree the quality of the outcome than old school agile software delivery.
- *Be specific* - Being specific when defining requirements, wishes, changes etc. is more important when the human-to-human understanding and intuition is gone. The machine only knows what you express in clear text.
- *Leverage loops* - Working in repetitive cycles, iterations, 
- *Carefully defined skills*
- *Carefully defined guardrails*
- *Carefully defined context layer*
- *Multi agentic development*

## Trends recognized in the Agentic software delivery market
- Context windows are growing rapidly.
- Token monsters are appearing (i.e. Opus 4.6)
- The users judgement is the great asset which Agents dont have
- .md "Agent" rules are standard, not emerging.
- Limitation seemingly rather on providing enough accurate input than processing requests correctly

## Finnish provokers
- What fuels "good judgement" in users?
- How can an organization opimize for "good judgement"
- What is "good judgement"-> Exposure of great content, what is useful, what is tasteful, what is valuable
- 
## Kris Predictions
- More work upfront than in agile software delivery, due to the deterministic nature of an agent / limited intunition
- Feature based development is to stay, cutting scope continues to be an important part of software delivery