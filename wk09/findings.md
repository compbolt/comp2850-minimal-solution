# Pilot Findings Analysis — Week 9

**Participants**: 3 (2 HTMX, 1 No-JS)
**Date range**: [2025-12-02 to 2025-12-04]

---

## Quantitative Summary

### Task 1: Find and delete
| Metric | HTMX (n=2) | No-JS (n=1) | Overall |
|--------|------------|-------------|---------|
| Mean time (s) | 4.705 | 1.77 | 48 |
| Success rate | 100% | 100% | 100% |
| Mean errors (out of 5) | 1.5 | 3.0 | 2.25 |
| Mean confidence | 4.0/5 | 4.0/5 | 4.0/5 |

**Interpretation**: task 1 seemed to be pretty successful, highlght using colour was requested, low error high confidence, the person doing no-js seemed to be more competent.

---

### Task 2: Add New Task
| Metric | HTMX (n=2)| No-JS (n=1)| Overall |
|--------|------|-------|---------|
| Mean time (s) | 11.69 | 5.40 | 30.6 |
| Success rate | 100% | 100% | 100% |
| Mean errors | 2.0 | 2.0 | 2.0 |
| Mean confidence | 4.5/5 | 4.0/5 | 4.25/5 |

**Interpretation**: success was common and people seem to be pretty confident, seemed to lack confirmation, once again no-js was more competent despite the slower reloads, high confidence low error.

---

### Task 3: Edit Task Inline
| Metric | HTMX (n=2)| No-JS (n=1)| Overall |
|--------|------|-------|---------|
| Mean time (s) | 5.535 | 90(dnf) | 30.6 |
| Success rate | 100% | 0% | 66.7% |
| Mean errors | 2.0 | 5.0 | 3.5 |
| Mean confidence | 3.5/5 | 1.0/5 | 2.25/5 |

**Interpretation**: worked well for htmx however it completely failed for the no-js set of data as inline edit wasn't possible, high confidence where it worked, could do with highlighting what was selected

---


### Task 4: Add New Task
| Metric | HTMX (n=2)| No-JS (n=1)| Overall |
|--------|------|-------|---------|
| Mean time (s) | 6.005 | 3.42 | 3.06 |
| Success rate | 100% | 100% | 100% |
| Mean errors | 2.5 | 0.0 | 0.8 |
| Mean confidence | 4.0/5 | 5.0/5 | 4.5/5 |

**Interpretation**: very high confident and high success, seemed to be fast as wel, 

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
