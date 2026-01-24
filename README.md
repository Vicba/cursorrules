## cursorrules
Personal library of Cursor rules and skills for coding and marketing work.

This repo is meant to be added as a rules/skills source for Cursor so you can quickly load:
- **Coding rules** (clean code, frameworks, languages)
- **Marketing skills** (CRO, copywriting, launch strategy, etc.)

---

## Structure

- **`rules/clean-code`**: General engineering practices  
  - Code quality, documentation, PR templates, code pairing, consistency, gitflow
- **`rules/frameworks`**: Framework-specific rules  
  - `react`, `react-native`, `nextjs`, `node-express`, `fastapi`, `jest`, `tailwind`
- **`rules/languages`**: Language-specific rules  
  - `python`, `typescript`, `rust`
- **`skills/marketing`**: Marketing skills, each in its own folder  
  - `page-cro`, `signup-flow-cro`, `copywriting`, `email-sequence`, `seo-audit`, `launch-strategy`, `paid-ads`, `programmatic-seo`, and more.
- **`commands`**: Ready‑made Cursor custom commands you can drop into your projects  
  - `address-github-pr-comments.md`
  - `code-review-checklist.md`
  - `create-pr.md`
  - `light-review-existing-diffs.md`
  - `onboard-new-developer.md`
  - `run-all-tests-and-fix.md`
  - `security-audit.md`
  - `setup-new-feature.md`
- **`subagents`**: Specialized AI subagents for task-specific workflows  
  - `verifier.md` - Validates completed work
  - `debugger.md` - Debugging specialist
  - `test-runner.md` - Test automation expert
  - `security-auditor.md` - Security specialist
  - `code-reviewer.md` - Code review specialist
- **`.cursor/worktrees-examples`**: Worktree configurations for parallel agent execution  
  - `worktrees-testing.json` - Testing/verification setup
  - `worktrees-review.json` - Code review/audit setup
  - `worktrees-feature.json` - Feature development setup
  - `worktrees-orchestrator.json` - Orchestrator multi-agent workflow setup
  - `COORDINATION_BOARD.md` - Template for agent coordination

Each `.mdc`, `SKILL.md`, command `.md`, subagent `.md`, or worktree `.json` file is a self-contained rule/skill/workflow document designed to be pulled into Cursor as context.

---

## Rules

Use the files under `rules/` as live coding guides while you work in Cursor:

- Open the relevant language/framework rule (e.g. `python.mdc`, `react-native.mdc`, `jest.mdc`).  
- Reference or pin the matching clean-code rules (`code-quality.mdc`, `documentation.mdc`, `pr-template.mdc`) while you work.

---

## Skills

- **As a local rules repo**
  - Add this folder as a project in Cursor.
  - Open any `.mdc` or `SKILL.md` file and pin it or reference it when prompting.

- **As a shared rules/skills source (via `add-skill`)**
  - This repo is compatible with the `add-skill` style workflows (e.g. `coreyhaines31/marketingskills`).

### Install all marketing skills

```bash
npx add-skill coreyhaines31/marketingskills
```

### Install specific marketing skills

```bash
npx add-skill coreyhaines31/marketingskills --skill page-cro copywriting
```

### List available marketing skills

```bash
npx add-skill coreyhaines31/marketingskills --list
```

---

## Commands

### Using the Cursor commands

