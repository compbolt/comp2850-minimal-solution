# Pilot Findings Analysis — Week 9

**Participants**: 5 (3 HTMX, 2 No-JS)
**Date range**: [YYYY-MM-DD to YYYY-MM-DD]

---

## Quantitative Summary

### Task 1: Filter and Complete
| Metric | HTMX (n=3) | No-JS (n=2) | Overall |
|--------|------------|-------------|---------|
| Mean time (s) | 42 | 58 | 48 |
| Success rate | 100% | 100% | 100% |
| Mean errors | 0.3 | 0 | 0.2 |
| Mean confidence | 4.3/5 | 4.0/5 | 4.2/5 |

**Interpretation**: Task 1 successful for all. HTMX slightly faster (no page reload). Low error rate. High confidence.

---

### Task 2: Add New Task
| Metric | HTMX | No-JS | Overall |
|--------|------|-------|---------|
| Mean time (s) | 28 | 35 | 30.6 |
| Success rate | 100% | 100% | 100% |
| Mean errors | 0.7 | 1.0 | 0.8 |
| Mean confidence | 4.7/5 | 3.5/5 | 4.2/5 |

**Interpretation**: High success but errors common (validation). HTMX confidence higher (instant feedback). No-JS participants less sure (PRG redirect, no confirmation message).

---

[Repeat for T3, T4]

---

## Qualitative Themes

### Theme 1: Confirmation Feedback Critical
**Evidence**: 4/5 participants mentioned needing "confirmation it worked"
**Quotes**:
- P1 (HTMX): "I like seeing 'Task added' immediately"
- P3 (No-JS): "I had to scroll down to check it was there - not obvious"

**Design implication**: No-JS path needs explicit success message (PRG currently shows none).

---

### Theme 2: Edit Cancel Button Confusing
**Evidence**: 3/5 participants hesitated on Cancel button
**Quotes**:
- P2: "Will Cancel save my changes or lose them?"
- P4: "I clicked it to test - wasn't sure"

**Design implication**: Button label needs clarification ("Cancel (discard changes)")

---

### Theme 3: Keyboard Access Excellent
**Evidence**: 2 participants tested keyboard-only (requested). Both succeeded all tasks.
**Quotes**:
- P5 (keyboard-only): "Tab order makes sense, focus always visible"

**Design implication**: Keep current keyboard implementation.

---

## Accessibility Observations

### Screen Reader (NVDA)
- ✅ Labels announced correctly ("Task title, edit text")
- ✅ Status messages announced ("Task added successfully")
- ❌ Error messages not announced in no-JS path (redirect loses `role="alert"`)

### Keyboard Navigation
- ✅ All features reachable
- ✅ Focus visible
- ⚠️ Tab order logical but Edit→Save→Cancel could be clearer

---

## Prioritised Issues

Based on frequency + severity:

1. **High**: No confirmation message in no-JS path (affects 2/2 no-JS participants, low confidence)
2. **Medium**: Cancel button ambiguous (3/5 confused, but completed anyway)
3. **Low**: Edit button focus order (minor hesitation, all succeeded)
