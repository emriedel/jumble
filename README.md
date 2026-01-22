# Jumble

A mobile-first daily word puzzle game where players find words on a Boggle-style letter grid within a time limit. Same puzzle for all players each day, with shareable results.

## Play

Find as many words as possible by connecting adjacent letters (including diagonals). Each tile can only be used once per word. Race against the 3-minute timer!

### Controls

- **Drag**: Swipe across tiles to form words, releases to submit
- **Tap**: Tap tiles to select, double-tap last tile to submit
- **Clear**: Reset your current selection

### Scoring

| Word Length | Points |
|-------------|--------|
| 3-4 letters | 1 pt   |
| 5 letters   | 2 pts  |
| 6 letters   | 3 pts  |
| 7 letters   | 5 pts  |
| 8+ letters  | 11 pts |

## Features

- **Daily Puzzle**: Seeded RNG ensures the same puzzle for all players each day
- **Touch-Optimized**: Drag or tap input methods for mobile and desktop
- **Visual Feedback**: Path highlighting, color-coded timer warnings, haptic feedback
- **Statistics**: Track games played, streaks, best scores
- **Shareable Results**: Native share on mobile, clipboard on desktop
- **Offline Support**: Dictionary loaded once, game works offline
- **Dark Mode**: Easy on the eyes

## Tech Stack

- **Framework**: Next.js 14 (App Router) + TypeScript
- **Styling**: Tailwind CSS
- **Storage**: localStorage (no backend required)
- **Dictionary**: ENABLE word list (~172K words)
- **Deployment**: Vercel

## Development

```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Build for production
npm run build

# Run linter
npm run lint
```

## Project Structure

```
src/
├── app/                    # Next.js app router
├── components/             # React components
│   ├── Game.tsx           # Main game orchestrator
│   ├── BoggleGrid.tsx     # Interactive letter grid
│   ├── Tile.tsx           # Individual letter tile
│   ├── Timer.tsx          # Countdown display
│   └── ...                # Modals, lists, buttons
├── hooks/                  # Custom React hooks
│   ├── useGameState.ts    # Game state management
│   ├── useTimer.ts        # Countdown timer
│   └── useTouchDrag.ts    # Touch/mouse handling
├── lib/                    # Core logic
│   ├── dictionary.ts      # Trie-based word validation
│   ├── boardGenerator.ts  # Seeded board generation
│   ├── wordValidator.ts   # Path validation
│   └── scoring.ts         # Score calculation
├── types/                  # TypeScript interfaces
└── constants/              # Game configuration
```

## Configuration

Edit `src/constants/gameConfig.ts` to customize:

```typescript
export const BOARD_SIZE = 4;        // Grid size (4x4)
export const TIMER_DURATION = 180;  // Seconds (3 minutes)
export const MIN_WORD_LENGTH = 3;   // Minimum word length
```

## Deploy

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/YOUR_USERNAME/jumble)

Or deploy manually:

```bash
npm i -g vercel
vercel
```

## License

MIT
