CONTRIBUTING.md 
This document outlines the development standards for the Industry Experience Project (S1 2026). Our goal is to ensure the system remains accessible, secure, and reliable for our target demographic (older adults).

1. Development Workflow
Since we are a two-developer team, we use a Peer-Review Workflow:

Branching: Create a new branch for every feature (feature/navigation, feature/social-hub).

Pull Requests (PRs): No code is merged into main without a review from the other developer.

Commit Messages: Use clear, imperative titles (e.g., feat: add voice-guided navigation logic).

2. Coding Standards (Technical Quality)
To maintain code health, we adhere to the following:

Linting & Formatting: * Run [your-formatter-command, e.g., npm run lint] before every commit.

No "magic numbers"—use constants for configuration values (especially for Map/UV API thresholds).

Error Handling: Use try-catch blocks for all external API calls (Mapbox, Weather, Auth) to ensure the UI never "freezes" (per HLSD Section 1.2).

3. Accessibility & UI Requirements
As per our Non-Functional Requirements, all frontend code must:

Use Semantic HTML (or equivalent framework components) for screen reader support.

Include aria-labels for all icons and buttons.

Maintain a Minimum Contrast Ratio of 4.5:1 (WCAG AA) to ensure readability for older adults.

Avoid nesting menus deeper than two levels to minimize cognitive load.

4. Security & Privacy Protocols
Input Validation: All user-generated content (stories/media) must be sanitized and validated before being sent to the database.

Environment Variables: Never commit API keys for Mapping or Weather services. Use a .env.local file.

Data Encryption: Ensure all authentication tokens are stored securely (e.g., HTTP-only cookies or encrypted local storage).

5. Definition of Done (DoD)
A task is "Done" only when:

Code is linted and formatted.

The feature is tested on a mobile-responsive view.

The PR is reviewed and approved by the peer developer.

No secrets (API keys) are exposed in the code.

1.5 Git Commit Message GuidelinesTo maintain a clear and traceable project 

history (supporting our Reliability NFR), all commits must use a specific 

prefix. 

This allows the team to distinguish between new features, bug fixes, and 

maintenance at a glance.

Prefix,Usage,Example

add:,"Introducing a new feature, component, or asset.",add: voice-guided navigation logic

fix:,"Fixing a bug, error, or UI glitch.",fix: adjust contrast for high-visibility buttons

mod:,Modifying or optimizing existing functionality.,mod: simplify the routine management UI

del:,"Removing unused code, files, or deprecated features.",del: remove legacy weather API utility

docs:,"Changes only to documentation (README, HLSD).",docs: update code quality standards

refactor:,Code changes that neither fix a bug nor add a feature.,refactor: optimize data fetching for maps