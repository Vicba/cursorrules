# Create PR

## Overview
Create a well-structured pull request with proper description, labels, and reviewers.  

## Steps
1. **Prepare branch**
   - Ensure all changes are committed
   - Rebase or merge to ensure branch is up to date with the target branch (e.g. `main` or `develop`)
   - Push branch to remote and verify CI starts (if applicable)

2. **Write PR description**
   - Summarize changes clearly in 2–4 sentences
   - Include context and motivation (the problem and the solution)
   - List any breaking changes or migrations
   - Add screenshots or GIFs for UI changes

3. **Set up PR**
   - Use a descriptive, consistent title (e.g. prefix with ticket ID)
   - Apply appropriate labels (feature, bugfix, cleanup, etc.)
   - Assign reviewers and request review
   - Link related issues or tickets

## PR Checklist
- [ ] Branch is up to date with target
- [ ] All tests passing locally
- [ ] CI pipeline is green or in progress
- [ ] Description is clear and complete
- [ ] Breaking changes are clearly called out
- [ ] Reviewers and labels are set

