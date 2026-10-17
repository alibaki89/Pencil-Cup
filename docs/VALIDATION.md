# Manual browser acceptance checklist

Run on desktop Chrome and Firefox (WebGL enabled), with a fresh profile and saved settings. Mark each scenario PASS/FAIL with screenshots/notes. These tests were **not** completed by the automated audit.

- [ ] Launch into team/competition menu; settings cards render
- [ ] Start each of Friendly, Quick Match and Pencil Cup modes
- [ ] Move with WASD, sprint and switch selected player
- [ ] Pass, charge/shoot and loft while in possession
- [ ] Tackle and call goalkeeper; verify no stuck input
- [ ] Observe goals, out-of-bounds, restarts and end-of-match results
- [ ] Pause, resume, quit, restart and open settings
- [ ] Alt-Tab and return; confirm no clock/input runaway
- [ ] Watch paused/menu frame rate and verify it does not harm responsiveness

## Measurement instructions

1. Open Chrome Developer Tools → Performance and capture 30 seconds during active gameplay and 30 seconds paused.
2. Compare frame count and GPU activity against the original release on the same hardware; expect non-gameplay draw frequency to fall toward 10 Hz, not a claimed measured FPS gain.
3. Test at 1280×720 and 1920×1080, low- and high-DPR displays if available.
4. Record browser, OS, GPU, seed, mode and result when filing a bug.

## Automated smoke test

`node tests/verify.mjs`

This validates self-containment and parsing, not full WebGL gameplay.

## Completed virtual-desktop smoke checks

- WebGL canvas and menus initialized in original and revised Chromium runs; no uncaught page errors.
- Team selection and match setup reached; kickoff scene rendered.
- Isolated idle draw-request count: original 135, release 26 over an approximately 3.6-second window. Not an FPS benchmark.
