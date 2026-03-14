# Terminal Multiplexer Market Research (Corrected)

Research conducted: 2026-01-14 (Updated)

## Important Clarification

### Terminal Emulator vs Terminal Multiplexer

| Type | Definition | Examples |
|------|------------|----------|
| **Terminal Emulator** | GUI app that provides a terminal window | Kitty, Alacritty, Ghostty, WezTerm, iTerm2 |
| **Terminal Multiplexer** | Software that manages multiple terminal sessions in one terminal, with detach/reattach | tmux, GNU Screen, Zellij, dvtm |

Some terminal emulators (Kitty, WezTerm) have built-in split panes, but they are **not multiplexers** because they lack session persistence (detach/reattach).

---

## Complete List of Terminal Multiplexers

Source: Wikipedia "Terminal multiplexer" article

### Tier 1: Widely Used

| Tool | Year | GitHub Stars | Layout File | Notes |
|------|------|-------------|-------------|-------|
| **GNU Screen** | 1987 | N/A | .screenrc | The prototypical terminal multiplexer |
| **tmux** | 2007 | ~40.6k | Layout strings | BSD-licensed, part of OpenBSD base since 2009 |

### Tier 2: Modern/Active

| Tool | Year | GitHub Stars | Layout File | Notes |
|------|------|-------------|-------------|-------|
| **Zellij** | 2021 | ~26.9k | KDL (.kdl) | "Terminal workspace with batteries included" |
| **Byobu** | 2008 | ~2k | Inherits | Profile/config utility for Screen and tmux |
| **3mux** | 2020 | ~1.8k | config.toml | i3-inspired, user-friendly defaults |

### Tier 3: Minimal/Specialized

| Tool | Year | GitHub Stars | Layout File | Notes |
|------|------|-------------|-------------|-------|
| **dvtm** | ~2007 | ~600 | config.h | Tiling window management for console |
| **mtm** | ~2017 | ~400 | None | "Perhaps the smallest useful terminal multiplexer" |
| **vtm** | ~2020 | ~1.5k | Unknown | TUI window manager, multi-party sharing |

### Tier 4: Historical/Niche

| Tool | Status | Notes |
|------|--------|-------|
| **neercs** | Inactive | "screen" backwards, 3D console switching via libcaca |
| **splitvt** | Legacy | Simple split terminal utility |
| **Twin** | Legacy | Text mode window environment, started as MS-DOS project |
| **TD/SMP** | Obsolete | DEC proprietary, VT330/340 terminals only |

---

## Layout File Formats Compared

### tmux
- **No dedicated layout file format**
- Layouts are stored as cryptic strings: `bb62,159x48,0,0{79x48,0,0,79x48,80,0}`
- Requires external tools for user-friendly layouts:
  - **tmuxinator** (YAML) - most popular
  - **tmuxp** (YAML/JSON)
  - **tmuxifier** (shell scripts)
- Built-in layouts: `even-horizontal`, `even-vertical`, `main-horizontal`, `main-vertical`, `tiled`

### GNU Screen
- Uses `.screenrc` for configuration
- `layout dump` command saves region order to file
- Layout format is basic, not designed for sharing
- Layouts don't persist between sessions by default

### Zellij
- **Native KDL format** for layouts
- Human-readable and shareable
- Can load layouts from URLs: `zellij --layout https://...`
- Most modern layout system of all multiplexers

### dvtm
- Configuration via `config.h` (C header file)
- **Requires recompilation** to change layouts
- 4 built-in layouts: vertical stack, bottom stack, grid, fullscreen
- Not designed for sharing

### 3mux
- Uses `config.toml` for configuration
- i3-inspired dynamic layout system
- No dedicated layout file format

---

## Does tmux Have a Layout Sharing Platform?

**No.** After extensive research:

### What Exists for tmux:
1. **awesome-tmux** (GitHub, ~9k stars) - curated list of plugins, themes, configs
2. **tmuxinator configs** - scattered in individual dotfiles repos
3. **DEV Community articles** - tutorials, not a gallery
4. **Reddit r/unixporn** - screenshots with config links
5. **Blog posts** - fragmented, not searchable

