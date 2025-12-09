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

### Theme 1: colour highlighting for different buttons
**Evidence**: 2/3 participants mentioned wanting to differentiate between buttons
**Quotes**:
- P1 (HTMX): "would be nice if highlighted red"
- P3 (No-JS): "clearer button highlighting"

**Design implication**: need to change the colour of the delete button

---

### Theme 2: edit button not working with no-js
**Evidence**: 1/3 couldn't get the edit button to work
**Quotes**:
- P3 (no-js) : "did not work", "edit fails with javascript off" 

**Design implication**: need to fix edit button with javascript off

---

### Theme 3: highlight button when selected (useful for keyboard only)
**Evidence**: 1 participant tested keyboard-only, requested better highlighting when things where selected
**Quotes**:
- P2 (keyboard-only): "hard to see whats highlighted"

**Design implication**: make highlighting focus using keyboard clearer

---

## Accessibility Observations

### Screen Reader (NVDA)
- ✅ Labels announced correctly ("Task title, edit text")
- ✅ Status messages announced ("Task added successfully")
- ❌ Error messages not announced in no-JS path (redirect loses `role="alert"`)

### Keyboard Navigation
- ✅ All features reachable
- ⚠️ Focus could be more visible


---

## Prioritised Issues

Based on frequency + severity:

1. **High**: Edit button not working in no-js (affects 1/1 no-JS participants, low confidence)
2. **Medium**: delete button not a different colour (minor problem, affected 2/3 participants)
3. **Low**: eyboard focus highlighting (minor hesitation, all succeeded)



