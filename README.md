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

Each `.mdc` or `SKILL.md` file is a self-contained rule/skill document designed to be pulled into Cursor as context.

---

## Using these rules/skills in Cursor

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

## Suggested usage patterns

- **When coding**  
  - Open the relevant language/framework rule (e.g. `python.mdc`, `react-native.mdc`, `jest.mdc`).  
  - Reference or pin the matching clean-code rules (`code-quality.mdc`, `documentation.mdc`, `pr-template.mdc`) while you work.

- **When doing marketing work**  
  - Open the closest `SKILL.md` to what you’re doing (e.g. `page-cro`, `pricing-strategy`, `email-sequence`).  
  - Use it as a checklist / prompt guide inside Cursor while drafting or reviewing work.

