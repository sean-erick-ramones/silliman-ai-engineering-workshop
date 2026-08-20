---
theme: seriph
title: Directing an Agent to Build Something Real
info: |
  Hands-On: Directing an Agent to Build Something Real

  Sean Ramones — Silliman University CCS alumnus, Miller Development AB
class: text-center
highlighter: shiki
drawings:
  persist: false
transition: slide-left
mdc: true
fonts:
  sans: 'Inter'
  mono: 'Fira Code'
---

# Hands-On

## Directing an Agent to Build Something Real

2:00 PM – 4:00 PM

<!--
This deck is a working reference, not a lecture. Keep it visible on the projector throughout — students glance up at checkpoints and prompts while they're heads-down typing.
-->

---

# Today's tools

<div class="grid grid-cols-3 gap-6 mt-6">
<div>

### Act 1 — vibe-code

**bolt.new**
free, no card, instant preview

Backup if it's slow: **AI Studio Build mode**
<span class="text-sm opacity-60">aistudio.google.com/apps</span>

</div>
<div>

### Act 2 — critical review

No new tool.
Just your eyes, and the checklist on the next slide.

</div>
<div>

### Act 3 — build with a spec

**VS Code + GitHub Copilot Free**
agent mode, signed in with GitHub

</div>
</div>

<!--
The AI Studio fallback is Build mode, reached directly at aistudio.google.com/apps. There is no obvious "Build" tab to hunt for in the nav, so give students the URL rather than a click path. Any Google account works, and the Gemini API key is provisioned automatically. One trap: do not let students click Publish or Deploy. Building and previewing in the browser is free, but publishing asks for Google Cloud billing, and anyone with a prior Cloud billing account is ineligible for the free starter tier. Act 1 only needs a running preview, never a deploy.

Two different tools for two different acts, on purpose — call this out directly rather than let it look like an accident. Act 2 deliberately has no tool of its own: it's the pause between building and rebuilding, and naming it here (even with nothing to install) keeps the room from thinking it got skipped. The morning talk used Claude Code; today uses free tools so everyone in the room can follow along with zero payment wall.
-->

---

# Setup checklist (10 min)

<div class="mt-6">

- [ ] Laptop charged, on ATA Hall wifi
- [ ] VS Code installed, GitHub Copilot extension installed and signed in
- [ ] bolt.new account created (from the pre-workshop email)
- [ ] Open bolt.new now — don't wait for Act 1 to start signing up

</div>

<div v-click class="mt-8 text-lg opacity-75">

Didn't get the pre-workshop email or something's missing? Raise your hand now.

</div>

<!--
This assumes the install email already went out. If someone missed it entirely, this is the moment to catch them, not five minutes into Act 1. Don't spend more than a couple minutes troubleshooting any one laptop here — flag them for roaming support during Act 1 instead.
-->

---

# If something breaks

| Problem | Try this |
|---|---|
| Wifi won't connect | Ask a neighbor to hotspot, or flag Sean |
| bolt.new slow or erroring | Go to **aistudio.google.com/apps**, sign in with any Google account |
| VS Code has no Copilot icon | Extensions panel → search "GitHub Copilot" → install → sign in |
| GitHub sign-in loop | Use a personal GitHub account, not a school SSO login |

<!--
Keep this slide up during Setup and revisit it verbally if Act 1 stalls for the room. The bolt.new-to-AI-Studio switch should be a one-line instruction, not an improvised recovery — that's the whole reason this fallback is rehearsed in advance rather than invented on the day.
-->

---
layout: section
---

# Act 1

## Vibe-code it

<!-- ~20 min, 2:10–2:30 -->

---

# Today's app: the CCS Event Board

A single page. No backend, no login.

<v-clicks>

- Lists upcoming campus org events
- A form to add a new event
- Filter the list by organization
- Saves to the browser, so it's still there on reload

</v-clicks>

<!--
This is the one requirement that carries through all three acts. Don't over-specify it here — the whole point of Act 1 is that students hand this over loosely and see what an agent decides to build without more guidance than that.
-->

---

# The one-shot prompt

Paste this into bolt.new (or aistudio.google.com/apps) and see what comes back:

```text
Build a single-page web app called "CCS Event Board".
It should list upcoming campus org events, let me add a
new event with a title, org name, and date, let me filter
the list by org, and save everything in the browser so it
persists on reload. Make it look clean and simple.
```

<div v-click class="mt-6 text-lg opacity-75">

One prompt. One shot. Don't fix anything yet — that's Act 2.

</div>

<!--
Resist the urge to let students iterate here. The value of Act 1 is a raw, un-reviewed output to critique next. If someone's output is broken, that's fine — broken is also a valid thing to critique in Act 2.
-->

---
layout: center
class: text-center
---

# Checkpoint: 2:30 PM

Everyone should have something running in the browser, even if it's rough

<!--
Live checkpoint marker. If a chunk of the room is stuck on tooling rather than on the prompt itself, this is where you make the fallback-platform call for the whole room at once rather than letting individuals silently struggle.
-->

---
layout: section
---

# Act 2

## Critical review

<!-- ~15 min, 2:30–2:45 -->

---

# What critical review actually looks like

<v-clicks>

