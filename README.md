# Sawasdee · Learn Thai 🐘

A single-file, zero-dependency web app for learning Thai vocabulary with swipeable
flashcards, quizzes, spaced-repetition memory tracking, and a growing animal buddy.
No build step, no server, no framework — just one `index.html` you can host on
GitHub Pages.

---

## Features

- **563 Thai words across 9 categories** — Animals, Family, Food & Drinks, Shopping,
  Travel, Weather, Basic Talk, Fruit & Veg, Plants.
- **Pick your meanings** — choose up to two of English, 日本語 (with kana), 简体中文,
  and 繁體中文 (Chinese shown with pinyin). Changeable anytime in Settings.
- **Pronunciation guide** — switch between Romanization and IPA.
- **Three Thai buddies** — **Sawasdee** the elephant, **Mali** the Siamese cat, and
  **Malai** the Thai dog. Each has gentle idle motion (breathing, ear-wave, blink,
  occasional glance and eye-roll) and reacts when you tap to tickle them. They grow
  through six stages as you learn.
- **Flashcards** — swipe through cards, tap the card to flip, SRS (Leitner) memory
  status (New → Learning → Familiar → Mastered). The Again / Hard / Good / Easy rating
  buttons are always available, so you can rate a word from either side of the card.
- **Quizzes** — Meaning, Thai, and Mixed modes, with configurable pool and length.
  *(A "Listening" mode exists in the code but is hidden for now — see ROADMAP.)*
- **Browse & search** — find any word across Thai, pronunciation, and all meanings.
- **Progress dashboard** — XP, daily streak, growth stage, and recent activity.
- **Local multi-profile accounts** — create / switch / delete profiles, each with its
  own progress, plus export/import backup codes. Everything is saved on the device
  via `localStorage`; nothing is uploaded.

---

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g. `sawasdee-learn-thai`).
2. Upload the contents of this folder to the repository root — at minimum
   `index.html` and `.nojekyll`. (`README.md`, `CHANGELOG.md`, and `ROADMAP.md` are
   for you; they don't affect the app.)
3. In the repo, go to **Settings → Pages**, set **Source** to *Deploy from a branch*,
   choose the `main` branch and the `/ (root)` folder, and save.
4. After a minute, your app is live at `https://<your-username>.github.io/<repo-name>/`.

To update later, commit a new `index.html` over the old one — GitHub Pages redeploys
automatically.

The `.nojekyll` file tells GitHub Pages to serve the files as-is (no Jekyll
processing), which is the safe default for a plain single-file app.

---

## Data

The vocabulary is embedded directly in `index.html` (from a multilingual Thai
spreadsheet), so the app works fully offline once loaded. Meanings and pronunciation
guides are reference study aids and may benefit from a native speaker's refinement.

---

## Tech notes

- Pure HTML / CSS / vanilla JS in one file. No dependencies except Google Fonts
  (Outfit for UI, **Noto Sans Thai Looped** — a looped (มีหัว) sans face — for Thai, and Noto Sans
  JP / SC / TC for Japanese and Chinese), which load from the CDN.
- Animations respect `prefers-reduced-motion`.
- Tested as a mobile-first layout (max width ~560px) with safe-area insets.
