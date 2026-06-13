# SYSTEM STATE — CONTROL RULES

This file defines how system state updates are generated.

---

## 1. SOURCE OF TRUTH

The ONLY system that can modify MACRO INDEX is:

→ Scenario Simulator (external execution layer)

---

## 2. STATE UPDATE TRIGGERS

State updates occur when simulator outputs:

- HIGH VOLATILITY → increase MACRO INDEX
- STABILITY → maintain or reduce MACRO INDEX
- SHOCK EVENT → change SYSTEM STATE to VOLATILE or TRANSITION
- RECOVERY → return to STABLE

---

## 3. UPDATE ACTIONS

When a trigger occurs:

### A. Update current-state.md
- Replace MACRO INDEX
- Update STATE VERSION
- Update SYSTEM STATE

### B. Append to state-history.md
- Add new version entry
- Include trigger event description

---

## 4. VERSION RULE

Each update increments version:

v1.0 → v1.1 → v1.2 → v2.0 (major structural change)

---

## 5. HUMAN RULE

Manual edits are allowed ONLY for documentation.
System truth must come from simulator logic.
