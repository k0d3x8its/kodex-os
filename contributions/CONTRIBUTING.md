# Contributing to Kodex OS

Kodex OS is a personal knowledge management system built on Field Notes, Notion, Obsidian,
and a layered information architecture. Contributions are welcome.

## What You Can Contribute
- Improvements to the Kodex Stack architecture
- New templates, views, or ideas
- Documentation and guides
- Bug reports or structural inconsistencies you spot

## Reporting Issues
Open an issue with:
- Which layer is affected (Layer 1 = LLM Wiki, Layer 2 = Notion/Project Intelligence, etc.)
- What the inconsistency or issue is
- What you expected vs. what you found

## Suggesting Changes
Open an issue labeled `enhancement` before making changes.
Describe the problem the change solves, not just what you want to add.

## Submitting Changes
1. Fork the repo
2. Branch: `git checkout -b feature/your-feature-name`
3. Commit clearly: `git commit -m "fix: corrected layer ordering in Kodex Stack"`
4. Open a PR against `main`

## Principles
Changes should respect the core design rule of Kodex OS:
**Layer order is defined by dependency, not importance.**
If your change affects layer numbering or data flow, justify it explicitly in the PR.

## Licensing
By submitting a pull request, you agree your contributions will be
licensed under the Apache License 2.0 — the same license covering this project.
