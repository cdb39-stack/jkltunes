# Project instructions

## Project proposal

- **Application name:** jkltunes (working repository name; confirm the approved application name)
- **Description:** To be filled in after the group’s idea is approved.
- **Group members:** To be completed by the group.
- **Intended users and current alternatives:** To be defined.
- **Main user flow:** To be defined.
- **Minimum version:** A responsive, interactive front end that sends a request to an Express route, shows the response, and handles invalid input; deployed publicly on Vercel.
- **Server routes:** To be specified with the proposal and implementation.
- **Additional and advanced features:** To be prioritized and assigned per group member.
- **Main screen sketch:** To be added after the interface is proposed.
- **Main technical risk and fallback:** To be identified with the proposal.

## Required architecture and constraints

- The Express server entry point is `server.js` in the repository root.
- Static front-end files live in `public/`.
- Use plain HTML, CSS, and browser JavaScript. Do not add a front-end framework.
- Reject empty, oversized, and malformed user input on the server. The interface must show useful error messages.
- Read keys, passwords, and other secrets from environment variables. Never put secrets in source control; `.env` must be excluded by `.gitignore`.
- Do not add file uploads, sensitive personal data, paid APIs, or paid services. Images, if needed, are referenced by URL.
- Use only free service plans and never enter a credit card for this project.
- Any database connection string must be read from `process.env.DATABASE_URL`; parameterize all SQL.
- If accounts are approved and implemented, hash passwords with bcrypt and store sessions in the database, not server memory.
- Every group member should be able to explain all project code.

## Build and verification workflow

1. Establish and verify deployment on Vercel, including redeploy-on-push from GitHub.
2. Implement and verify the Express route on the deployed site.
3. Implement and verify the core application features.
4. Implement and verify the assigned advanced features.
5. Check all pages at phone and laptop sizes. Manually verify behavior on the deployed site. Codex cannot access the Vercel URL; when a deployed check is needed, ask the user to provide browser console errors and Vercel logs.

Keep `TESTING.md` current with at least 12 deployed-site test cases. Each case needs an ID, item under test, steps, expected result, and actual result. Cover every form and input with valid and invalid data, every route with valid and invalid data, every page at phone size, and each advanced feature. Do not claim a test was run unless it was actually performed.

## Git and project journal

- Keep `devjournal.md` current as work proceeds. Record design and implementation decisions, alternatives considered and not selected (with reasons where known), relevant tradeoffs, and unresolved questions. Write enough context that a new contributor can understand why the project is built as it is.
- At the end of each completed task, commit the work and push it to the configured GitHub remote when the working tree is in a coherent state. Prefer small, meaningful commits and push after each task or coherent milestone so GitHub and Vercel stay current. Do not push secrets or unrelated user changes.
- Update `README.md` with the application description, group members, deployed URL, and local run instructions as those details become known.
- For the individual report, keep track of three useful Codex prompts and one Codex error, including how it was detected. Each student writes their own report text.
