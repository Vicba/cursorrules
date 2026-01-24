# Run All Tests and Fix Failures

## Overview
Execute the full test suite and systematically fix any failures, ensuring code quality and functionality.  

## Steps
1. **Run test suite**
   - Execute all tests in the project (unit, integration, e2e as applicable)
   - Capture output and identify failures
   - Note flaky tests versus consistently broken ones

2. **Analyze failures**
   - Categorize by type: flaky, broken, new failures
   - Prioritize fixes based on impact and severity
   - Check if failures are related to recent changes

3. **Fix issues systematically**
   - Start with the most critical failures
   - Fix one issue or failure category at a time
   - Re‑run relevant subset of tests to validate each fix

4. **Final verification**
   - Re‑run the full test suite
   - Ensure no new failures were introduced
   - Update documentation or comments if behavior has changed

## Checklist
- [ ] Full test suite has been executed
- [ ] Failures categorized and prioritized
- [ ] Highest impact failures fixed first
- [ ] Flaky tests investigated or quarantined
- [ ] Final full test run passing

