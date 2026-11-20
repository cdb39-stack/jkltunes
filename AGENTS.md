# Project instructions

## Project proposal

- **Application name:** JKL Tunes
- **Description:** A personal music library for organizing and playing music the user is authorized to use, with playlists and editable track details.
- **Group members:** Christopher Bennett (confirm whether there are additional group members).
- **Intended users and current alternatives:** Music listeners who want to organize and play music they already have permission to use, without ads in their personal library. Current alternatives were not specified.
- **Main user flow:** View the library and playlists; add a track; play it; edit its title, cover reference, or playlist membership.
- **Minimum version:** A responsive music library that organizes and plays user-provided tracks. The assignment prohibits file uploads, so the storage/upload portion needs an instructor-approved, compliant design before implementation. Ensure the required Express route still receives a request and returns a response.
- **Server routes:** Proposed audio and cover-image upload routes conflict with the assignment's no-file-uploads rule. Redesign routes around validated metadata or another instructor-approved approach before implementation.
- **Additional features:** Playlist import from a streaming service; automatic track metadata and cover lookup. Do not download audio from third-party services unless the source explicitly authorizes it and the method complies with its terms and the assignment.
- **Advanced features:** Not assigned; confirm group size and one feature per member.
- **Main screen sketch:** Not supplied yet.
- **Main technical risk and fallback:** Browser playback compatibility. Test supported audio formats; show a clear unsupported-format error and let the user select another authorized file. Do not search for or download a replacement recording without authorization.

## Required architecture and constraints

- The Express server entry point is `server.js` in the repository root.
- Static front-end files live in `public/`.
- Use plain HTML, CSS, and browser JavaScript. Do not add a front-end framework.
- Reject empty, oversized, and malformed user input on the server. The interface must show useful error messages.
- Read keys, passwords, and other secrets from environment variables. Never put secrets in source control; `.env` must be excluded by `.gitignore`.
- Do not add file uploads, sensitive personal data, paid APIs, or paid services. Images, if needed, are referenced by URL.
- Treat user-provided audio as content the user must have rights to use. Do not build functionality that retrieves copyrighted recordings from YouTube or other services without authorization. Prefer metadata lookup and user-authorized source links; never bypass service restrictions.
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
