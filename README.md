# Pencil Cup

A hand-drawn 3v3 arcade football game featuring human and AI teams, a fixed-step match simulation, possession, goalkeeping, replay, set pieces, and a customizable presentation.

**[Play on itch.io](https://abprojects.itch.io/pencil-cup)** · [Technical report](docs/TECHNICAL_REPORT.pdf) · [Report source](docs/TECHNICAL_REPORT.md) · [Architecture](docs/ARCHITECTURE.png)

![Game preview](docs/screenshots/cover.png)

![Kickoff in the game](docs/screenshots/kickoff.png)

![System architecture](docs/ARCHITECTURE.png)

## Run

Open **`index.html`** in a modern desktop browser with WebGL support. The runtime is a single-file HTML5 build: bundled scripts, styles and assets stay embedded. The game can also be uploaded as an HTML5 ZIP to itch.io with `index.html` at the root.

## Gameplay and controls

WASD to move, Shift to sprint, P to pause; left mouse to pass/charge a shot with the ball, right mouse for lofted play; without the ball, left mouse to tackle and right mouse to switch players or call the goalkeeper.

## Repository guide

- `index.html`: complete executable game. Do not separate or import runtime dependencies.
- `docs/TECHNICAL_REPORT.pdf`: formal report covering architecture, algorithms, behavior changes and limits.
- `docs/TECHNICAL_REPORT.md`: readable report source for GitHub.
- `docs/ARCHITECTURE.png`: diagram of major subsystems.
- `docs/RELEASE_NOTES.md`: precise change summary.
- `docs/VALIDATION.md`: structured manual acceptance checks.
- `docs/RELEASE_MANIFEST.json`: original and release SHA-256 hashes.
- `tests/verify.mjs`: non-graphics regression and syntax smoke checks.

## Verification and performance

The updated build passed JavaScript syntax and document-integrity checks. An Xvfb-hosted Chromium session initialized WebGL and checked the visible menus. A match reached the kickoff sequence. Render-submission scheduling was examined with the WebGL draw method stubbed; **no measured FPS or GPU speedup is claimed**. See the report for details and `docs/VALIDATION.md` for the essential browser tests before publishing to itch.io.

## Source, screenshots and permissions

The existing game page is [Pencil Cup on itch.io](https://abprojects.itch.io/pencil-cup). The included cover screenshot was captured from this game in a software-WebGL browser. The itch.io page can supply additional screenshots once their exact image files are downloaded or verified. Third-party embedded engine licences remain with their original code. This repository does not include a new project licence; discuss licence terms before distributing for reuse.
