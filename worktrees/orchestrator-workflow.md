# Orchestrator Workflow: Planning → Orchestrator → Work Agents → Test → Review

This workflow demonstrates a structured multi-agent approach for complex features.

## Workflow Pattern

```
Planning Agent → Orchestrator Agent → [Work Agents (parallel)] → Test Agent → Review Agent
```

## Step-by-Step Implementation

### Step 1: Planning Agent

**Prompt for Composer:**
```
You are the Planning Agent. Analyze the following feature request and create a comprehensive plan:

[Feature Description]

Create a structured plan that includes:
1. Feature breakdown into components
2. Dependencies between components
3. Required agents and their roles:
   - Backend Agent (API, database, business logic)
   - Frontend Agent (UI components, user interactions)
   - Integration Agent (connecting frontend to backend)
4. Success criteria
5. Testing requirements

Output the plan to agents/PLAN.md
```

**Expected Output:** `agents/PLAN.md` with structured breakdown

---

### Step 2: Orchestrator Agent

**Prompt for Composer:**
```
You are the Orchestrator Agent. Review the plan in agents/PLAN.md and:

1. Assign tasks to specialized work agents based on the plan
2. Set up the coordination board (agents/COORDINATION_BOARD.md) with:
   - Goals from the plan
   - Agent roles and assignments
   - Dependencies and hand-off points
3. Determine which tasks can run in parallel
4. Create worktree assignments for parallel execution

Update agents/COORDINATION_BOARD.md with the orchestration plan.
```

**Expected Output:** Updated `agents/COORDINATION_BOARD.md` with agent assignments

---

### Step 3: Work Agents (Parallel Execution)

**Launch multiple agents simultaneously in worktrees:**

#### Backend Agent
```
You are the Backend Agent. Working from agents/COORDINATION_BOARD.md:

1. Implement the backend components assigned to you
2. Create API endpoints, database models, and business logic
3. Update COORDINATION_BOARD.md with your changes:
   - Files changed
   - Summary of implementation
   - Status: Complete/In Progress/Blocked
4. Mark "Next Owner" when ready for integration

Work in your assigned worktree.
```

#### Frontend Agent
```
You are the Frontend Agent. Working from agents/COORDINATION_BOARD.md:

1. Implement the frontend components assigned to you
2. Create UI components, pages, and user interactions
3. Update COORDINATION_BOARD.md with your changes
4. Mark "Next Owner" when ready for integration

Work in your assigned worktree.
```

#### Integration Agent (runs after Backend + Frontend)
```
You are the Integration Agent. Working from agents/COORDINATION_BOARD.md:

1. Review changes from Backend and Frontend agents
2. Connect frontend to backend APIs
3. Ensure data flow works end-to-end
4. Update COORDINATION_BOARD.md with integration status

Work in your assigned worktree.
```

**How to run in parallel:**
- In Composer, select multiple models or use the multi-agent interface
- Each agent gets its own worktree automatically
- They can work simultaneously without conflicts

---

### Step 4: Test Agent

**Prompt (runs after all work agents complete):**
```
You are the Test Agent. Review agents/COORDINATION_BOARD.md and:

1. Run the full test suite
2. Write additional tests for new functionality
3. Verify all components work together
4. Check edge cases and error handling
5. Update COORDINATION_BOARD.md with:
   - Test results (passed/failed)
   - Coverage report
   - Any issues found

If tests fail, identify root causes and update the board.
```

**Expected Output:** Test results and status in `agents/COORDINATION_BOARD.md`

---

### Step 5: Review Agent

**Final prompt:**
```
You are the Review Agent. Conduct a final review:

1. Review agents/COORDINATION_BOARD.md for complete status
2. Compare all agent outputs and diffs
3. Validate against the original plan (agents/PLAN.md)
4. Check code quality, security, and best practices
5. Run final tests
6. Create a summary report with:
   - What was completed
   - What needs attention
   - Recommendations for merging

Output review to agents/REVIEW.md
```

**Expected Output:** `agents/REVIEW.md` with final assessment

---

## Coordination Board Structure

The `agents/COORDINATION_BOARD.md` should track:

```markdown
## Goals
- [Goal 1 from plan]
- [Goal 2 from plan]

## Agent Roles
| Role | Status | Notes |
|------|--------|-------|
| Planning Agent | ✅ Complete | Plan created |
| Orchestrator | ✅ Complete | Tasks assigned |
| Backend Agent | 🚧 In Progress | Implementing API |
| Frontend Agent | 🚧 In Progress | Building UI |
| Integration Agent | ⏸️ Waiting | Waiting for Backend + Frontend |
| Test Agent | ⏸️ Pending | Waiting for integration |
| Review Agent | ⏸️ Pending | Final step |

## Changes
[Each agent updates this section]

## Next Owner
Current: Integration Agent
Next: Test Agent
```

---

## Complete Workflow Prompt (All-in-One)

You can also run this as a single orchestrator prompt:

```
Act as an orchestrator for this feature: [Feature Description]

Execute this workflow:
1. Planning Agent: Create plan → agents/PLAN.md
2. Orchestrator: Assign tasks → agents/COORDINATION_BOARD.md
3. Launch parallel work agents (Backend, Frontend) in separate worktrees
4. Integration Agent: Connect components (after work agents)
5. Test Agent: Run tests and verify
6. Review Agent: Final review → agents/REVIEW.md

Each agent should update agents/COORDINATION_BOARD.md with status.
Use worktrees for parallel execution where possible.
```

---

## Tips

- **Sequential dependencies**: Use COORDINATION_BOARD.md to track when agents can start (e.g., Integration waits for Backend + Frontend)
- **Parallel execution**: Backend and Frontend can run simultaneously in separate worktrees
- **Review gates**: Review Agent should validate everything before you apply changes
- **Human approval**: Review the Review Agent's output before applying any changes to your main branch
