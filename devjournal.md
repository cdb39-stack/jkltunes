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

## 2026-11-19 — JKL Tunes proposal and content boundaries

### Context

Christopher Bennett proposed JKL Tunes as a personal music library: view tracks and playlists, add music, play tracks, and edit track details such as title, cover art, and playlist membership. Proposed additional features are importing a playlist from a streaming service and automatically identifying track metadata and cover art. The stated technical risk is playback incompatibility. The proposal also mentions using `yt-dlp` to populate the library from YouTube.

### Decisions

- Record JKL Tunes as the application name and Christopher Bennett as a group member; the group size still needs confirmation.
- Frame the intended use as organizing and playing music the user is authorized to use. This makes the project about a personal library rather than a way to bypass ads or payment for third-party recordings.
- Do not plan a YouTube audio downloader. `yt-dlp` could retrieve recordings without rights or in ways restricted by the source service. The project should not retrieve copyrighted audio absent explicit authorization and should respect service terms. Metadata lookup or links to authorized sources are safer possible directions for the advanced feature.
- Do not implement audio or image upload routes as currently described until the assignment conflict is resolved: its supplied requirements explicitly say “No file uploads.” The current route idea would receive files, so the proposal needs an instructor-approved adjustment or a design that uses permitted inputs.
- Use image URLs for cover art if the assignment's no-upload rule remains in force.
- Address playback failure by validating format and showing a clear error, then letting the user choose another authorized file. Searching the internet for a replacement copy is not an appropriate fallback without rights to retrieve it.

### Alternatives considered

- **Use `yt-dlp` to populate tracks from YouTube:** not selected because the idea does not establish authorization to download those recordings or compliance with YouTube's terms. This is also outside the assignment's stated no-file-upload model if downloaded files are uploaded to the app.
- **Keep the proposed file-receiving routes unchanged:** deferred because they conflict directly with the assignment's no-file-uploads constraint.
- **Replace a failed track with a copy found online:** not selected because availability online does not establish permission to download or redistribute it.

### Tradeoffs / consequences

- The intended private-library experience remains, but persistent server-side audio storage and upload-based import are not implementation decisions yet.
- The required Express route can be designed around validated metadata or another instructor-approved interaction, preserving the server requirement without prematurely violating the upload restriction.
- Playlist import should be scoped to permitted playlist metadata and authorized sources unless the instructor approves a different approach.

### Open questions

- Is Christopher the only group member? Which advanced feature(s) are assigned?
- Does the instructor allow user-selected audio to be played locally in the browser, even though server uploads are prohibited?
- What server interaction will satisfy the Express-route requirement while respecting the no-upload rule?
- Which streaming services and metadata sources, if any, are allowed for playlist import and cover lookup?
- What should the main screen sketch and exact minimum scope be?
