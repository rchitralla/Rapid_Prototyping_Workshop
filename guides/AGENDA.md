# Workshop Agenda — Rapid Prototyping for Data Projects

**Duration:** 2 hours
**Format:** Hands-on, small groups (2-4 people)
**Language:** English (groups may collaborate in French)

---

## Phase 1: Intro + Setup (10 min)

**0:00–0:05 — Welcome & Intro**
- What we're building today
- What rapid prototyping is (and isn't)
- Introduce the two tools: Streamlit (Python data apps) and Lovable (AI-powered no-code)

**0:05–0:10 — Form Groups & Pick a Brief**
- Groups of 2-4 people
- Mix of skill levels is ideal
- Each group picks one of the three Strasbourg-themed briefs
- Confirm everyone has: GitHub, LLM access, Lovable account, Streamlit account

---

## Phase 2: Ideation (25 min)

**0:10–0:20 — Define Your Prototype**
- Read through the project brief
- Discuss as a group: What's the core feature?
- Use the AI Workflow (`resources/AI_WORKFLOW.md`) to brainstorm with your LLM
- Sketch a rough wireframe (paper, Excalidraw, or whiteboard)

**0:20–0:35 — Wireframe Your Prototype**
- Each group shares their plan in 30 seconds
- Facilitator helps scope down if too ambitious
- Rule of thumb: 3 features max for the build sprint

---

## Phase 3: Build Sprint (65 min)

**0:35–1:40 — Hands-on Building**

Groups work at their own pace. Suggested approach:

**If using Streamlit:**
1. Open `examples/streamlit/app.py`
2. Load your dataset
3. Add filters (sidebar)
4. Add a chart (Plotly)
5. Add a metrics row
6. Use your LLM to generate code for anything you're stuck on

**If using Lovable:**
1. Open Lovable and create a new project
2. Write your initial prompt (see `examples/lovable/README.md` for examples)
3. Iterate with follow-up prompts
4. Add your real data
5. Customize the design

**If using both:**
1. Start with Lovable for the visual concept (10 min)
2. Switch to Streamlit for the functional prototype (35 min)
3. Use the Lovable design as a reference for layout

**Facilitator notes:**
- Walk around and check on groups every 5-10 min
- Common blockers: data loading, chart formatting, filter logic
- Remind groups to use their LLM when stuck — that's the point
- Encourage groups to commit their code to a branch

---

## Phase 4: Group Demos (20 min)

**1:40–2:00 — Show What You Built**
- Each group gets 2-3 minutes
- Show: what you built, what tools you used, one thing you learned
- Audience feedback: one thing that works well, one suggestion

---

## Wrap-Up Checklist

After the workshop, participants should have:

- [ ] A working prototype (Streamlit app and/or Lovable project)
- [ ] Code committed to their GitHub repo
- [ ] A repeatable workflow for AI-assisted prototyping
- [ ] Links to all resources for continued learning

---

## Facilitator Tips

- **Don't lecture.** Keep intros under 5 minutes. The learning happens by building.
- **Scope aggressively.** If a group has 5 ideas, help them pick 1 and finish it.
- **Normalize AI use.** Remind people the goal is to build fast, not to memorize APIs.
- **Time-box.** Announce time remaining at 30 min, 15 min, and 5 min before each phase ends.
- **Celebrate progress.** A working filter + one chart is a great outcome for 2 hours.
