# Issue #53: Zellij Layout Sharing Platform

GitHub: https://github.com/PabloLION/free-idea/issues/53

## Idea

A platform for sharing and discovering Zellij terminal layouts. Layouts take time and experience to optimize - they involve screen real estate decisions, workflow patterns, and iterative refinement.

## Domain Research

### Availability

| Domain | Status |
|--------|--------|
| `zellij-layouts.com` | Available (confirmed via whois) |
| `zellij-layouts.dev` | Likely available (no DNS records) |

### Pricing Comparison

#### .com Domain

| Registrar | First Year | Renewal | Notes |
|-----------|------------|---------|-------|
| Cloudflare | $9.77 | $9.77 | At-cost, no markup, lowest long-term |
| Porkbun | $7.97 | $11.08 | First-year discount, flat renewals forever |
| Namecheap | ~$6-10 | ~$15 | Competitive first-year, higher renewals |
| GoDaddy | ~$12 | ~$20+ | Avoid, expensive renewals |

#### .dev Domain

| Registrar | First Year | Renewal | Transfer | Notes |
|-----------|------------|---------|----------|-------|
| Cloudflare | $12 | $12 | $12 | At-cost pricing |
| Porkbun | ~$10 | $12-13 | - | Flat renewals |
| Namecheap | $10.98 | ~$13 | - | Free WHOIS privacy |
| Dynadot | $10.00 | $12.50 | $11.99 | - |
| Cheapest found | $4.99 | $12.20 | $10.16 | (via tld-list.com comparison) |

#### Wholesale Prices (Registry Level)

- **.com**: Verisign charges ~$9.59 to registrars
- **.dev**: Google Registry increased from $10 → $12 (as of 2024)

#### All Registrars Include

- Free WHOIS privacy (Cloudflare, Porkbun, Namecheap)
- DNS management
- No hidden fees

#### Sources

- https://porkbun.com/products/domains
- https://tld-list.com/tld/dev
- https://www.registry.google/policies/pricing/dev/
- https://domaindetails.com/registrars/cheapest

### Recommendation

- `.com` is slightly cheaper (~$10/year) and more universal
- `.dev` requires HTTPS (built-in security), more developer-focused
- Cloudflare or Porkbun offer best long-term value

## Existing Similar Projects

| Resource | URL | Notes |
|----------|-----|-------|
| awesome-zellij | https://github.com/zellij-org/awesome-zellij | Plugin list, not layout-focused |
| Official examples | https://zellij.dev/documentation/layout-examples.html | Limited examples |
| Layout docs | https://zellij.dev/documentation/layouts | Technical reference |

**Gap:** No dedicated layout sharing platform/gallery exists.

## Proposed Features

- Layout gallery with screenshots/previews
- Categories: development, DevOps, writing, data science, etc.
- One-click try via Zellij's URL loading (`zellij --layout https://...`)
- User ratings and comments
- Version compatibility tracking (KDL format, Zellij version)
- Search and filter by use case, pane count, plugins used

## Technical Notes

- Zellij supports loading layouts from URLs natively
- Layouts use KDL format (since v0.32.0)
- Commands in URL-loaded layouts start suspended for security

## Market Research

See detailed research: [issue-53.terminal-multiplexer-research.md](./issue-53.terminal-multiplexer-research.md)

### Key Findings

1. **No layout sharing platform exists** for ANY terminal multiplexer
2. **tmux dominates** with ~40k GitHub stars
3. **Zellij has best tech** (native KDL format + URL loading)
4. **Layout sharing is fragmented** across dotfiles repos, blog posts, r/unixporn

### Terminal Multiplexers Only (Corrected)

Note: Ghostty, Kitty, WezTerm are **terminal emulators**, not multiplexers.

| Tool | Year | GitHub Stars | Layout Format |
|------|------|-------------|---------------|
| GNU Screen | 1987 | N/A | .screenrc |
| tmux | 2007 | ~40.6k | Layout strings (cryptic) |
| Zellij | 2021 | ~26.9k | KDL files (human-readable) |
| Byobu | 2008 | ~2k | Inherits from tmux/screen |
| 3mux | 2020 | ~1.8k | config.toml |
| dvtm | ~2007 | ~600 | config.h (recompile) |

### Why Zellij Has an Advantage

- **Native layout file format** (KDL) - human-readable, shareable
- **URL loading** - `zellij --layout https://...` built-in
- tmux has no native layout format (relies on tmuxinator/tmuxp)

### Strategic Options

1. **Zellij-only** - Best tech, but smaller market
2. **tmux + Zellij** - Larger reach, more complex
3. **tmux-only** - Largest market, but no native layout format

### Recommendation

**Start with Zellij** - it has the best technical foundation for layout sharing. Consider adding tmuxinator export later.

## Next Steps

- [ ] Decide: Zellij-only vs multi-multiplexer approach
- [ ] Decide on domain (.com vs .dev)
- [ ] Design basic MVP features
- [ ] Choose tech stack
