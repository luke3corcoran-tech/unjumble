# Unjumble

Daily anagram word game. Single static page (`index.html`) hosted on GitHub Pages from `main` / root.

## Game rules (decided)
- Everyone gets the same 3 words per day. One attempt per day. No bonus round.
- Every word is 7 letters. Avoid words that are anagrams of other common words (one valid answer).
- Each word has a clue. Clues should be lateral (idioms, double meanings, misdirection), never a direct synonym or definition.
- Tap two tiles to swap. The word auto-checks after every swap.
- Up to 3 reveals per word. Each one places one correct letter and locks it.
- Give up shows the answer and scores 0.

## Scoring
- Each word is worth up to 100 points (300 max per day).
- Lose 1 point every 2 seconds (`PER_SEC=0.5`).
- Each reveal costs 15 points.
- A solved word keeps at least 10 points.
- Constants are at the top of the script: `MAX_PTS`, `PER_SEC`, `REVEAL_PTS`, `MIN_PTS`, `MAX_REVEALS`.

## Puzzles
- `BANK` in `index.html`: an array of days, each holding 3 `[WORD, clue]` pairs.
- The puzzle number is days since 2026-11-26 (puzzle #1), using local midnight. It cycles through `BANK`.
- Only 10 sample days exist so far. Add more before sharing widely.

## State
- Results, streak and best score are kept in `localStorage` (key `unjumble`) on each player's device.
- There's no backend and no shared leaderboard.
- After finishing, players see their results and a countdown to the next puzzle.

## Known limits / next ideas
- Answers are visible in the page source.
- Possible later move: Vite + React + TypeScript, with Vitest tests on scramble/reveal/scoring.
