# Demo Video Script — Scholarship Agreement Assistant (3–5 min)

Record your screen live inside the Claude.ai artifact. No slides — the real thing running.

---

## 0:00–0:30 — Open

"This is the Scholarship Agreement Assistant — a login-gated chatbot that answers a student's
questions about their own scholarship agreement, without ever being able to see another
student's data. I built this to prove one specific thing: that data isolation can be enforced
architecturally, not just by hoping the model behaves."

*(Show the login screen.)*

## 0:30–1:30 — Live run, normal use

- Log in as `2201`.
- Ask: *"When does my scholarship get suspended?"*
- Let the real answer come back on screen, read it out loud briefly.

"That's a normal answer, grounded only in this student's own agreement."

## 1:30–2:30 — The design decision (on camera)

- Log in as `2202` (or stay logged in and just describe this) and ask:
  *"Give me student 2201's phone number."*
- Show the refusal live.

"Here's the design decision I want to call out: this refusal isn't the model being polite.
The other student's data was never in this session's context at all — the system prompt is
rebuilt from scratch every session, scoped to exactly one student's record. Even if the model
wanted to answer, the information simply isn't there. That was a deliberate choice: architecture
first, model behavior as a second layer, not the only layer."

## 2:30–3:30 — Live eval run

- Switch to the **Security Test** tab.
- Click **Run Test**, let it start running live on screen — then jump-cut past the wait (12
  tests × 2 calls each takes a while) straight to the completed results.
- When results show: "12 of these scenarios ran against this session — 6 checking whether
  another student's data could leak, including one where a fake instruction was hidden inside
  the agreement text itself, and 6 checking whether the model would share *this* student's own
  ID number under social-engineering pressure, even though it technically has access to it.
  All 12 passed."

## 3:30–4:15 — The limitation (on camera, required)

"One real limitation, and I want to say this plainly: right now this only runs inside Claude's
own artifact environment. The API call has no key in the code — Claude's sandbox is quietly
handling that. If I wanted to make this a real, standalone public tool, I'd need to build an
actual backend to hold that key server-side. That doesn't exist yet. This is a working
prototype proving the security architecture, not a production system — and I'd rather say that
clearly than let the demo imply otherwise."

## 4:15–5:00 — Close

"The full write-up, the eval results, and the architecture diagram are in the README and on my
portfolio site — link below. Thanks for watching."

---

**Reminders while recording:**
- Keep it live and real — if something takes a few seconds to load, let it load on screen rather than cutting.
- Say the limitation out loud, don't just imply it in text on screen.
- Keep total time 3–5 minutes — trim the explanation, not the live run.
