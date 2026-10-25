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
