# From Autocomplete to Agents

A whole-day industry lecture and workshop on agentic engineering, delivered to
Computer Science students at **Silliman University CCS**, ATA Hall.

Everything here is free to take, reuse, and reteach. See [License](#license).

| Session | Time | Deck |
|---|---|---|
| **Beyond Autocomplete, Beyond Vibe-Coding**<br>Software Engineering at the Tipping Point | 9:00 AM to 12:00 NN | [`morning-lecture.md`](morning-lecture.md) |
| **Hands-On: Directing an Agent to Build Something Real** | 2:00 PM to 4:00 PM | [`afternoon-workshop.md`](afternoon-workshop.md) |

## What this is about

Developer AI tools moved from autocomplete to agents that plan work across
multiple steps, use real tools, and correct their own mistakes.

The morning lecture traces that shift through real production engineering work:
writing a decision record before any code exists, diagnosing a slow client
dashboard, orienting fast in an unfamiliar codebase, and automating a recurring
reporting workflow. The argument is that the hiring differentiator is no longer
whether you know a particular framework, it is whether you can direct an agent
to build the right thing correctly.

The afternoon workshop makes that concrete. You build the same small app twice:

1. **Vibe-code it.** One prompt, one shot, accept whatever comes back.
2. **Review it critically.** Against what you actually asked for.
3. **Rebuild it from a written spec**, with an agent that has to show you a plan
   before it writes a single line.

Comparing those two versions is the whole point of the day.

## What's in here

| Path | What it is |
|---|---|
| `morning-lecture.md` | Morning lecture deck, speaker notes included |
| `afternoon-workshop.md` | Afternoon workshop deck, doubles as the live instructions |
| `docs/adr/` | Architecture decision records for the workshop itself |
| `CONTEXT.md` | Terminology used across both decks |
| `scratch/` | Side experiments, not part of either session |

The `docs/adr/` folder is worth a look. Those are real decision records
explaining why the workshop is structured the way it is, written before it was
built. That is the same practice the morning lecture argues for, applied to the
workshop itself.

## Read the slides

The decks are plain Markdown. You can read them straight on GitHub, no setup.

To run them properly, with animations, diagrams, and presenter notes:

```bash
npm install
npm run dev:morning     # or: npm run dev:afternoon
```

Other useful commands:

```bash
npm run build:morning    # static site into dist/morning
npm run export:morning   # PDF export
```

Built with [Slidev](https://sli.dev). If you are editing the decks with an
agent, install the Slidev skill first so it knows the syntax:

```bash
npx skills add slidevjs/slidev
```

## Workshop setup

Everything used in the workshop is free. Nothing to pay for, no license to buy.

- A laptop, charged
- A **personal** GitHub account, not a school SSO login
- A [bolt.new](https://bolt.new) account, for Act 1.
  Fallback if it is slow: [AI Studio Build mode](https://aistudio.google.com/apps)
- [VS Code](https://code.visualstudio.com) with the **GitHub Copilot** extension
  installed and signed in, for Act 3. GitHub Copilot Free is enough.

Troubleshooting:

| Problem | Try this |
|---|---|
| bolt.new is slow or erroring | Go to [aistudio.google.com/apps](https://aistudio.google.com/apps), sign in with any Google account. Build and preview only, do not click Publish |
| VS Code shows no Copilot icon | Extensions panel, search "GitHub Copilot", install, sign in |
| GitHub sign-in keeps looping | Use a personal GitHub account, not school SSO |

## Where to go next

- **[roadmap.sh](https://roadmap.sh)** — developer roadmaps. Start here when you
  are not sure what to learn next.
- **[freeCodeCamp](https://www.freecodecamp.org)** — free, project-based courses.
  Where you build the fundamentals an agent cannot fake for you.
- **[Claude Code docs](https://docs.claude.com)** — the agent behind the morning
  talk, documented properly.

The tools change every few months. The fundamentals under them do not.

## License

[Creative Commons Attribution 4.0 International](LICENSE) (CC BY 4.0).

Use it, remix it, teach it, including commercially. Just credit the original:

> "From Autocomplete to Agents" by Sean Erick C. Ramones,
> licensed under CC BY 4.0. https://www.seancramones.com

The vendored Slidev skill under `.agents/skills/` is intentionally not committed
here, since it belongs to the Slidev project rather than to this material.

## About

**Sean Erick C. Ramones** — Full-Stack Software Engineer at Miller Development AB,
Silliman University CCS alumnus (BSIT, 2018).

[seancramones.com](https://www.seancramones.com) ·
[GitHub](https://github.com/sean-erick-ramones) ·
[LinkedIn](https://www.linkedin.com/in/sean-erick-ramones-102a64192)

Client work referenced in the morning lecture is anonymized throughout.
