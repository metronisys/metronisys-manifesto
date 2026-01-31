# Metronisys™ Decision Boundaries – Use Cases  
## Operationalizing Attention, Energy, and Identity Guards

> **Metronisys™** is a trademark of Tony Nudd.  
> These use cases illustrate how agents can infer user states and enforce boundaries to remain aligned with human wellbeing, identity, and productivity principles.  

---

## 1️⃣ Attention / Focus Guard

**Goal:** Detect if the user is in deep focus and avoid unnecessary interruptions.

**Signals / Data Sources:**
- Active window / application usage  
- Keyboard/mouse input patterns  
- Calendar context (scheduled deep work blocks)  
- Optional self-reported focus (“On a scale of 1–5, how focused are you?”)

**AI Approach:**
- Model recent activity patterns to classify focus state (deep / medium / shallow)  
- Simple heuristics: e.g., 45+ minutes uninterrupted work → deep focus  
- Optionally, ML models can predict attention trends

**Decision Logic:**
- If focus state = deep → block non-critical notifications or task assignments  
- Optionally allow urgent override for high-priority tasks

---

## 2️⃣ Energy / Fatigue Guard

**Goal:** Detect low energy and recommend pacing or rest.

**Signals / Data Sources:**
- Behavioral signals: typing speed, error rate, reaction times  
- Physiological signals (optional): heart rate, HRV, sleep data, posture, eye tracking  
- Self-reported energy levels  
- Task history: duration of continuous work without breaks

**AI Approach:**
- Combine workload, physiology, and self-reports into an **energy index**  
- Rule-based: e.g., >2 hours continuous work without break → low energy  
- ML-based: model energy patterns over time

**Decision Logic:**
- If energy index < threshold → agent proposes:  
  - Short breaks or reduced workload  
  - Task reprioritization  
- Optional: recommend rest support tasks

---

## 3️⃣ Identity Alignment Guard

**Goal:** Detect conflicts between proposed goals/tasks and the user’s core values.

**Signals / Data Sources:**
- User-defined core values (structured YAML/JSON profile)  
- Task/goal metadata, including tagged values  
- Historical decisions for similar tasks

**AI Approach:**
- Rule-based: if task values ∩ user core values = ∅ → conflict  
- NLP semantic matching for subtle value conflicts

**Decision Logic:**
- If conflict detected → agent:  
  - Prompts user for explicit reassessment  
  - Suggests alternative tasks aligned with core values

---

## 4️⃣ Inputs → State → Actions Overview

| Guard       | Signals/Input                     | State Inference        | Agent Action |
|------------|-----------------------------------|----------------------|-------------|
| Attention  | App usage, input activity, calendar | Deep / Medium / Shallow focus | Block or allow notifications/tasks |
| Energy     | Task duration, self-report, wearables | Energy index (0–100) | Propose rest / reduce scope |
| Identity   | Core values, task metadata, history | Alignment / Conflict | Prompt reassessment / suggest alternatives |

---

## 5️⃣ Implementation Notes

- Hybrid approach: combine **self-report** with **passive monitoring**  
- Privacy first: collect sensitive data only with user consent  
- Configurable thresholds per user and domain  
- Learning: agent improves accuracy by tracking outcomes vs. predictions  

---

## 6️⃣ Versioning

- Document name: `decision_boundaries_use_cases_v1.0.0.md`  
- Versioned for traceability and audit purposes  
- Future updates must increment the version number and update `CHANGELOG.md`  

---

## 7️⃣ Licensing

- Published under **Creative Commons Attribution‑NonCommercial 4.0 International (CC BY‑NC 4.0)**  
- Commercial use of the Metronisys™ brand, materials, or derived content requires permission  
- See `LICENSE.md` and `TRADEMARK.md` for details
