# Sawasdee · Roadmap & Open Items

Notes on what's next, kept here so we both have the same reference between sessions.

---

## 1. Mascot growth + XP + stage names

**Status: already implemented.** Sawasdee inherited the full growth/XP system from the
Panda HSK app, already adapted with Thai-themed stage names — so this is mostly a
*naming* decision now, not new engineering. To your question: yes, stage 1 really is
called **"First Hello." 😄**

### How growth works

The buddy advances through **6 stages**, driven by **Growth Points (GP)**:

> **GP = (mastered words × 3) + (familiar words × 1)**

GP comes from *memory status*, not raw XP — so the buddy grows as words genuinely
stick, not just from time spent. (XP, the number on the dashboard, is a separate
motivational tally: +2/+3/+5/+6 per study rating of Again/Hard/Good/Easy, plus a
one-time +20 when a word first reaches **Mastered**.)

### The six stages (open for revision)

| # | Stage name | GP to reach | Caption |
|---|------------|-------------|---------|
| 1 | **First Hello**   | 0   | Just learned to say สวัสดี! |
| 2 | **Curious Steps** | 20  | Picking up new words every day. |
| 3 | **Market Ready**  | 60  | Can chat through a market run. |
| 4 | **City Explorer** | 140 | Finding the way around with ease. |
| 5 | **Smooth Talker** | 300 | Words flow like the Chao Phraya. |
| 6 | **Thai at Heart** | 600 | Speaks with warmth and confidence. |

These names + captions show on the Study page, the Progress dashboard, and in the
"grew into …" toast (e.g. *"🌱 Sawasdee grew into Market Ready!"*).

**Your move:** propose any revised names/captions you'd prefer (Thai words, learner
milestones, whatever fits the tone). Both the names *and* the GP thresholds are easy
to change — they live in one `STAGES` array near the top of the script. Send the new
list and I'll drop it in.

> Idea space if useful: stage names could lean on a Thai-language theme
> (สวัสดี → ตลาด → เดินทาง → …), a journey theme (Arrival → Wandering → At Home), or a
> lotus-growth theme (Seed → Sprout → Bud → Bloom → …). Happy to draft a couple of full
> sets for you to pick from.

---

## 2. Thai voice (audio) — deferred

The browser's built-in `th-TH` speech voice is unreliable: many phones and desktops
either lack a Thai voice entirely or fall back to a wrong-language voice, which sounds
worse than silence. So for now the audio affordances are **hidden, not deleted**:

- Speaker (🔊) buttons on the flashcards and in Browse — hidden via CSS.
- The **Listening** quiz mode — hidden, and Mixed quizzes no longer generate audio
  questions.
- The `speak()` function and all wiring remain in place.

### To re-enable later

In `index.html`:
1. Remove the two hide rules in the CSS comment block
   `/* Thai voice deferred … */` (`.spk` and the `data-qt="listen"` rule).
2. In `buildQuiz()`, restore `"listen"` in the Mixed-mode array and remove the
   `if(quiz.type==="listen")quiz.type="mean";` coercion line.

### Options worth weighing when we pick this back up

- **Pre-recorded audio clips** per word (best quality, but adds files and size — would
  break the single-file constraint unless base64-embedded).
- **Smarter voice detection** — only show the speaker when a real `th-TH` voice is
  present on the device, and hide it otherwise.
- **A cloud TTS** at build time to generate clips — more setup, highest consistency.

---

## Thai font — how to swap

The app uses **Maitree** (looped serif). Every Thai glyph routes through one CSS
variable, so changing the face is two edits in `index.html`:

1. In the `<head>` Google Fonts `<link>`, swap the `Maitree:wght@400;500;600;700`
   segment for the family you want.
2. Change the `--thai` variable to match.

Drop-in looped alternatives (all keep the traditional heads):

| Family | Style | Feel |
|--------|-------|------|
| **Maitree** *(current)* | looped serif | warm, textbook |
| **Pridi** | looped serif | a touch more formal |
| **Noto Serif Thai** | looped serif | neutral, pairs with the Noto stack |
| **Trirong** | looped serif | higher contrast, display-ish |
| **Sarabun** | looped **sans** | the Thai document/textbook standard — clean heads, no serif |

If you'd like to A/B them without editing files, I can add a small "Thai font" toggle
to Settings.

---

## Possible later additions (parked)

- A fourth+ buddy (the `MASCOTS` map is ready for it — one entry adds a buddy
  everywhere).
- More vocabulary / categories as the spreadsheet grows.
- A short in-app user guide / help sheet.
