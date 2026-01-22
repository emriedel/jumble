# Jumble - Daily Boggle Word Puzzle

## Project Overview
A mobile-first daily word puzzle game where players find words on a Boggle-style letter grid within a time limit. Same puzzle for all players each day, with shareable results.

## Tech Stack
- Next.js 14 (App Router) + TypeScript
- Tailwind CSS (dark mode)
- localStorage only (no database)
- Vercel deployment

## Key Files
- `src/constants/gameConfig.ts` - Configurable game parameters (board size, timer, scoring)
- `src/lib/dictionary.ts` - Trie-based word validation
- `src/lib/boardGenerator.ts` - Seeded daily board generation
- `src/lib/wordValidator.ts` - Path adjacency validation
- `src/components/Game.tsx` - Main game orchestrator

## Commands
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run lint` - Run ESLint

## Game Rules
- Find words by connecting adjacent tiles (including diagonals)
- Each tile can only be used once per word
- Minimum word length: 3 letters
- "Qu" is a single tile (counts as 2 letters for scoring)
- Timer: 3 minutes

## Scoring
- 3-4 letters: 1 point
- 5 letters: 2 points
- 6 letters: 3 points
- 7 letters: 5 points
- 8+ letters: 11 points
