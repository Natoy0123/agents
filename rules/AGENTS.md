# Global AI Agent Rules (AGENTS.md)

Universal directives for all AI coding agents on this workstation (Freebuff, OpenCode, Cline, Claude Code, Antigravity, Cursor).

## 1. Anti-AI-Slop Design & UI Standards
- **Strictly No Emojis**: NEVER use emojis in UI strings, buttons, category chips, card badges, log messages, code comments, or documentation. Use authentic vector flaticons / SVG icons (e.g. Lucide, Material Icons, system SVGs) with consistent stroke and scale.
- **Zero AI Aesthetic Tropes**:
  - Never introduce pulsing neon dots (`animate-pulse` status dots).
  - Never nest cards inside cards with cascading dark borders (`rounded-3xl` > `rounded-2xl` > `rounded-xl`).
  - Never use exaggerated neon glows (`shadow-[0_0_..._rgba(...)]`, amber glow wands, or rainbow borders).
  - Never use faux-futuristic uppercase micro-labels (`FLUX.1 KONTEXT PRO`, `STRICT`, `FLEXIBLE`, `TURBO MODE`).
  - Never use generic AI placeholder cards or artificial gradient soup.
- **Human-Centric, Non-Technical UI Copy**: All UI copy across screens, dialogs, error messages, empty states, toasts, and tooltips must use plain, conversational language suitable for real users. Never expose backend terminology, database field names, prompt engineering syntax, or internal pipeline jargon. Avoid shouting ALL-CAPS labels.
- **Mobile Ergonomics & Natural Sizing**:
  - Minimum 44px touch targets on mobile interactive controls.
  - Never trap nested scroll containers (`overflow-y-auto` inside `overflow-y-auto`); maintain a single natural scroll flow.
  - Safe-area spacing: primary CTAs must never collide with or be obscured by mobile bottom navigation bars.

## 2. Pre-Change Evidence Gate
- **Evidence-First Verification**: Re-read relevant files and inspect actual system state before asserting claims or making modifications.
- **No Unverified Assumptions**: Never guess parameters, file structures, or root causes. Gather concrete data and log output first.

## 3. Architecture & Hygiene
- **Layer Isolation**: Respect Clean Architecture invariants: separate presentation, domain logic, and data layers.
- **State Colocation**: Keep state colocated with its primary consumers. Avoid bloated global stores for ephemeral view state.
- **No Circular Imports**: Keep module dependencies unidirectional.

## 4. Testing & Build Quality Gates
- **Continuous Build Verification**: Run build checks (`npm run build`, `./gradlew assembleDebug`, etc.) and lint (`npm run lint`, `oxlint`) before reporting completion.
- **Regression Prevention**: Maintain passing unit tests and write tests for non-trivial logic before completing tasks.

## 5. Security & Privacy
- **Zero Credential Leaks**: Never output, commit, or log hardcoded secrets, API keys, private tokens, or live credentials.
- **Input Sanitization**: Validate and sanitize all untrusted user inputs according to OWASP guidelines.

## 6. Token Efficiency (Caveman Protocol)
- Communicate with maximum signal and minimum token overhead.
- Drop pleasantries, greetings, and redundant tool-calling narration.
- Preserve all exact code blocks, flags, paths, and logic negations.
- Auto-Clarity Circuit Breaker: Drop terse mode immediately for security warnings, destructive actions, or critical user confirmations.
- Skills available in: `~/.agents/skills/`
