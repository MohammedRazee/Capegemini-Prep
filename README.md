# Capgemini Exceller Prep — Presidency University MCA 2027

> One place for everything you need to clear the **Capgemini Exceller** drive, from the online assessment to the HR interview.
> Curated for MCA students of the School of Information Science, Presidency University. Updated as the process changes.

**Last updated:** October 2026 · **Status of links:** see [CHANGELOG](CHANGELOG.md)

---

## ⚠️ Read this first: the test has changed

Most Capgemini prep material online describes the **old** pattern (pseudocode + quant + 2 coding questions).
The **2026 Exceller** assessment is different. It has **five stages**, and several of them are **eliminatory**:

```
 Stage 1           Stage 2              Stage 3          Stage 4              Stage 5
 ENGLISH     →     TECHNICAL MODULE  →  DEBUGGING    →   AI-ASSISTED     →    COGNITIVE
 COMMUNICATION     AI Literacy + Tech   1 problem        CODING               Games + Logic
 (eliminatory)     ~45 min, 40 MCQs     ~20 min          Prompt an AI to      + Behavioural
                                        C / C++ / Java   solve a problem
                   └──────────── Stages 2–5 are taken in ONE sitting ────────────┘
```

Then: **Technical Interview → HR Interview**.

**What this means for you:**
1. **Balance beats brilliance.** A great score in one stage won't save a failed stage elsewhere.
2. **Half of the technical MCQs are about AI** (LLMs, prompting, RAG, agents, responsible AI). Almost nobody prepares for this, so it's easy marks for you.
3. **Debugging is in C, C++ or Java.** If you only know Python, start reading Java or C today.
4. **Stages 2–5 run back-to-back**, roughly 2.5 hours. Stamina and focus count.

---

## 🧭 How to use this repo (don't read everything)

