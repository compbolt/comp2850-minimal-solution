# Redesign Priorities — Week 10 Lab 2

## Priority 1: No Confirmation in No-JS (MUST FIX)
**Issue**: P3, P4 low confidence, had to verify task added
**Evidence**: `wk09/data/pilot-notes.md` L45-48, L89-92
**WCAG**: 4.1.3 Status Messages (AA)
**Fix**: Add success message to PRG redirect (query param or session flash)
**Effort**: 1-2 hours

## Priority 2: Edit Inline Fails in No-JS (MUST FIX)
**Issue**: P4 couldn't complete T3 in no-JS mode
**Evidence**: 50% failure rate
**WCAG**: 2.1.1 Keyboard (A) - parity required
**Fix**: Debug no-JS edit flow, ensure PRG works
**Effort**: 1 hour

## Priority 3: Cancel Button Label (SHOULD FIX)
**Issue**: 3/5 confused
**Evidence**: Hesitation, quotes
**WCAG**: 2.4.6 Headings and Labels (AA)
**Fix**: Change to "Cancel (discard changes)"
**Effort**: 10 minutes

## Deferred (Post-Assessment or Semester 2)
- Filter persistence across sessions
- Progress indicator
