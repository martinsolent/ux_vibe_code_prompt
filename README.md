# VibeProto: Vibe-Coding Prompt Studio and Audio Guide

VibeProto teaches UX students to build clickable prototypes with [Claude](https://claude.ai) without writing code. You describe the prototype in plain English. Claude builds it on top of a real open-source design system. You judge the result and steer it with small, precise changes.

The skill you practise is **specifying and steering**, not programming. Claude writes the HTML, and you make the UX decisions.

**Live site:** <https://martinsolent.github.io/ux_vibe_code_prompt/>

---

## What's in this repo

| File | What it is |
| --- | --- |
| [`index.html`](index.html) | **Guided audio walkthrough.** A narrator takes you through the whole workflow one step at a time. It shows the diagram for each step and pauses when it's your turn to act. |
| [`vibe-coding-prompt-studio.html`](vibe-coding-prompt-studio.html) | **Prompt Studio.** The workspace where you choose a design system, plan your prototype, build your prompt and copy follow-up prompts. |

Both are single, self-contained HTML files, with no build step, server or install. Each page links to the other: **🎧 Audio guide** in the Studio and **✏️ Prompt Studio** in the guide. The link opens in a new tab with the same level and plan already selected, passed as `?level=1|2&plan=free|pro`.

The intended way to use them is side by side. Listen to the guide in one tab and do each step in the Studio in the other.

---

## Choose your level and plan

Both pages have the same switches at the top. Changing them changes the narration, diagrams, checklists and prompts to match.

### Levels

| | Level 1: the recipe | Level 2: the studio |
| --- | --- | --- |
| **For** | Your first prototype | Any app, feature, tool or situation you can imagine |
| **Starting point** | A guided prompt builder with worked examples | A blank 12-part scenario canvas, in your own words |
| **Prompting** | One clear recipe, plus a library of follow-up prompts | Edit the prompt freely, add reusable patterns, check it against a quality gate |
| **Scope** | Set by the recipe | Set by you, and you should be able to explain every decision |

Both levels share the same rules: **one self-contained HTML file, and fake data only.**

### Claude plans

| | Free | Pro |
| --- | --- | --- |
| **Artifacts** (live preview) and publishing a share link | ✅ | ✅ |
| **Usage** | A budget that refills over a rolling window of a few hours | At least 5× the free plan's usage per rolling 5-hour session, plus a weekly cap |
| **Projects** | No | Yes. A Project keeps your rules and files, so every chat in it starts already briefed |
| **Advice in the guide** | Make every message count: plan first, keep builds small, start fresh chats | Use Projects, one chat per version or job, and spend the extra room on comparing variants |

Anthropic doesn't publish exact message counts, so both editions say to plan your prompts carefully.

---

## The Level 1 workflow

There are five stages: **Pick → Plan → Prompt → Fix → Finish.** The audio guide narrates them as seven steps:

1. **Get set up.** Sign in at claude.ai, check that Artifacts is switched on in Settings, and create a folder for your versions (v1, v2, v3…). On Pro, also create a Project.
2. **Choose a design system.** Start from your task, not from what looks nicest (see [Design systems](#design-systems)).
3. **Plan before you build.** Narrow down from a realistic scenario, to one main task with a clear end point, to only the screens that task needs.
4. **Use the prompt builder.** Enter your idea, users, main task, screens and example content, then choose the device and fidelity. Three example buttons (📅 room booking app, 🪴 plant-care tracker, 📊 café sales dashboard) fill in the form so you can see a finished prompt. The generated prompt has six parts:
   - **Format:** one HTML file with inline CSS and JavaScript, and no server
   - **Design system:** real components
   - **The prototype:** users, main task, screens and fake content
   - **Requirements:** the task must work, and the prototype must be accessible and suit the device
   - **Before you build:** a plan first
   - **After you build:** a plain-English walk-through
5. **Build version 1.** Paste the prompt, check Claude's plan, then reply `go`. Click through the task, note every problem, and download the file as v1 *before* asking for any changes.
6. **Fix in small, precise steps.** Describe the symptom rather than guessing the fix. Change one thing at a time, and say what must *not* change. After every change, click through the whole task again. Save the result as v2.
7. **Finish and share.** Run the accessibility pass, check the prototype yourself using only the keyboard, run the final check, download it, publish a share link, and keep a plain-English description with the file.

## The Level 2 workflow

This is the studio loop: **Define → Craft → Gate → Build → Refine**, then go round again.

- **Scenario canvas.** Twelve parts in three groups. Each part has a coaching question, examples you can reveal, and live feedback: green means clear, blue is a tip and orange is a warning.
  - **A · The idea and the people:** idea, users, situation, problem
  - **B · The task:** main task, success statements (Given / When / Then), screens
  - **C · How it behaves:** features, states and edge cases, constraints and accessibility, what to fake, what's out of scope
- **Let Claude interview you.** If you're stuck, copy the interview prompt into a new chat with your rough idea. Claude asks about 8–10 questions, one at a time, then writes a summary. Paste the summary back and press **Fill canvas**.
- **Build settings.** Choose the device (mobile, desktop, responsive, kiosk or tablet) and fidelity, plus two options: a hidden **Shift+S** state switcher, and asking Claude to question you and plan before building.
- **Project kit (Pro).** Copy the Project instructions and download `scenario.md` for the Project's knowledge. Use one chat per job: interview, build v1, variants, fixes.
- **Workspace and quality gate.** Assemble the prompt from your canvas, then edit it freely or write your own. The gate scores it out of 10 for: users, a clear task, output format, a design system, states, fake content, accessibility, a scope fence, the device, and a check before building. Aim for 8/10 on build prompts. The gate gives advice and never blocks you.
- **Prompt patterns.** Ten reusable prompt shapes (listed [below](#prompt-library-and-patterns)).
- **Fake it honestly.** How to simulate the parts a single HTML file can't really do.
- **Troubleshooting.** Fixes for the most common problems.

---

## Design systems

The Studio offers these, each with a live preview and a **Select** button that writes your choice into the prompt:

| Design system | Licence | Good for |
| --- | --- | --- |
| Pico CSS | MIT | First prototypes, simple forms, content pages |
| Bulma | MIT | Clean marketing pages, simple apps, card layouts |
| Bootstrap 5 | MIT | Dashboards, tables, lots of components |
| IBM Carbon | Apache-2.0 | Dashboards and data-heavy, component-rich apps |
| GOV.UK Design System | MIT (code) | Form-heavy or step-by-step services |
| NHS.UK Design System | MIT (code) | Health and care services |
| U.S. Web Design System | Public domain | Form-heavy or step-by-step services |
| Shoelace | MIT | A modern, app-like feel |
| Material Web | Apache-2.0 | Mobile-app-style prototypes |
| Tailwind CSS | MIT | Custom-looking apps (ask Claude for one accent colour and consistent spacing) |
| No design system | — | Always loads, even when other files are blocked |

To choose quickly, work down this list and take the first yes:

1. Is it a health or care service? Use **NHS.UK**.
2. Is it form-heavy or a step-by-step service? Use **GOV.UK** or **USWDS**.
3. Does it have dashboards, tables or lots of components? Use **Bootstrap** or **Carbon**.
4. Is it your first prototype, and you want the fewest problems? Use **Pico** or **Bulma**.
5. Do you want a modern, app-like feel? Use **Shoelace** or **Material**.

> **Note:** the government and NHS code is free to use, but their logos, crown and fonts are not. The generated prompts tell Claude to use a generic header.

---

## Prompt library and patterns

**Level 1 prompt library.** Follow-up prompts for after the first build. Your design system is filled in automatically, and you replace the `[square brackets]` with your own details.

- **Change one thing** (small edits)
- **It's broken** (something doesn't work)
- **Stay on-system** (parts don't match the design system)
- **Accessibility pass** (a WCAG 2.2 AA review and fix)
- **Final check** (the task works end to end, with no placeholders)
- **Explain it to me** (a plain-English description, under 150 words)
- **Handover to a new chat**
- **Update the Project** (Pro)

**Level 2 prompt patterns:**

1. **Ask before building.** Claude asks its questions first, so a wrong guess costs one message instead of a rebuild.
2. **User story → acceptance criteria.** Claude builds only what's needed to meet the criteria.
3. **Constraints first.** Limits go at the top so they shape the design.
4. **Three variants.** Three genuinely different designs of one screen, behind tabs A / B / C.
5. **State switcher.** A hidden Shift+S panel to preview empty, loading, error and other states.
6. **Self-critique, then fix.** A review against Nielsen's heuristics and WCAG 2.2 AA. You still check every fix yourself.
7. **Scope fence.** Say exactly what to change and what must stay the same.
8. **Simulate a persona.** Claude narrates where a particular user would hesitate.
9. **Reverse prompt.** Claude writes the single prompt that would have produced the prototype.
10. **Explain like I'm the client.** A non-technical summary in under 120 words.

---

## Ground rules

- **Fake data only.** Never paste real personal data, names or private information into Claude.
- **No real credentials.** A prototype must never collect real passwords, card numbers or personal details. Label fake sign-in and payment screens *"Prototype — don't enter real details"*.
- **Build only what the main task needs.** A prototype is a sketch you can click, not a finished product.
- **Download every working version** before asking for changes.
- **Never take "fixed" on trust.** Check every fix yourself with the keyboard, 200% zoom and a contrast checker.
- **Check your module's AI-use policy.**

---

## Features of the pages

- **Narration.** The guide uses the browser's built-in read-aloud voice (the Web Speech API). It pauses automatically at each "Pause here", the space bar plays and pauses, and diagrams are highlighted as the narrator reaches them. If your browser has no voice, **Copy this script** copies the narration as plain text for another reader.
- **Diagrams view.** All the diagrams for the current level and plan in one place, without narration. Each has a **Download SVG** button for use in slides, and exports keep the current light or dark theme.
- **Dictation.** In the Studio, a 🎤 button on form fields lets you speak instead of type. Say "new line", "comma" or "full stop" for punctuation. Your browser may send the audio to its speech service, so don't dictate personal details.
- **Saved progress.** Your answers, level, plan and view are saved in your browser's `localStorage`, so they're still there when you come back. Nothing is sent to a server. **↺ Reset** clears the Studio.
- **Light and dark themes** with the ◐ button, a skip link, and keyboard-accessible controls.

### External resources

The pages load web fonts (DM Sans and JetBrains Mono) from Google Fonts. The Studio's design-system previews load the design systems' stylesheets from public CDNs, so the previews need an internet connection. Everything else works offline.

---

## Running locally

Clone the repo and open either HTML file in a modern browser. Chrome, Edge and Safari have the best support for speech and dictation.

```bash
git clone https://github.com/martinsolent/ux_vibe_code_prompt.git
cd ux_vibe_code_prompt
open index.html   # macOS; or double-click the file
```

Keep both files in the same folder so the links between them work.

## Deployment

The site is served by GitHub Pages from the `main` branch. After you push, Pages can take a minute or two to update, and browsers may keep the old version for up to 10 minutes. Press **Cmd+Shift+R** (or **Ctrl+Shift+R**) to force a fresh load.

---

## Troubleshooting

| Problem | What to do |
| --- | --- |
| The preview looks plain or unstyled | Claude's preview can block some external files. Download the HTML and open it in Chrome or Edge, or ask Claude to load the design system from cdnjs.cloudflare.com. |
| Claude rebuilt everything for one small change | Say what must *not* change: *"Change only… Keep everything else exactly as it is."* If it still changes other things, go back to your last download. |
| A button does nothing | Describe the symptom: what you clicked, what you expected and what happened. Ask Claude to fix only that. |
| The response stopped halfway | Reply *"Continue from exactly where you stopped."* For big prototypes, build one flow at a time. |
| You've hit your usage limit | Download what you have, click through it and plan your next prompts. Then start a fresh chat with the latest HTML attached and a short summary. |
| It doesn't look like the design system | Use the **Stay on-system** prompt, then compare against the design system's own component pages. |

---

## Credits and licences

The design systems are their owners' work and are used under their own open-source licences. Government and NHS logos, crowns and typefaces are not covered by those licences and must not be used.
