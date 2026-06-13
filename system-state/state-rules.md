# SYSTEM STATE — CONTROL RULES

This file defines the governing logic for how Sextant Protocol system state is updated and maintained.

---

## 1. SOURCE OF TRUTH

The Scenario Simulator is the ONLY source allowed to generate state changes.

All system state updates must originate from simulation outputs, not manual edits.

---

## 2. STATE UPDATE TRIGGERS

System state changes occur only under the following conditions:

- HIGH VOLATILITY → increases MACRO INDEX and elevates risk state  
- LOW VOLATILITY → stabilizes or reduces MACRO INDEX  
- SHOCK EVENT → transitions SYSTEM STATE to VOLATILE or TRANSITION  
- RECOVERY PHASE → returns SYSTEM STATE to STABLE  

---

## 3. UPDATE PROCESS

When a trigger occurs, the system must:

### A. Update Current State File
File: `system-state/current-state.md`

- Update STATE VERSION
- Update SYSTEM STATE
- Update MACRO INDEX
- Update RISK VECTOR
- Update LAST UPDATE trigger description

---

### B. Append to History Log
File: `system-state/state-history.md`

- Add new version entry
- Include timestamp
- Include trigger type
- Record MACRO INDEX change

---

## 4. VERSION CONTROL RULE

State versions must increment sequentially:

- v1.0 → baseline system  
- v1.1 → minor adjustment  
- v1.2 → incremental shift  
- v2.0 → structural or regime change  

---

## 5. HUMAN OVERRIDE RULE

Manual edits are allowed only for documentation clarity.

Any change to system state must be simulation-driven to be considered valid.

---

## 6. SYSTEM BEHAVIOR PRINCIPLE

The system is designed to reflect evolving conditions, not static assumptions.

State is a function of simulated pressure, not human declaration.
