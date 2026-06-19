# CLAUDE.md

## ECC — Enhanced Claude Code Framework

This project runs the full **ECC (Everything Claude Code)** agent harness.
ECC is installed globally at `/root/.claude/` with the `developer` profile.

### Active ECC Components

| Component | Location |
|-----------|----------|
| Rules | `/root/.claude/rules/ecc/` — Angular, React, Python, Go, Rust, TypeScript, common |
| Commands | `/root/.claude/commands/` — 80+ slash commands |
| Agents | `/root/.claude/agents/` — 60+ specialized subagents |
| Skills | `/root/.claude/skills/` — continuous learning, session, quality |
| Hooks | `/root/.claude/hooks/hooks.json` — 7 event types wired in settings |
| MCP configs | `/root/.claude/mcp-configs/` — preconfigured integrations |

### Active MCP Servers

- **codebase-memory-mcp** — Code knowledge graph (158 languages, sub-ms queries, 14 tools).
  Binary: `/root/.local/bin/codebase-memory-mcp`
  Usage: say "Index this project" or ask "who calls X" / "what does Y depend on"

### Key ECC Slash Commands

| Command | What it does |
|---------|-------------|
| `/plan` | Restate requirements, assess risks, step-by-step plan |
| `/code-review` | Quality review (`--fix` to apply findings) |
| `/security-scan` | Security audit of pending changes |
| `/build-fix` | Detect build system and incrementally fix errors |
| `/learn` | Extract reusable patterns from the current session |
| `/prp-plan` | Comprehensive implementation plan with codebase analysis |
| `/feature-dev` | Guided feature development with architecture focus |
| `/checkpoint` | Create/verify workflow checkpoints |
| `/sessions` | List known projects and session stats |

### ECC Hook Events (auto-active)

- **PreToolUse** — GateGuard fact-forcing, config protection, observation, MCP health check
- **PostToolUse** — Quality gate, accumulator, context monitor, metrics bridge
- **SessionStart** — Load previous context, detect package manager
- **Stop** — Format/typecheck batch, session persist, cost tracker
- **PreCompact** — Save state before context compaction
- **SessionEnd** — Session end lifecycle marker

### Plugin Root

`CLAUDE_PLUGIN_ROOT=/root/.claude` (set in `.claude/settings.json`)

### Disabling GateGuard for Setup Commands

If GateGuard blocks shell setup work, prefix with `ECC_GATEGUARD=off`:
```bash
ECC_GATEGUARD=off <your-command>
```

### Source Repos

- ECC: `/home/user/ECC/` (github.com/affaan-m/ECC) — primary framework, developer profile
- ECC zh: `/home/user/everything-claude-code-zh/` (github.com/xu-xiang/everything-claude-code-zh) — Chinese-localized commands/agents merged in
- codebase-memory-mcp: `/home/user/codebase-memory-mcp/` (github.com/DeusData/codebase-memory-mcp)