- Does it match what you asked for — nothing more, nothing less?
- Did it invent a dependency or library you didn't ask for?
- Did it quietly drop something? (Did the filter actually filter?)
- Does it survive a page reload? Does the data actually persist?

</v-clicks>

<!--
This is the skill the whole day is building toward. Have students run through this checklist against their own Act 1 output, out loud with a neighbor if time allows. The goal isn't to shame vibe-coding — it's to make the gaps visible before Act 3 shows the alternative.
-->

---
layout: center
class: text-center
---

# Pair up

Trade laptops with your neighbor for five minutes.
Run their app through the checklist. What would you have asked for differently?

<!--
Pairing here is optional depending on room size and time, but strongly recommended — critiquing someone else's output is easier than critiquing your own, and it's good practice for reviewing an agent's work on a team.
-->

---
layout: section
---

# Act 3

## Rebuild it, with a spec

<!-- ~45 min, 2:45–3:30 -->

---

# Step 1 — write the spec first

Same app. This time, write down what it needs to do before you touch the agent.

```md
# CCS Event Board — Spec

- List events: title, org, date
- Add event form: title, org, date, all required
- Filter dropdown by org
- Persist to localStorage, reload-safe
- No backend, no login
```

<div v-click class="mt-4 text-lg opacity-75">

This is the same practice from this morning's ADR slide — context in, before code.

</div>

<!--
Keep this genuinely short. The point isn't a heavyweight document, it's the discipline of writing the requirement down before asking the agent to act on it.
-->

---

# Step 2 — ask the agent to plan first

In VS Code, open Copilot's agent mode and try:

```text
Here's my spec: [paste spec]. Before writing any code,
tell me your plan: what files you'll create, and how
you'll implement each requirement. Wait for me to
confirm before you start.
```

<div v-click class="mt-6 text-lg opacity-75">

Read the plan. Does it cover every line of your spec? Say "go" only once it does.

</div>

<!--
This is the plan-before-execute habit from the morning talk's BigQuery case study. Reviewing a plan is cheap; reviewing finished code for the same gaps is expensive. Make students actually read the plan, not just skim and approve.
-->

---

# Step 3 — review the output, critically

Same checklist as Act 2, now against your own written spec:

<v-clicks>

- Does it match the spec, line for line?
- Did it hallucinate a dependency?
- Is it doing something you didn't ask for?

</v-clicks>

<div v-click class="mt-6 text-lg opacity-75">

Compare this app to your Act 1 app. Same requirement, two processes. What changed?

</div>

<!--
This comparison is the entire thesis of the day, made concrete. Give students a moment to actually notice the difference rather than rushing to the extension challenge.
-->

---
layout: center
class: text-center
---

# Checkpoint: 3:30 PM

Everyone should have a spec-built version of the Event Board running

<!-- Live checkpoint marker. -->

---
layout: section
---

# Extension Challenge

<!-- ~20 min, 3:30–3:50 -->

---

# Add one feature

Pick one, agent-assisted, solo or with a partner:

<v-clicks>

- Search events by title
- Sort by date
- Dark mode toggle

</v-clicks>

<div v-click class="mt-6 text-lg opacity-75">

Write the one-line spec addition first. Then prompt. Then review.

</div>

<!--
Keep the extension genuinely small — the point is repeating the spec-plan-review loop once more on their own, not building something new. Reinforce: even a one-line addition deserves a one-line written spec.
-->

---
layout: center
class: text-center
---

# Stuck? Wave a hand

I'll be walking around the room

<!--
Roaming support reminder. Say this explicitly rather than assuming students will ask — a lot of a first-agentic-tool session is quiet confusion, not loud questions.
-->

---
layout: section
---

# Wrap-Up

<!-- ~10 min, 3:50–4:00 -->

---

# Keep this going: a skill repository

<v-clicks>

- Write down a workflow once you've done it well twice
- A saved, repeatable process an agent can follow the same way every time
- Not a prompt you retype — a document the agent reads before it starts

</v-clicks>

<div v-click class="mt-6 text-lg opacity-75">

This is exactly what powered the monthly report workflow from this morning's talk.

</div>

<!--
Tie back generically to the real skill-repository pattern from Block 3 without naming any internal tool or page. The point for students: today's spec is a one-off; a skill is what you get when you save that spec pattern for reuse.
-->

---

# Keep learning

<v-clicks>

- **roadmap.sh** <span class="opacity-60">: developer roadmaps. Start here when you are not sure what to learn next.</span>
- **freeCodeCamp.org** <span class="opacity-60">: free, project-based courses. Where you build the fundamentals an agent cannot fake for you.</span>
- **Claude Code docs, docs.claude.com** <span class="opacity-60">: the agent behind this morning's talk, documented properly.</span>

</v-clicks>

<div v-click class="mt-8 text-lg opacity-75">

The tools change every few months. The fundamentals under them do not.

</div>

<!--
Three links doing three different jobs: roadmap.sh answers "what do I learn next", freeCodeCamp answers "where do I actually practice", and the Claude Code docs answer "how do I go deeper on today's topic". Say the closing line out loud instead of letting it sit on the slide. It is the honest answer to the anxiety in the room: agents did not make learning to code pointless, they moved where the leverage is.
-->

---
layout: end
---

# Thank you

seancramones.com

<!--
Contact slide. Pull current contact details from your own site before publishing the hosted version.
-->
