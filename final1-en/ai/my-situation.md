# Project Situation Summary (quick context for a new session)

> The complexity of this project lies in **the people and liability**, not the engineering.
> This file provides a quick overview. Updated: 16/06/2026

---

## What Is This Project?

Building an outdoor calisthenics gym at the owner's home. Budget ~150k THB (current estimate ~89k). Users: one adult + one child ~5 years old. Designs and 3D models are in `models/final1-blender/`.

## The Four Parties

| Party | Who | Role |
|---|---|---|
| **A** | **Night (me)** — file owner | Research (~90% of data) · 3D modelling · requirement drafting · rough budget estimate · **does not decide final spec** · wants maximum self-protection |
| **B** | **Friend** | Same research/requirement role + coordination + proposes/selects final spec · wants to be seen as **"coordinator", not contractor** |
| **C** | **Owner ("Phi Khao")** | Homeowner + Professional Engineer (PE licence) + site inspector — one person, three roles · **will sign off on everything without doing detailed checks** · treats this as a "large toy" — if it breaks, no big deal · hires the contractor |
| **D** | **External Contractor** | Hired by Party C to build per approved design · no authority to change the design |

## Background

- Original plan: Party A and B only write requirements + quotation, then Party C hires a contractor and inspector.
- Plan changed: Party C **does not want to hire an additional engineer/inspector**, has no time to do calculations, said "if it breaks, it's fine, like a big toy."
- Party A **cannot accept this risk** (a child will use it), so stepped back to being **purely a researcher** — no decision-making authority.
- Party B wants the project to move forward and accepts more risk → a clear role-separation document became necessary.

## Documents Created to Manage This (`final1-en/`)

- **policy.liability.md** = Internal agreement between A ↔ B (signed by Party A and B only) → shields both from liability
- **policy.handoff.md** = Handover letter for Party C to sign (clean, concise, not confusing) → Party C acknowledges being the certifier and decision-maker
- **Two separate files are intentional** — to avoid confusing Party C with the internal agreement

## Agreed Document-Writing Rules (do not violate)

1. Use **"recommend/suggest"** not "must" — if written "the engineer must inspect before construction" and Party C doesn't actually inspect, the condition breaks immediately
2. All technical data provided = **"gathered from public sources · as-is · no warranty"** — Party C verifies it himself
3. ⛔ **Never put the word "AI" in the contract under any circumstances** — it is hard to interpret and Thai law is still unsettled (all instances have already been removed)
4. All policy files are **finalised** (owner chose not to involve a lawyer, accepts own risk · effective upon signing)

## Reality Check (paper cannot protect everything)

- Liability waivers can limit *civil liability between the parties* to some degree, but **cannot prevent criminal liability or third-party claims** (if a child is injured and the family sues)
- Protection works only when **actual conduct matches the roles on paper** (Party B must not act as contractor · contractor agreement must be in Party C's name)
- The one thing that genuinely prevents harm: **physically inspecting every weld and anchor before letting the child use the equipment**

## Current Status

- ✅ Policy documents complete (16/06/2026)
- ⏭️ Next: prepare **4-party quotation** (based on `archive/specs/quotation.full.md`)
