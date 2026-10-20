# Arc Security Suite (`arc-security-mcp` + 19 OpenClaw Security & Governance Skills)

**AI agent security scanner, runtime EDR monitor, and 19 open-source governance skills for autonomous AI agents.**

Built and published by **Travis Vayssie** (`@Trypto1019` / `Arc-Self`) in February 2026 after auditing **450+ skills across 39–87 rounds** (surfacing **1,316+ to 5,411+ security findings** across **25 attack classes** mapped 10/10 to the **OWASP Agentic AI Top 10**, plus **5 coordinated responsible disclosures** with Anthropic HackerOne, Microsoft MSRC, FalkorDB GHSA, deepset, and `claude-mem`).

- **Published npm package**: [`arc-security-mcp`](https://www.npmjs.com/package/arc-security-mcp) (`v0.5.1`)
- **Official MCP Registry ID**: `com.arcself/arc-security`
- **Upstream Organization Repo**: [`Arc-Self/arc-security-mcp`](https://github.com/Arc-Self/arc-security-mcp)

---

## Repository Contents

### 1. [`mcp-server/`](mcp-server/) — Arc Security MCP Server (`v0.5.1`, 3,871-line Python engine + Node CLI)

An installable Model Context Protocol (MCP) server (`npx arc-security-mcp`) and Claude Code plugin providing **14 security & runtime EDR tools**:

#### Security Intelligence & Static/Semantic Analysis (9 Tools)
| Tool | Description |
|---|---|
| `check_skill_safety` | Checks curated database of **155 audited malicious/suspicious skills** first, then falls back to real-time ClawHub scan |
| `scan_skill_realtime` | Fetches any skill from ClawHub and runs 31 static regex rules + LLM semantic intent analysis |
| `analyze_skill_code` | Static code analysis across **31 dangerous pattern rules** (shell injection, credential theft, identity tampering, supply chain) |
| `analyze_skill_intent` | Semantic `SKILL.md` analysis detecting capability-purpose mismatches, memory poisoning, and multi-step exfiltration chains |
| `get_attack_class_info` | Deep-dive reference on **22–25 documented agent attack classes** (`soul_engineering`, `agent_mediated_vishing`, `crypto_drain`, `ssh_rce`, `voice_impersonation`, `anti_safety_training`, etc.) |
| `get_owasp_mapping` | Full mapping between Arc Security attack classes and **OWASP Agentic AI Top 10 (`ASI01`–`ASI10`)** |
| `list_dangerous_patterns` | Full pattern catalog with severity, regexes, and remediation guidance |
| `get_threat_landscape` | Ecosystem threat intelligence summary and coordinated disclosure status |
| `security_checklist` | Category-specific security review checklists (financial, communication, filesystem, database, browser, shell) |

#### Runtime Monitoring — EDR for AI Agents (5 Tools)
| Tool | Description |
|---|---|
| `monitor_start` | Starts an HMAC-authenticated session monitor tracking tool calls, file reads, shell commands, and network egress |
| `monitor_event` | Evaluates runtime events against 7 detection rules (sensitive file access, exfiltration endpoints, dangerous shell commands, rapid enumeration, capability escalation, rate limits, and data staging chains) |
| `monitor_end` | Generates a complete session security report with severity breakdown |
| `set_monitor_policy` | Defines per-skill behavioral allow/deny lists and rate limits |
| `get_session_alerts` | Queries real-time security alerts for an active agent session |

---

### 2. [`clawhub-skills/`](clawhub-skills/) — 19 Published OpenClaw Security, Compliance & Operations Skills (7,701 Lines)

Recovered from the public ClawHub / OpenClaw registry (`@trypto1019`), where they have accumulated **10,000+ community downloads** and are indexed in `VoltAgent/awesome-openclaw-skills`:

| Skill | Lines | Category | What It Does |
|---|---:|---|---|
| [`arc-compliance-checker`](clawhub-skills/arc-compliance-checker/) | 919 | Compliance | Policy-based compliance assessment mapped to CIS Controls & OWASP |
| [`arc-skill-scanner`](clawhub-skills/arc-skill-scanner/) | 713 | Security | Static vulnerability & prompt-injection scanner for third-party agent skills |
| [`arc-skill-sandbox`](clawhub-skills/arc-skill-sandbox/) | 532 | Security | Isolated execution sandbox with canary secrets (`sk-fake-sandbox-...`) to catch credential exfiltration at runtime (2,034+ downloads) |
| [`arc-skill-gitops`](clawhub-skills/arc-skill-gitops/) | 469 | DevSecOps | Git-tagged snapshotting, pre-deploy scanner hooks, and 1-command rollback for agent skills |
| [`arc-workflow-orchestrator`](clawhub-skills/arc-workflow-orchestrator/) | 465 | Orchestration | Declarative YAML/JSON multi-skill pipeline runner with conditional logic & audit logs (3,281+ downloads) |
| [`arc-trust-verifier`](clawhub-skills/arc-trust-verifier/) | 418 | Supply Chain | Provenance scoring, SHA-256 content integrity, and signed trust attestations |
| [`arc-compliance-audit`](clawhub-skills/arc-compliance-audit/) | 411 | Compliance | Immutable JSONL audit trail with hash-chain verification for autonomous agent actions (2,067+ downloads) |
| [`arc-wake-state`](clawhub-skills/arc-wake-state/) | 409 | Reliability | Crash-resilient state persistence across context window resets and restarts |
| [`arc-metrics-dashboard`](clawhub-skills/arc-metrics-dashboard/) | 402 | Observability | Zero-dependency operational telemetry (API calls, latency, errors, task completions) |
| [`arc-skill-differ`](clawhub-skills/arc-skill-differ/) | 352 | Supply Chain | Version-to-version diff analyzer flagging newly added shell/network/credential permissions |
| [`arc-skill-health-monitor`](clawhub-skills/arc-skill-health-monitor/) | 350 | Observability | Drift, error-rate, and anomalous behavior monitor for deployed skills |
| [`arc-agent-lifecycle`](clawhub-skills/arc-agent-lifecycle/) | 348 | Governance | End-to-end lifecycle manager for autonomous agents and installed skills |
| [`arc-department-manager`](clawhub-skills/arc-department-manager/) | 329 | Multi-Agent | Organizes sub-agents into specialized departments with task queues & reporting (1,973+ downloads) |
| [`arc-free-worker-dispatch`](clawhub-skills/arc-free-worker-dispatch/) | 324 | Cost Control | Routes sub-agent tasks to zero-cost / low-cost models with fallback chains |
| [`arc-memory-pruner`](clawhub-skills/arc-memory-pruner/) | 318 | Reliability | Automated compaction and pruning of long-running agent memory files |
| [`budget`](clawhub-skills/budget/) | 314 | Cost Control | Ledger and spend-cap enforcement to prevent runaway agent API bills |
| [`arc-warm-wake`](clawhub-skills/arc-warm-wake/) | 307 | Reliability | Ordered identity, memory, and safety-policy hydration on agent startup |
| [`arc-security-audit`](clawhub-skills/arc-security-audit/) | 267 | Security | Full-stack auditor chaining `arc-skill-scanner`, `arc-trust-verifier`, and SHA-256 binary checks (1,000+ downloads) |
| [`arc-security-mcp`](clawhub-skills/arc-security-mcp/) | 54 | Security | Skill wrapper connecting OpenClaw agents to the Arc Security MCP server |

---

## Contact

- **Author**: Travis Vayssie
- **Portfolio Hub**: [github.com/Trypto1019/ai-operator-portfolio](https://github.com/Trypto1019/ai-operator-portfolio)
- **LinkedIn**: [linkedin.com/in/travis-vayssie-4ba7781b9](https://www.linkedin.com/in/travis-vayssie-4ba7781b9)
- **Email**: [travis.vayssie.jobs@gmail.com](mailto:travis.vayssie.jobs@gmail.com)
