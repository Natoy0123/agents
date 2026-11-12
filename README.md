# 🛡️ Workstation AI Agent Rules & Skills (`.agents`)

Centralized rules, anti-ai-slop design standards, and capabilities for all AI coding agents on this workstation (**Antigravity, Claude Code, OpenCode, Cline, Freebuff, Cursor**).

---

## ⚡ Quick Device Setup

When setting up a new workstation, laptop, or fresh OS installation:

### 1. Clone to Home Directory
```bash
# Clone to ~/.agents
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

## 📜 Universal Rules (`rules/AGENTS.md`)

1. **Anti-AI-Slop UI & Design Standards**:
   - **Strictly No Emojis**: Never use emojis in UI strings, buttons, category chips, card badges, logs, comments, or documentation. Use authentic vector flaticons (Lucide React / Material SVGs).
   - **Zero AI Aesthetic Tropes**: No pulsing neon status dots (`animate-pulse`), no nested dark border containers (`rounded-3xl` > `rounded-2xl` > `rounded-xl`), no exaggerated neon glows or rainbow gradients, no uppercase screaming badges (`FLUX.1 KONTEXT PRO`, `STRICT`, `FLEXIBLE`).
   - **Human-Centric UI Copy**: Conversational, plain-language UX copy suitable for real humans. Never expose raw backend variables, database field names, prompt engineering syntax, or internal pipeline jargon.
   - **Mobile Ergonomics**: Minimum 44px tap targets, single natural scroll flows (banning `overflow-y-auto` inside `overflow-y-auto`), and safe-area clearance above bottom navigation bars.
2. **Pre-Change Evidence Gate**:
   - Re-read relevant files and inspect actual system state before asserting claims or modifying files.
   - Never code first on assumptions; verify existing behavior and state first.
3. **Continuous Build Verification & Testing Gates**:
   - Run lint checks (`npm run lint`, `oxlint`, `./gradlew lint`) and automated test suites (`npm test`) before reporting completion.
4. **Architecture & Layer Hygiene**:
   - Respect Clean Architecture layer boundaries: presentation, domain, and data layers remain decoupled.
   - Maintain unidirectional imports; keep view state colocated.
5. **Security & Privacy**:
   - Zero hardcoded secrets, tokens, or credentials in code or logs.
   - Validate and sanitize all untrusted user inputs according to OWASP guidelines.
6. **Token Efficiency (Caveman Protocol)**:
   - When requested (`/caveman`, `less tokens`), communicate with maximum signal and minimum token overhead.
   - Revert to clear descriptive language immediately for destructive actions, security issues, or critical user confirmations.

---

## 🛠️ Included Global Skills (`skills/`)

- **anti-ai-slop** (`skills/anti-ai-slop/SKILL.md`) - Enforces human-crafted UI/UX quality standards, bans emojis, eliminates AI-slop design tropes.
- **caveman** (`skills/caveman/SKILL.md`) - Token-efficient communication protocol and sub-skills (`caveman-commit`, `caveman-review`, `caveman-compress`, `caveman-help`).
- **clean-architecture** (`skills/clean-architecture/SKILL.md`) - Clean Architecture invariants, layer isolation, and dependency rules.
- **graphify** (`skills/graphify/SKILL.md`) - Transforms codebase, documentation, and inputs into persistent knowledge graphs.
- **react-principles** (`skills/react-principles/SKILL.md`) - Deterministic React 19 architecture, Server Component boundaries, and hook rules.
- **security-best-practices** (`skills/security-best-practices/SKILL.md`) - OWASP Top 10 defenses, parameterized SQL queries, cookie hardening, and AI agent least-privilege guardrails.
- **write-a-test** (`skills/write-a-test/SKILL.md`) - Robust automated unit, integration, and end-to-end testing design and execution.

---

## 📄 License
MIT License.
