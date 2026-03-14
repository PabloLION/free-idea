# Vim Learning Game

**Status:** Paused / Not Proceeding
**Decision:** Pivot to programming game instead
**Date:** 2026-01-16

---

## Why Not Proceeding

Vim has ~100+ commands. Many have no natural game purpose:

| Command    | Vim Purpose         | Game Purpose               |
| ---------- | ------------------- | -------------------------- |
| `gU/gu/g~` | Change case         | ???                        |
| `Ctrl-a/x` | Increment/decrement | ???                        |
| `J`        | Join lines          | Conflicts with grid design |
| `^` vs `0` | First non-blank     | Redundant in game          |
| `"a-z`     | 26 registers        | Why 26 inventory slots?    |

We would have to **invent mechanics** just to include commands, rather than commands naturally fitting gameplay.

### Comparison: Programming Games Are More Viable

| Aspect | The Farmer Was Replaced | Our Vim Game |
| ------ | ----------------------- | ------------ |
| Mechanic fit | Code IS gameplay | Commands mapped TO mechanics (forced) |
| Skill value | Python = valuable, growing | Vim = niche, shrinking (AI writes code) |
| Market proof | 500k+ copies, 96% positive | Unproven |

---

## Existing Vim Learning Tools

| Name | URL | Type | Pricing | Evaluation |
| ---- | --- | ---- | ------- | ---------- |
| VIM Adventures | https://vim-adventures.com/ | Zelda-like puzzle | Freemium | Too limited free levels |
| Vim Racer | https://vim-racer.com/ | Racing | Free | Too simple |
| Vim Snake | https://vimsnake.com/ | Snake game | Free | Too simple |
| VimHero | https://www.vim-hero.com/ | Tutorial + challenges | Freemium | Good resource, not a game; too limited free content |
| VimGenius | http://www.vimgenius.com/ | Flashcards | Free | Good resource, not a game |
| OpenVim | https://openvim.com/ | Interactive tutorial | Free | Comprehensive; fixed workflow, not smart/modern |
| PacVim | https://github.com/jmoon018/PacVim | Terminal PacMan | Free | Outdated, too simple |
| VimGore | https://vimgore.netlify.app/ | Code fixing | Free | Not available (source exists) |
| VSCode Vim Academy | https://github.com/kaisunc/vscodevimacademy | VSCode extension | Freemium | Closed source, last update 2022 |
