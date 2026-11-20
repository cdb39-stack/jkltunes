# Development journal

This journal records the reasoning behind the project as it takes shape. Entries should capture decisions, alternatives considered (including approaches not selected), reasons and tradeoffs, implementation context, and questions that remain open. Add dated entries as decisions are made; do not rewrite history silently.

## 2026-11-19 — Project setup

### Context

The repository is named `jkltunes`, contains only a minimal `README.md`, and is connected to the GitHub remote `cdb39-stack/jkltunes`. The supplied assignment brief requires a plain HTML/CSS/JavaScript front end, an Express server rooted at `server.js`, public Vercel deployment, input validation, responsive behavior, and project documentation.

### Decisions

- Use the assignment’s required architecture and constraints as project-level instructions in `AGENTS.md` so future contributors and coding agents have one shared reference.
- Keep the product proposal fields explicitly pending. The brief describes the assignment but does not say what jkltunes does, who its users are, or who is in the group; guessing would create false project requirements.
- Create this journal before implementation and continue recording choices as they are made, including alternatives that are considered and rejected.
- Commit and push coherent work after each task or milestone, as required by the assignment and the project request. This keeps the remote repository and Vercel’s push-triggered deployment current without making a push for every tiny edit.
- Follow the prescribed delivery order: deployment, server route, core features, then advanced features. Verify each stage on the deployed site before advancing.

### Alternatives considered

- **Invent a product proposal from the repository name:** not selected because `jkltunes` alone does not establish an approved idea, intended users, features, or group responsibilities.
- **Wait to create project guidance until the application is selected:** not selected because the assignment already supplies important architecture, security, deployment, and documentation rules that should guide the first implementation work.
- **Push after every individual file edit:** not selected; instead, push each coherent task or milestone to keep history reviewable while still syncing frequently.

### Open questions

- What is the approved application idea and one-sentence description?
- Who are the group members, and which advanced feature belongs to each person?
- What are the planned user flow, routes, screen sketch, and main technical risk/fallback?
- What is the Vercel deployment URL?

## Journal entry template

### YYYY-MM-DD — Short decision title

**Context:** What prompted the decision?

**Decision:** What was chosen, and why?

**Alternatives considered:** What else was considered and why was it not selected?

**Tradeoffs / consequences:** What does the choice enable or make harder?

**Open questions:** What still needs an answer?
