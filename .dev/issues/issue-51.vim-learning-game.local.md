# Vim Learning Game - Local Notes

Private scratchpad for issue #51. Not for publishing.

---

## Notes

### Platform Concerns

- Mobile: Possible with on-screen keyboard
- Console: Requires external keyboard (dealbreaker?)

### OpenVim Observations

- Keyboard layout is odd
- Fixed workflow, can't ask questions
- Good tutorial coverage, free

---

## Scratchpad

### Game Ideas (Raw)

- Box pushing mechanics
- Words as tunnels

### Vim Questions

- `qqq` has 4 q's. What does `5fq` do from line start?
  - Answer: Cursor doesn't move. Vim requires the count to be satisfiable; if not enough matches exist, the command fails completely (no partial movement).
