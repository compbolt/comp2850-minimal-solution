# Evaluation Tasks — Week 9

use this to clear ports: pkill -f java

## Task 1: Find and delete
**Scenario**: you have just cooked for your family

**Instructions**:
1. Find the task titled "Cook dinner"
2. Delete it
3. Verify it's deleted

**Success criteria**:
- Participant finds correct task within 30 seconds
- deleting the task works (task is removed)
- Visual confirmation shown (task no longer there)

**Inclusion focus**: Keyboard access, screen reader announcement

---

## Task 2: Add New Task
**Scenario**: you decide to go out for dinner and make a booking for 19:30

**Instructions**:
1. Add a new task: "dinner booked for 19:30"
2. Confirm it appears in the list

**Success criteria**:
- Form submission works (HTMX + no-JS)
- New task appears immediately (or after reload for no-JS)

**Inclusion focus**: Error handling (if blank title), status announcements

---

## Task 3: Edit Task Inline
**Scenario**: dinner booking was changed from 19:30 to 19:45

**Instructions**:
1. Find task "dinner booked for 19:30"
2. Edit it to "dinner booked for 19:45"
3. Save the change

**Success criteria**:
- Edit mode activates (input appears)
- Save updates the title
- Focus returns to edited task
- Done in under 90 seconds

**Inclusion focus**: Focus management, keyboard-only editing, Cancel button

---

## Task 4: filter task
**Scenario**: you've forgotten what time dinner was and need to find the task

**Instructions**:
1. filter tasks to find task: "dinner booked for 19:45"
2. Confirm it's there

**Success criteria**:
- task is visually presented on the screen
- Status message announced

**Inclusion focus**: Confirmation (HTMX has `hx-confirm`, no-JS has none - documented trade-off)

---

## Metrics per Task

For each task, record:
- **Time-on-task** (seconds from start to completion)
- **Success** (1 = completed, 0 = abandoned)
- **Error count** (validation errors, wrong clicks)
- **Mode** (HTMX or no-JS)
