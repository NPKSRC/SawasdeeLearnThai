# Changelog

All notable changes to Sawasdee · Learn Thai. This project follows
[Semantic Versioning](https://semver.org/).

## [1.2.0] — 2026-06-21

### Changed
- **Thai typeface** is now **Noto Sans Thai Looped**, a looped (มีหัว) sans face with
  traditional clear "heads," replacing the loopless Noto Sans Thai. All Thai text routes
  through the single `--thai` CSS variable, so the font can be swapped in one line (see
  ROADMAP for alternatives: Sarabun, Maitree, Pridi, Noto Serif Thai).

## [1.1.0] — 2026-06-21

### Added
- **Mascot idle animations** — gentle breathing, ear-wave (tuned per animal),
  blinking, and occasional eye glances / eye-roll. Scoped to the resting mood so they
  pause cleanly while an expression plays.
- **Tap to tickle** — tapping the buddy on the Study or Quiz page plays one of three
  reactions (wiggle, bounce, squish) at random, never repeating the same one twice in
  a row, with a floating spark and a happy-face flash.
- All ambient motion respects `prefers-reduced-motion`; the tap reaction stays as
  deliberate user feedback.

### Changed
- **Renamed the buddies**: Chang → **Sawasdee** (elephant), Wichian → **Mali** (cat),
  Tongdaeng → **Malai** (dog).

### Deferred
- **Thai audio** — the `th-TH` speech voice is unreliable across operating systems, so
  the speaker icons (cards and browse) and the **Listening** quiz mode are hidden for
  now. The `speak()` code path is kept intact; Mixed quizzes no longer generate audio
  questions. See ROADMAP for the re-enable plan.

## [1.0.0] — 2026-06-21

### Added
- Initial build: three-step onboarding (profile + buddy → up to two meaning languages
  → pronunciation guide), category-based study (9 categories), three Thai buddies with
  six growth stages, SRS flashcards with swipe, quizzes, browse/search, a progress
  dashboard (XP, streak, growth), and local multi-profile accounts with backup codes.
