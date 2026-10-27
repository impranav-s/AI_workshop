# Workshop source notes

Official documentation checked October 25, 2026. These are instructor references for the compact slides. Interfaces, eligibility, and experimental features can vary by installed version and organization policy.

## Setup

- [Copilot in VS Code](https://code.visualstudio.com/docs/copilot/setup): enable the supported integration and sign in to GitHub.
- [Codex CLI](https://learn.chatgpt.com/docs/codex/cli): install using the official instructions, run `codex` in the project, and sign in. [Codex IDE setup](https://learn.chatgpt.com/docs/codex/ide) covers the extension. [Desktop setup](https://learn.chatgpt.com/docs/quickstart) covers the current ChatGPT desktop surface.
- [Claude Code quickstart](https://code.claude.com/docs/en/quickstart): choose the installation method for the operating system, check `claude --version`, run `claude`, and sign in. Terminal, IDE, and desktop access are separate setup routes.
- [GitHub student access](https://docs.github.com/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-for-students): education verification and Copilot activation are separate steps. Teacher eligibility has its own [education guidance](https://docs.github.com/en/education/about-github-education/github-education-for-teachers/about-github-education-for-teachers).

## Harnesses, models, and interfaces (slides 28-30)

A harness manages context, tools, permissions, and session behavior. A model selected within Copilot does not change the harness. VS Code's current Copilot/Local built-in roles are Ask, Agent, and Plan. [Harness selection and built-in agents](https://code.visualstudio.com/docs/agents/run/agent-harnesses).

VS Code can discover supported local external Claude Code/Codex sessions. They may be hidden under the External filter or `chat.agentSessions.showExternal`. This does not establish discovery of arbitrary remote SSH/tmux sessions. Codex continuation can require quitting the other application before Retry because only one writer can control the session. [Session management](https://code.visualstudio.com/docs/agents/run/sessions/manage-sessions).

The OpenAI extension supplies Codex in the editor Chat view. The experimental Agent Host integration also supports the Agents window and has separate settings and account/policy requirements. Do not promise identical UI on all installations. [Integration requirements](https://code.visualstudio.com/docs/agents/run/agent-harnesses).

## Ten useful comparison points

| Feature | Codex | Claude Code | How to use the distinction |
|---|---|---|---|
| Project instructions | `AGENTS.md`, including scoped files | `CLAUDE.md`; recent versions also support an AGENTS.md fallback | Keep project conventions in files the selected harness discovers. |
| Skills | `SKILL.md`; repository `.agents/skills`; `/skills` or `$name` | `SKILL.md`; repository `.claude/skills` | Reuse a workflow; inspect its instructions and dependencies first. |
| Planning | `/plan` | Plan permission mode, including `--permission-mode plan` | Review a proposed approach before implementation. |
| Advisory help | Use a separate reviewer/planning task as supported | `/advisor` is experimental and provider/billing dependent | Reserve extra reasoning or reviewers for tasks that justify the allowance. |
| Response style | Instructions and `/personality` where supported | Named output styles, e.g. `/output-style explanatory` | Style controls explanation; it does not verify research claims. |
| External tools | MCP and approved connectors | MCP and approved connectors | Configure only needed tools; retrieved material is evidence, not instructions. |
| Permissions | Approval policy and sandbox are separate | Permission rules and shell sandbox are separate | Inspect the scope of access before execution; avoid bypass flags. |
| Session continuity | `codex resume`, compaction and supported forks | `--continue`, `--resume`, `/resume` | Keep durable decisions in project files/issues as well as conversation history. |
| Remote access | Supported remote connections; CLI remote control experimental | Remote Control into a running host/process | Remote viewing is not migration of execution into a cloud environment. |
| Parallel work and review | Subagents, worktrees, `/review` | Subagents, worktrees, Git/review workflows | Separate writers, use independent reviewers, and inspect changes before merging. |

Sources: Codex [instructions](https://learn.chatgpt.com/docs/agent-configuration/agents-md), [skills](https://learn.chatgpt.com/docs/build-skills), [planning](https://learn.chatgpt.com/docs/learn/best-practices), [commands](https://learn.chatgpt.com/docs/developer-commands), [MCP](https://learn.chatgpt.com/docs/extend/mcp), [permissions](https://learn.chatgpt.com/docs/agent-approvals-security), [remote connections](https://learn.chatgpt.com/docs/remote-connections), [subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents), [worktrees](https://learn.chatgpt.com/docs/environments/git-worktrees), [GitHub review](https://learn.chatgpt.com/docs/third-party/github).

Claude Code [instructions](https://code.claude.com/docs/en/memory), [skills](https://code.claude.com/docs/en/skills), [workflows](https://code.claude.com/docs/en/common-workflows), [advisor](https://code.claude.com/docs/en/advisor), [output styles](https://code.claude.com/docs/en/output-styles), [MCP](https://code.claude.com/docs/en/mcp), [permissions](https://code.claude.com/docs/en/permissions), [sandboxing](https://code.claude.com/docs/en/sandboxing), [sessions](https://code.claude.com/docs/en/sessions), [Remote Control](https://code.claude.com/docs/en/remote-control), [subagents](https://code.claude.com/docs/en/sub-agents).

Claude's AGENTS.md fallback requires sufficiently recent versions (introduced in 2.1.277 with compatibility fixes in 2.1.281). A project CLAUDE.md takes precedence. An explicit `@AGENTS.md` import is a portable way to share project guidance. Neither provider's instructions guarantee that every request will follow them; inspect the result.

## Instructions and skills (slide 29)

[VS Code instruction discovery](https://code.visualstudio.com/docs/agent-customization/custom-instructions) depends on the harness. Project-level AGENTS.md instructions are not universally read only on demand. [Custom agents](https://code.visualstudio.com/docs/agent-customization/custom-agents) still combine role instructions and tools, with optional model settings.

Matt Pocock's exact skill names are [`grill-me`](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md) and [`grill-with-docs`](https://github.com/mattpocock/skills/blob/main/skills/engineering/grill-with-docs/SKILL.md). The first wraps `grilling` for an interview, normally without writing files. The second is repository-aware glossary/ADR work and depends on both `grilling` and `domain-modeling`. It is not a generic paper-reading skill.

Optional installation routes documented by the [maintainer](https://github.com/mattpocock/skills):

```bash
# Claude Code plugin collection
claude plugin install mattpocock-skills@claude-plugins-official

# Codex plugin collection
codex plugin marketplace add mattpocock/skills
codex plugin add mattpocock-skills@mattpocock

# Alternative: interactively choose editable skills
npx skills@latest add mattpocock/skills
```

Choose a plugin or copied-skill route for each agent to avoid duplicate installation. Preserve dependent skills. Version/platform support varies. These commands are reference instructions; no installation was performed for this revision. No third-party skill files are redistributed in this workshop.

## Git and integrations

- [Git worktrees](https://git-scm.com/docs/git-worktree): multiple working trees share a repository while keeping separate working files and indexes. Worktrees do not isolate external services or shared output paths.
- [Git ignore rules](https://git-scm.com/docs/gitignore): ignore rules affect untracked files; subdirectories may have their own rules.
- [Overleaf Git and GitHub integration](https://docs.overleaf.com/integrations-and-add-ons/git-integration-and-github-synchronization): both are Premium features for Overleaf Cloud. The diagram illustrates the author's chosen collaboration convention, not a requirement imposed by Git.

## Writing (slide 37)

The author-instruction slide draws on Tomas's user-owned `academic-draft-editing`, `econ-write`, and `humanizer` guidance and the instructions he explicitly requested for this workshop. Private skill files, assistant instructions, research drafts, results, and machine details are not included. Scientific claims and exhibits remain the author's responsibility. This slide makes no universal writing-model ranking and includes no detector discussion.

## Verified redesign of slides 15–17 — October 26, 2026

This dated addendum supplies the sources and qualifications for the three redesigned agent slides. The earlier numbered comparison notes describe a previous layout. The current comparison selects harness mechanisms and useful workflows; it makes no model-intelligence or universal performance ranking.

Local versions checked without starting a remote session: Codex CLI **0.164.0** and Claude Code **2.1.311**. Both installed binaries document a `remote-control` command in `--help`; Codex labels its command experimental. No software, plugins, or skills were installed for this revision.

### Slide 15: shared capabilities and selected differences

The shared strip names supported capability categories, not identical configuration, discovery, permissions, or event behavior:

| Capability | Official primary references and scope |
|---|---|
| Project instructions | Codex reads scoped [`AGENTS.md` guidance](https://learn.chatgpt.com/docs/agent-configuration/agents-md). Claude Code loads [`CLAUDE.md` and related guidance](https://code.claude.com/docs/en/memory); recent versions also have a configurable `AGENTS.md` fallback. The slide does not equate their loading rules. |
| Reusable skills | Both use `SKILL.md` workflows/resources: [Codex skills](https://learn.chatgpt.com/docs/build-skills), [Claude Code skills](https://code.claude.com/docs/en/skills). Explicit invocation and relevance-based loading have tool-specific controls. |
| MCP/tools | Both provide configurable MCP connections: [Codex MCP](https://learn.chatgpt.com/docs/extend/mcp), [Claude Code MCP](https://code.claude.com/docs/en/mcp). Available tools depend on configuration and access. |
| Hooks | Both document lifecycle hooks: [Codex hooks](https://learn.chatgpt.com/docs/hooks), [Claude Code hooks](https://code.claude.com/docs/en/hooks). Their event sets and handlers differ. Codex requires review/trust for non-managed hooks. |
| Output guidance | Claude Code provides [named and custom output styles](https://code.claude.com/docs/en/output-styles). Codex supports instructions and [`/personality` when the current model supports it](https://learn.chatgpt.com/docs/developer-commands). The comparison does not claim that these mechanisms are interchangeable. |
| Action controls | Claude Code offers [tool/path rules and permission modes](https://code.claude.com/docs/en/permissions). Codex distinguishes [sandbox scope from approval policy](https://learn.chatgpt.com/docs/agent-approvals-security). These are selected mechanisms, not exclusive capabilities or guarantees about a particular session's policy. |

**Mods is the exact official name.** The [Claude Code mods reference](https://code.claude.com/docs/en/plugins/mods/overview) describes JavaScript/TypeScript event handlers packaged in plugins, which can alter behavior and rendered UI. The CLI requires v2.1.287 or later; the desktop runtime requires v2.1.286. VS Code rendering starts at extension v2.1.299, with v2.1.304 needed for some sessions without feature-flag evaluation. Support differs by surface. The slide's code-maintenance tradeoff is an instructor judgment about creating custom plugin code; users can also install existing mods.

**Remote control needs two distinct qualifications.** [Claude Code Remote Control](https://code.claude.com/docs/en/remote-control) can start from the CLI and continue through a browser or the mobile app while execution stays on the host. It requires eligible subscription authentication and applicable organization permissions; API-key-only and third-party endpoint configurations are excluded. The host/process must remain available.

For Codex, the documented [mobile-to-desktop pairing workflow](https://learn.chatgpt.com/docs/remote-connections) starts in the ChatGPT desktop app on a supported Mac/Windows host, with account, workspace, device and rollout requirements. Separately, the official [CLI reference](https://learn.chatgpt.com/docs/cli/reference) documents experimental `codex remote-control`, including managed-server operation and pairing commands. Therefore the slide explicitly acknowledges CLI remote control; it does not generalize the desktop pairing instructions into a claim that Codex CLI cannot support remote control. Checking command help establishes command availability in the installed version, not account eligibility or a successful connection.

The sole Copilot footer points to an alternative integrated environment with model choice. The [VS Code harness guide](https://code.visualstudio.com/docs/agents/run/agent-harnesses) distinguishes selecting a model from selecting its harness and access surface. A Claude model selected within a Copilot session still uses that session's harness.

### Slide 16: conceptual instruction organization

The diagram describes sources of guidance for one task, not a universal instruction-precedence hierarchy. Project instructions supply enduring context; the task prompt supplies the current request; output requirements may be supplied in that prompt or session configuration. The skills branch feeds the task when invoked or selected as relevant. Actual loading and precedence remain tool-specific, as the instruction, skills, and output-style references above explain.

The two examples, `academic-draft-editing` and `humanizer`, are the author's existing workshop skills. Agents can help install/use skills, but the target tool's supported locations must be checked. For example, current Codex repository discovery uses `.agents/skills`, while Claude Code project skills use `.claude/skills`; neither path is presented as a universal discovery directory. No installation was performed.

### Slide 17: access surfaces

Only Terminal / CLI, IDE Extension, and Desktop remain. The nine useful interface bullets are retained verbatim. Headings and first bullet baselines are aligned, and the former Custom Agents block is removed. Remote access is qualified by a running host and supported access, consistent with the remote-control references above. No agents-panel demonstration or additional harness comparison is introduced.