### What Doesn't Exist:
- No visual gallery of layouts
- No searchable database
- No one-click install
- No rating/commenting system
- No version compatibility tracking

---

## User Count Estimation (Multiplexers Only)

### Methodology
- Homebrew analytics (tmux): ~327k installs/year on macOS alone
- Pre-installed on most Linux servers (tmux, screen)
- GitHub stars as proxy for developer interest

### Estimates

| Tool | Est. Active Users | Confidence | Notes |
|------|------------------|------------|-------|
| **tmux** | 300k-700k | Medium | Homebrew + Linux servers |
| **GNU Screen** | 100k-300k | Low | Legacy, declining |
| **Zellij** | 20k-50k | Low | Growing, but niche |
| **dvtm** | 2k-5k | Low | Very niche |
| **3mux** | 1k-3k | Low | Small community |

*Note: These are rough estimates. The user correctly points out I may have overestimated.*

---

## Key Finding

**No layout sharing platform exists for ANY terminal multiplexer.**

- tmux has the largest user base but fragmented sharing
- Zellij has the best technical foundation (KDL + URL loading)
- All multiplexers rely on dotfiles repos and blog posts

### Why Doesn't a Platform Exist? (Analysis)

This is surprising. Even niche games like Dyson Sphere Program have dedicated blueprint sharing platforms. Terminal multiplexer users are power users who could easily build such a site.

#### Possible Explanations

| Factor | Games (e.g., Dyson Sphere) | Terminal Multiplexers |
|--------|---------------------------|----------------------|
| **Complexity** | Blueprints are complex, hours to design | Layouts are simple text files |
| **Sharing friction** | Need dedicated platform | GitHub gist works |
| **Standardization** | One game, one format | Multiple tools, different formats |
| **Visual appeal** | 3D factories look impressive | Terminal layouts less shareable |
| **Discovery need** | "How do I build X efficiently?" | "I'll split panes my way" |

#### Cultural Factors

1. **Dotfiles culture** - Developers share via GitHub, not dedicated platforms
2. **tmux's hostile format** - Cryptic layout strings discourage sharing
3. **Personalization** - Layouts depend on workflow, screen size, preferences
4. **r/unixporn exists** - Screenshots with config links (but not searchable)

#### Conclusion

**This is likely a missed opportunity, not an impossibility.**

The demand exists but is dispersed across GitHub, Reddit, and blogs. A centralized, searchable gallery with:
- Visual previews
- One-click install (especially for Zellij with URL loading)
- Categories and ratings

...would fill a genuine gap that the community hasn't bothered to build yet.

---

## Strategic Analysis

### If Building a Layout Platform:

| Approach | Pros | Cons |
|----------|------|------|
| **tmux only** | Largest user base | No native layout format, complex tooling |
| **Zellij only** | Best tech (KDL, URL loading) | Smallest user base |
| **Both tmux + Zellij** | Balanced market | More complex to build |
| **All multiplexers** | Maximum reach | Very complex |

### Recommendation

Given that:
1. tmux has no native layout format (relies on external tools)
2. Zellij has native KDL + URL loading
3. Both lack sharing platforms

**Start with Zellij** (better tech) and consider tmuxinator-compatible exports later.

---

## Sources

### Official Documentation
- tmux: https://github.com/tmux/tmux/wiki
- GNU Screen: https://www.gnu.org/software/screen/manual/
- Zellij: https://zellij.dev/documentation/layouts
- dvtm: https://github.com/martanne/dvtm
- 3mux: https://github.com/aaronjanse/3mux

### Community Resources
- https://github.com/rothgar/awesome-tmux
- https://github.com/zellij-org/awesome-zellij

### Layout Tools
- tmuxinator: https://github.com/tmuxinator/tmuxinator
- tmuxp: https://github.com/tmux-python/tmuxp
- tmuxifier: https://github.com/jimeh/tmuxifier
