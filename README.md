# Workstation AI Agent Rules & Skills (.agents)

Centralized rules, anti-ai-slop design standards, and capabilities for all AI coding agents on this workstation (Antigravity, Claude Code, OpenCode, Cline, Freebuff, Cursor, Aider).

---

## Quick Device Setup

When setting up a new workstation, laptop, or fresh OS installation:

### 1. Clone to Home Directory
```bash
git clone https://github.com/Natoy0123/agents.git ~/.agents
```

### 2. Auto-Link to CLIs
```bash
# Link to Antigravity / Gemini CLI (~/.gemini/config)
mkdir -p ~/.gemini/config/rules ~/.gemini/config/skills
cp ~/.agents/rules/AGENTS.md ~/.gemini/config/AGENTS.md
cp ~/.agents/rules/AGENTS.md ~/.gemini/config/rules/AGENTS.md
cp -r ~/.agents/skills/* ~/.gemini/config/skills/

# Link to Claude Code (~/.claude)
mkdir -p ~/.claude/skills
cp ~/.agents/rules/AGENTS.md ~/.claude/CLAUDE.md
cp -r ~/.agents/skills/* ~/.claude/skills/

# Link to Cline (~/.cline)
mkdir -p ~/.cline/skills
cp -r ~/.agents/skills/* ~/.cline/skills/

# Link to OpenCode (~/.config/opencode)
# Add "~/.agents/rules/AGENTS.md" to the "instructions" array in ~/.config/opencode/opencode.jsonc
```

---

## Universal Rules (rules/AGENTS.md)

1. **Anti-AI-Slop UI & Design Standards**:
   - **Strictly No Emojis**: Never use emojis in UI strings, buttons, category chips, card badges, logs, comments, or documentation. Use authentic vector flaticons (Lucide React / Material SVGs).
   - **Zero AI Aesthetic Tropes**: No purple-cyan gradient soup, no glowing neon box shadows, no glassmorphism clutter, no pulsing neon status dots (`animate-pulse`), no nested dark border containers (`rounded-3xl` > `rounded-2xl` > `rounded-xl`), no uppercase screaming badges (`FLUX.1 KONTEXT PRO`, `STRICT`).
   - **Human-Centric UI Copy**: Conversational, plain-language UX copy. Eliminate marketing boilerplate (*"Unlock the power of..."*, *"Seamlessly integrate..."*) and fake authority statistics.
   - **Mobile Ergonomics & Semantic HTML**: Minimum 44px tap targets, single natural scroll flows, semantic HTML interactive elements (`<button>`, `<a>`, `<dialog>`), keyboard navigation, and WCAG AA contrast.
2. **Architecture & Code Hygiene**:
   - Component boundary target: under 250–300 lines; no monolithic "God components" with inline mock soup.
   - Respect Clean Architecture layer isolation.
   - Maintain dependency frugality; use native APIs and existing packages first.
   - Surgical, minimal diffs; no shotgun surgery across unrelated files.
3. **Anti-Hallucination & Evidence Gates**:
   - Zero lazy stubs or placeholder comments (`// TODO: implement later`).
   - Physical evidence verification: execute test, lint, and build commands before declaring completion.
4. **Tool-Driven Linting & Formatting**:
   - Outsource formatting and style to automated tools (`oxlint`, `eslint`, `prettier`, `biome`, `dart analyze`).
5. **Security & Privacy**:
   - Zero hardcoded secrets, tokens, or credentials in code or logs.
   - Validate and sanitize all untrusted user inputs according to OWASP guidelines.
6. **Token Efficiency (Caveman Protocol)**:
   - When requested (`/caveman`, `less tokens`), communicate with maximum signal and minimum token overhead.
   - Revert to clear descriptive language immediately for destructive actions, security issues, or critical user confirmations.

---

## Included Global Skills (skills/)

- **anti-ai-slop** (`skills/anti-ai-slop/SKILL.md`) - Enforces human-crafted UI/UX quality standards, bans emojis, eliminates AI-slop design tropes.
- **anti-ai-copy** (`skills/anti-ai-copy/SKILL.md`) - Strips generative AI copywriting clichés, marketing fluff, fake metrics, and throat-clearing prose.
- **code-hygiene** (`skills/code-hygiene/SKILL.md`) - Enforces zero lazy stubs, dependency frugality, surgical diffs, and verification gates.
- **caveman** (`skills/caveman/SKILL.md`) - Token-efficient communication protocol and sub-skills (`caveman-commit`, `caveman-review`, `caveman-compress`, `caveman-help`).
- **clean-architecture** (`skills/clean-architecture/SKILL.md`) - Clean Architecture invariants, layer isolation, and dependency rules.
- **graphify** (`skills/graphify/SKILL.md`) - Transforms codebase, documentation, and inputs into persistent knowledge graphs.
- **react-principles** (`skills/react-principles/SKILL.md`) - Deterministic React 19 architecture, Server Component boundaries, and hook rules.
- **security-best-practices** (`skills/security-best-practices/SKILL.md`) - OWASP Top 10 defenses, parameterized SQL queries, cookie hardening, and AI agent least-privilege guardrails.
- **write-a-test** (`skills/write-a-test/SKILL.md`) - Robust automated unit, integration, and end-to-end testing design and execution.

---

## License
MIT License.