These markdown files in `commands/` are designed to be used as [Cursor custom commands](https://cursor.com/docs/context/commands).

- **Add to a specific project**
  - In that project, create a `.cursor/commands` directory if it doesn’t exist.
  - Copy any `.md` files from this repo’s `commands/` folder into that `.cursor/commands` directory.
  - In Cursor chat for that project, type `/` and you should see them (e.g. `/create-pr`, `/code-review-checklist`).

- **Use as global commands**
  - Copy the `.md` files from `commands/` into `~/.cursor/commands`.
  - They will be available across all your projects when you type `/` in chat.

Each command file documents its own workflow (code review, security audit, running tests, onboarding, etc.) and acts as a reusable checklist you can quickly trigger inside Cursor.

### Command reference

| Command file                       | Slash command           | What it’s for / how to use it                                                                 |
|------------------------------------|-------------------------|------------------------------------------------------------------------------------------------|
| `address-github-pr-comments.md`    | `/address-github-pr-comments` | Guide to systematically review and resolve GitHub PR comments before re‑requesting review.     |
| `code-review-checklist.md`         | `/code-review-checklist`      | Run through a structured checklist while reviewing a PR for quality, security, and clarity.   |
| `create-pr.md`                     | `/create-pr`                  | Step through preparing a clean branch and writing a solid PR description before opening a PR. |
| `light-review-existing-diffs.md`   | `/light-review-existing-diffs`| Do a quick pass over your current `git diff` to catch obvious issues before committing.       |
| `onboard-new-developer.md`         | `/onboard-new-developer`      | Use as a checklist when onboarding a new engineer to the repo and tooling.                    |
| `run-all-tests-and-fix.md`         | `/run-all-tests-and-fix`      | Run the full test suite and walk through fixing and re‑running until everything is green.     |
| `security-audit.md`                | `/security-audit`             | Perform a lightweight security audit of dependencies, code, and infra settings.               |
| `setup-new-feature.md`             | `/setup-new-feature`          | Plan and scaffold a new feature from requirements through initial architecture and setup.     |

---

## Subagents

### Using the Cursor subagents

These markdown files in `subagents/` are designed to be used as [Cursor subagents](https://cursor.com/docs/context/subagents). Subagents are specialized AI assistants that Cursor's agent can delegate tasks to, each operating in its own context window.

- **Add to a specific project**
  - In that project, create a `.cursor/agents` directory if it doesn't exist.
  - Copy any `.md` files from this repo's `subagents/` folder into that `.cursor/agents` directory.
  - Agent will automatically use them when appropriate, or you can invoke them explicitly with `/name` syntax.

- **Use as global subagents**
  - Copy the `.md` files from `subagents/` into `~/.cursor/agents`.
  - They will be available across all your projects.

Each subagent has a focused responsibility and can run in parallel with other subagents for maximum efficiency. Subagents provide context isolation, allowing long-running tasks to not consume space in your main conversation.

### Subagent reference

| Subagent file              | Name                    | What it's for / when to use it                                                                 |
|----------------------------|-------------------------|------------------------------------------------------------------------------------------------|
| `verifier.md`              | `/verifier`             | Validates that completed work actually functions. Use after tasks are marked done.            |
| `debugger.md`              | `/debugger`             | Root cause analysis for errors and test failures. Use when encountering issues.                |
| `test-runner.md`           | `/test-runner`          | Runs tests proactively and fixes failures. Use when making code changes.                      |
| `security-auditor.md`      | `/security-auditor`     | Security vulnerability audit. Use when implementing auth, payments, or handling sensitive data. |
| `code-reviewer.md`        | `/code-reviewer`        | Thorough code review for quality and best practices. Use when reviewing pull requests.         |

---

## Worktrees

### Using Cursor worktrees for parallel agent execution

Worktrees allow you to run multiple agents in parallel, each in their own isolated Git worktree. This enables parallel execution, Best-of-N model comparisons, and complex orchestrator-style workflows. See the [Cursor worktrees documentation](https://cursor.com/docs/configuration/worktrees) for full details.

- **Add to a specific project**
  - Copy any `.json` file from this repo's `.cursor/worktrees-examples/` folder into your project's `.cursor/worktrees.json`.
  - Customize the setup commands for your project's needs.
  - When you run parallel agents in Cursor, they will use this configuration.

- **What worktrees enable**
  - Run multiple agents simultaneously without conflicts
  - Compare outputs from different models (Best-of-N)
  - Isolate long-running tasks from your main workspace
  - Orchestrate complex multi-agent workflows

### Worktree configuration examples

Four example configurations are available in `.cursor/worktrees-examples/`:

| Configuration file | Use case | Best for |
|-------------------|----------|----------|
| `worktrees-testing.json` | Testing/Verification | Parallel test execution, validation tasks, Best-of-N test approaches |
| `worktrees-review.json` | Code Review/Audit | Security audits, code reviews, quality checks in parallel |
| `worktrees-feature.json` | Feature Development | Developing new features while other work continues, refactoring, experimental work |
| `worktrees-orchestrator.json` | Orchestrator Multi-Agent | Complex full-stack features requiring coordination between multiple specialized agents |

### Step-by-step example: Using the testing worktree

Here's a complete walkthrough of using the testing worktree configuration:

#### Step 1: Set up the worktree configuration

1. In your project root, create the `.cursor` directory if it doesn't exist:
   ```bash
   mkdir -p .cursor
   ```

2. Copy the testing worktree configuration:
   ```bash
   cp /path/to/cursorrules/.cursor/worktrees-examples/worktrees-testing.json .cursor/worktrees.json
   ```

3. (Optional) Customize the setup commands in `.cursor/worktrees.json` for your project. For example, if you use Python instead of Node.js:
   ```json
   {
     "setup-worktree-unix": [
       "python -m venv venv",
       "source venv/bin/activate && pip install -r requirements.txt",
       "cp $ROOT_WORKTREE_PATH/.env .env 2>/dev/null || true"
     ]
   }
   ```

#### Step 2: Run a parallel agent with the worktree

1. Open Cursor in your project
2. Open Composer (Cmd/Ctrl + I) or use the Agent chat
3. In the model selector, you'll see options for parallel execution. Select "Run in worktree" or choose multiple models for Best-of-N
4. Enter your prompt, for example:
   ```
   Run all tests and fix any failures. Use the test-runner subagent.
   ```
5. Click to start the agent. Cursor will:
   - Create a new Git worktree automatically
   - Run the setup commands from `worktrees.json` (install dependencies, copy env files, etc.)
   - Execute your agent task in the isolated worktree

#### Step 3: Monitor progress

- The agent runs in the background worktree, so you can continue working in your main workspace
- Watch the agent's progress in the Cursor interface
- The agent can run tests, make fixes, and iterate without affecting your main branch

#### Step 4: Review and apply results

1. Once the agent completes, you'll see a card showing the changes made
2. Review the diff to see what was changed in the worktree
3. Click the **"Apply"** button to merge the changes into your main working tree
4. Cursor will attempt a clean merge. If there are conflicts, you'll see options to:
   - Resolve conflicts manually
   - Full overwrite (replace files entirely)
   - Merge with conflict resolution UI

#### Example: Best-of-N testing approach

To compare how different models handle the same test task:

1. In Composer, select multiple models (e.g., Claude Sonnet + GPT-4)
2. Enter the same prompt: `"Fix all failing tests in the test suite"`
3. Cursor creates separate worktrees for each model
4. Compare the results side-by-side:
   - Which model fixed more tests?
   - Which approach was cleaner?
   - Which solution is more maintainable?
5. Apply the best result to your main branch

#### What happens behind the scenes

When you run an agent with worktrees enabled:

1. **Worktree creation**: Cursor runs `git worktree add` to create an isolated branch
2. **Setup execution**: Runs your `worktrees.json` setup commands in the new worktree
3. **Agent execution**: The agent works in isolation, making changes only in the worktree
4. **Result merging**: When you click "Apply", Cursor merges the worktree changes back to your main branch

You can see all worktrees with:
```bash
git worktree list
```

Cursor automatically cleans up old worktrees (default: keeps last 20, removes oldest when limit exceeded).

### Orchestrator-style workflows

Cursor 2.0's Composer enables orchestrator-style workflows by planning tasks, spinning up multiple specialized agents (up to 8 in parallel git worktrees), and incorporating a final review step. This approach is ideal for complex features that require coordination between different specialists.

#### Setup Orchestrator in Composer

1. Open Composer (Cmd/Ctrl + I) and prompt it to act as an orchestrator
2. Define roles like "Planner, Backend Agent, Frontend Agent, Tester" with a structured plan including dependencies
3. Composer creates the plan, assigns sub-tasks to agents, and executes in sequence or parallel via worktrees

#### Spin Up Agents

Use role-based prompts in the same session (e.g., "You are Backend Agent: implement API per plan") or launch parallel agents in the multi-agent interface for independent work. Agents communicate via shared markdown boards (e.g., `agents/COORDINATION_BOARD.md`) for updates and hand-offs like "Goal → Changes → Next Owner."

#### Final Reviewer

After agents complete phases, trigger a "Reviewer Agent" or synthesis session: prompt Composer to compare outputs, validate against criteria, run tests, and merge best diffs. Review gates ensure human approval of changes before finalizing.

#### Example Orchestrator Workflow

| Step | Action | Tools/Agents |
|------|--------|-------------|
| 1. Plan | "Create plan for full-stack auth feature with roles" | Orchestrator (Composer) |
| 2. Parallel | Launch DB, API, UI agents simultaneously | Multi-agent worktrees (up to 8 parallel) |
| 3. Coordinate | Agents post to `COORDINATION_BOARD.md` | Shared coordination boards |
| 4. Review | "Compare agent outputs, test, merge best" | Reviewer prompt |

This human-in-the-loop approach keeps reasoning visible and safe. The coordination board template (`COORDINATION_BOARD.md`) is included in the worktrees-examples directory for agent communication.

#### Complete Orchestrator Workflow Pattern

For a structured **Planning → Orchestrator → Work Agents → Test → Review** workflow, see the detailed guide in `worktrees-examples/orchestrator-workflow.md`. This guide includes:

- Step-by-step prompts for each agent role
- How to run agents in parallel using worktrees
- Coordination board management
- Complete all-in-one orchestrator prompt

The workflow pattern:
```
Planning Agent → Orchestrator Agent → [Work Agents (parallel)] → Test Agent → Review Agent
```

---

## MCP

If you also use MCP servers with Cursor, you can browse and install them from the [MCP Directory](https://cursor.com/docs/context/mcp/directory).
