# Evaluation Protocol — Week 9 Pilots

**Module**: COMP2850 HCI
**Activity**: Task-based usability pilots
**Date**: [YYYY-MM-DD]
**Researcher**: [Your Name]

---

## Purpose

Evaluate task manager usability and accessibility through structured pilots. Data will inform Week 10 redesign and assessment submission.

## Consent (GDPR/Data Protection Act 2018)

**Lawful basis**: Legitimate interest (educational research) + informed consent

**Before starting**, confirm:
- [ ] Purpose explained (evaluate task manager, not testing you)
- [ ] Tasks described (4 scenarios, ~15 minutes)
- [ ] Data collected listed (times, clicks, observations - no PII)
- [ ] Right to withdraw explained (stop anytime, data deleted)
- [ ] Participant verbally consents

**Record**: Participant pseudonym (P1, P2...), date, consent confirmed (initials)

---

## Procedure

### Setup (5 minutes)
1. **Assign mode**: Participant 1 → HTMX, Participant 2 → No-JS (alternate)
2. **Disable JS if needed**: Chrome DevTools → Settings → Disable JavaScript
3. **Set session ID**: Open browser DevTools Console, paste:
   ```javascript
   document.cookie = "sid=P1_7a9f; path=/";  // P1 = Participant 1, random suffix

