# ghc-ralph-cli-demo

> ⚠️ **This repository is archived.** It is preserved for reference purposes and is no longer actively maintained.

🤖 Demonstration repository for [`ghcralph`](https://www.npmjs.com/package/ghcralph) — a GitHub Copilot-powered CLI for running autonomous agentic coding loops using the **Ralph Wiggum pattern**.

## What is this?

This repository was created to demonstrate how `ghcralph` works end-to-end. It contains:

- A **sample implementation plan** (`PLAN.md`) describing a task for the agent to execute: implementing a `calculator.sh` bash script with full arithmetic support, input validation, and error handling.
- A **`ghcralph` configuration file** (`.ghcralph/config.json`) defining how the agent should run (model, iteration limits, commit strategy, etc.).
- A **dev container** (`.devcontainer/devcontainer.json`) to provide a ready-to-use environment with `ghcralph`, the GitHub CLI, and GitHub Copilot pre-installed.

## What is the Ralph Wiggum pattern?

The Ralph Wiggum pattern is an agentic loop approach where the CLI autonomously breaks down a task plan into small steps and executes them iteratively — asking at each step "Can I do it?" — until all tasks are complete or the iteration limit is reached.

## Repository structure

```
.
├── .devcontainer/
│   └── devcontainer.json   # Dev container configuration (Node.js + TypeScript + ghcralph)
├── .ghcralph/
│   └── config.json         # ghcralph CLI configuration
├── PLAN.md                 # Demo task: calculator bash script implementation plan
├── LICENSE                 # MIT License
└── README.md
```

## Configuration snapshot

The `.ghcralph/config.json` used in this demo:

```json
{
  "planSource": "local",
  "maxIterations": 10,
  "maxTokens": 100000,
  "defaultModel": "claude-sonnet-4.5",
  "autoCommit": true,
  "branchPrefix": "ghcralph/",
  "maxRetriesPerTask": 2,
  "autoPush": false,
  "pushStrategy": "per-task",
  "progressVerbosity": "standard"
}
```

## Getting started (archived reference)

> This repo is archived. The instructions below are preserved for historical reference.

1. Open this repository in a GitHub Codespace or a local dev container — the environment will automatically install `ghcralph`.
2. Review or modify `PLAN.md` with the task you want the agent to execute.
3. Run the CLI:
   ```bash
   ghcralph run
   ```
4. The agent will autonomously work through the plan, committing progress along the way on a branch prefixed with `ghcralph/`.

## Related

- [`ghcralph` on npm](https://www.npmjs.com/package/ghcralph)

## License

[MIT](LICENSE)
