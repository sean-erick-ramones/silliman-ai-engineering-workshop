# Silliman AI Engineering Workshop

A one-day pair of sessions delivered to Silliman University CCS students: a morning lecture on how agentic engineering changed the speaker's professional practice, and an afternoon hands-on workshop where students build something with an agent themselves.

## Language

### Sessions

**Morning Lecture**:
The 9:00 AM to 12:00 NN lecture-and-discussion session, delivered from `morning-lecture.md`.
_Avoid_: Session 1, the talk, keynote

**Afternoon Workshop**:
The 2:00 PM to 4:00 PM hands-on lab session, delivered from `afternoon-workshop.md`.
_Avoid_: Session 2, the lab

**Block**:
A timed division of the Morning Lecture. There are four, numbered Block 1 through Block 4.
_Avoid_: Segment, section, part

**Act**:
A timed division of the Afternoon Workshop. There are three, corresponding to build, critique, and rebuild.
_Avoid_: Segment, block, phase

### Core teaching distinction

**Vibe-coding**:
Producing working software by describing the desired result to a model and accepting what comes back, without a written specification or a structured review of the output. Judged by whether it runs, not by whether it is correct.
_Avoid_: prompt engineering, AI coding, one-shotting

**Agentic Engineering**:
Directing an agent to build software through a structured process: written context in, a plan reviewed before execution, and human review of the output against the specification. The discipline the Morning Lecture argues is the actual hiring differentiator.
_Avoid_: AI-assisted development, AI pair programming, agentic coding

**Agent**:
A tool that plans across multiple steps, uses tools to act on a real environment, and self-corrects when a step fails. Distinguished from a chatbot (no tools, no persistence) and a copilot (suggests, does not act).
_Avoid_: AI, bot, assistant, LLM

### Workshop artifacts

**Mini-App**:
The single small visual web application students build during the Afternoon Workshop. Carried across all three Acts rather than restarted, so the critique in Act 2 lands on the student's own work.
_Avoid_: demo app, project, toy app

**Spec**:
The short markdown document written before any code, stating what the Mini-App must do. The student-facing counterpart to the speaker's professional ADR practice.
_Avoid_: PRD, requirements doc, brief

**Critical Review**:
Reading agent output against the Spec to find where it diverged: unrequested features, invented dependencies, requirements silently dropped. The named skill Act 2 exists to teach.
_Avoid_: code review, QA, checking the output

**Skill Repository**:
A durable collection of written, reusable agent workflows, kept so an agent performs a recurring task consistently rather than being re-explained each time.
_Avoid_: prompt library, playbook, templates
