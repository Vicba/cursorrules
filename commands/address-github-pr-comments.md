# Address GitHub PR Comments

## Overview
Systematic workflow to review and address all comments on an existing GitHub pull request.

## Steps
1. **Review context**
   - Open the PR and read the description and latest commits
   - Skim through the conversation to understand overall feedback
   - Note any high‑level requested changes or decisions

2. **Triage comments**
   - Filter to "Unresolved" comments
   - Group comments by type: bugs, style, architecture, documentation, tests
   - Identify any blocking issues that must be resolved before merge

3. **Plan updates**
   - Decide which comments can be addressed together in a single change
   - Note any comments that require clarification or stakeholder input
   - For larger refactors, outline a small sequence of commits

4. **Implement fixes**
   - Address one logical group of comments at a time
   - Keep commits focused and well‑described
   - Update or add tests where behavior changes

5. **Respond in PR**
   - For each addressed comment:
     - Mark it as resolved (if appropriate)
     - Add a short note describing what changed or why you chose an alternative
   - Ask follow‑up questions where the request is unclear

6. **Finalize**
   - Re‑run relevant tests and linters
   - Push changes and ensure CI is green
   - Leave a summary comment describing the scope of your updates

## Checklist
- [ ] All "Unresolved" comments have been reviewed
- [ ] Blocking issues are fully addressed
- [ ] Code changes are grouped into coherent commits
- [ ] Tests updated/added where necessary
- [ ] Each comment has a clear response or resolution
- [ ] CI is green and PR is ready for another review