| If you have... | Do this |
|---|---|
| **10 minutes** | Read this page + the [Night-Before Checklist](#-night-before-checklist) |
| **1 day** | Do every **🟢 Start here** item in the table below |
| **7 days** | Follow the [7-Day Sprint](#-7-day-sprint) |
| **More time** | Open each stage folder and work through **🔵 Go deeper** |

**Legend:** 🟢 Start here (essential) · 🔵 Go deeper (optional) · 💰 Paid · 🧪 Practice inside this repo

---

## 🟢 The "Start here" list: one per stage

| Round / Stage | What it tests | 🟢 Start here | Folder |
|---|---|---|---|
| **Round 0 — Profile** | Eligibility, resume, setup | [Jake's Resume template](https://www.overleaf.com/latex/templates/jakes-resume/syzfjbzwjncs) + [our checklist](round-0-profile/README.md) | [round-0-profile](round-0-profile/) |
| **Stage 1 — English** | Listening, speaking, reading, writing (AI-scored) | [Versant-style listening & speaking practice](https://test-prep-guides.com/versant-test-practice-online/listening-and-speaking/) | [stage-1-english](round-1-exceller-assessment/stage-1-english/) |
| **Stage 2 — AI Literacy** | GenAI, LLMs, prompting, RAG, agents, responsible AI | [Google: Introduction to Generative AI](https://www.cloudskillsboost.google/course_templates/536) + 🧪 [AI cheat sheet](round-1-exceller-assessment/stage-2-technical-module/ai-literacy.md) | [stage-2-technical-module](round-1-exceller-assessment/stage-2-technical-module/) |
| **Stage 2 — Technical** | Pseudocode, DSA basics, OOP, DBMS/SQL, REST, Git, cloud, networking, security | 🧪 [CS one-liners](round-1-exceller-assessment/stage-2-technical-module/technical-mcq.md) + [PrepInsta Capgemini](https://prepinsta.com/capgemini/) | same |
| **Stage 3 — Debugging** | Find and fix bugs in C/C++/Java | 🧪 [10 practice bugs with answers](round-1-exceller-assessment/stage-3-debugging/practice-bugs.md) | [stage-3-debugging](round-1-exceller-assessment/stage-3-debugging/) |
| **Stage 4 — AI-Assisted Coding** | How well you guide an AI to solve a problem | 🧪 [The 4-step prompt template](round-1-exceller-assessment/stage-4-ai-assisted-coding/README.md#the-4-step-prompt-template) | [stage-4-ai-assisted-coding](round-1-exceller-assessment/stage-4-ai-assisted-coding/) |
| **Stage 5 — Cognitive** | Motion & Grid games, logical reasoning, personality | [builduforward game simulators](https://www.builduforward.com/courses/cognizant-capgemini-games) | [stage-5-cognitive](round-1-exceller-assessment/stage-5-cognitive/) |
| **Round 2 — Technical Interview** | Projects, OOP, DBMS, DSA, live code | 🧪 [Top questions + project script](round-2-technical-interview/README.md) | [round-2-technical-interview](round-2-technical-interview/) |
| **Round 3 — HR Interview** | Communication, fit, Capgemini knowledge | 🧪 [HR answers + Capgemini facts](round-3-hr-interview/README.md) | [round-3-hr-interview](round-3-hr-interview/) |

---

## ⚡ 7-Day Sprint

About 2–3 hours a day. Each day mixes one "new" thing with practice on something you've already started.

| Day | Main focus (90 min) | Daily habit (30–45 min) |
|---|---|---|
| **1** | Read this README + [stage overview](round-1-exceller-assessment/README.md). Play **Motion + Grid** 3 rounds each. | Record a 60-second self-introduction on your phone. Listen back. |
| **2** | **AI literacy:** Google *Intro to Generative AI* + our [AI cheat sheet](round-1-exceller-assessment/stage-2-technical-module/ai-literacy.md). Do the 15 practice MCQs. | Versant drill: read a news paragraph aloud and repeat 10 sentences. |
| **3** | **Debugging:** solve bugs 1–5 in [practice-bugs.md](round-1-exceller-assessment/stage-3-debugging/practice-bugs.md) (10 min each, no peeking). | Motion + Grid, 2 rounds each. |
| **4** | **Technical MCQs:** [CS one-liners](round-1-exceller-assessment/stage-2-technical-module/technical-mcq.md) + 20 pseudocode questions on PrepInsta. | Versant drill + write a 200-word email in 15 min. |
| **5** | **AI-assisted coding:** solve 2 easy problems *only* by prompting an AI with the [4-step template](round-1-exceller-assessment/stage-4-ai-assisted-coding/README.md). Then debugging bugs 6–10. | Logical reasoning: 20 questions on IndiaBix. |
| **6** | **Interviews:** prepare your project story + "Tell me about yourself" + "Why Capgemini" ([Round 2](round-2-technical-interview/) & [Round 3](round-3-hr-interview/)). Mock with a friend. | Motion + Grid, timed. |
| **7** | **Full mock:** 45 min MCQs → 20 min debug → 1 AI-assisted problem → games. Review mistakes only. | Rest. Sleep 7+ hours. |

---

## 🌙 Night-Before Checklist

- [ ] Laptop charged, charger ready, **stable internet** (with a hotspot as backup)
- [ ] **Working headset with mic.** The English test scores your speaking by machine, and a bad mic costs you marks.
- [ ] Quiet room booked for the whole slot (Stages 2–5 take about 2.5 hours in one go)
- [ ] ID card, admit/login details, browser updated, notifications off
- [ ] Phone **away**. Any malpractice means disqualification.
- [ ] Re-read: [4-step prompt template](round-1-exceller-assessment/stage-4-ai-assisted-coding/README.md#the-4-step-prompt-template) · [Debugging routine](round-1-exceller-assessment/stage-3-debugging/README.md#the-4-step-routine) · [Game strategies](round-1-exceller-assessment/stage-5-cognitive/README.md)
- [ ] Sleep. Grid Challenge tests working memory, and a tired brain scores lower.

---

## 📁 Repo map

```
README.md                         ← you are here
round-0-profile/                  eligibility, resume, portal, test-day setup
round-1-exceller-assessment/
  ├─ stage-1-english/             listening, speaking, reading, writing
  ├─ stage-2-technical-module/    ai-literacy.md · technical-mcq.md · pseudocode.md
  ├─ stage-3-debugging/           routine + practice-bugs.md (10 bugs with answers)
  ├─ stage-4-ai-assisted-coding/  prompt template + worked example + review checklist
  └─ stage-5-cognitive/           Motion, Grid, logical reasoning, behavioural
round-2-technical-interview/      core CS, project script, top questions
round-3-hr-interview/             HR answers, Capgemini facts, questions to ask
experiences/                      interview experiences from seniors (add yours!)
CHANGELOG.md · CONTRIBUTING.md
```

---

## 🤝 Contribute

Cleared (or attempted) the drive? **Add your experience** to [`experiences/`](experiences/) using the [template](experiences/TEMPLATE.md). The next batch will thank you. See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## ⚖️ Disclaimer

This is an independent, student-focused study guide. It is **not affiliated with or endorsed by Capgemini**. The stage structure here comes from Capgemini's candidate briefing and publicly available prep guides. Exact question counts, timings and rules **vary from drive to drive**, so always follow the instructions from Capgemini and the Placement Cell on test day.
