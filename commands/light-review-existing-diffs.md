# Light Review Existing Diffs

## Overview
Perform a quick, lightweight review of your current uncommitted or staged diffs before committing or opening a PR.

## Steps
1. **Gather diffs**
   - Run a diff command (e.g. `git diff` or `git diff --cached`)
   - Focus on the files most relevant to the change
   - Ignore generated or vendor files

2. **Scan for obvious issues**
   - Look for debugging code (logs, `console.log`, `print`, breakpoints)
   - Check for commented‑out blocks that should be removed
   - Ensure no secrets, tokens, or credentials are present

3. **Quick quality pass**
   - Verify naming is clear and consistent
   - Check for small refactors that reduce duplication
   - Ensure functions are not excessively long or doing too much

4. **Safety checks**
   - Confirm important branches, conditions, and edge cases are handled
   - Make sure any risky changes are covered by tests
   - Verify configuration and environment changes are correct

5. **Finalize**
   - Stage any missing files
   - Update or add small tests if easy wins are obvious
   - Proceed to commit or PR preparation workflow (e.g. `/create-pr`)

## Checklist
- [ ] Diffs reviewed for debug code and temporary changes
- [ ] No secrets or sensitive data present
- [ ] Obvious style and clarity issues addressed
- [ ] Risky changes have test coverage
- [ ] Ready to move forward to commit / PR

