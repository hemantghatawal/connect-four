# Connect Four Game

A classic Connect Four game built with React, TypeScript, and Vite. Drop your colored discs and try to connect four in a row to win!

## Features

- Two-player gameplay (Red vs Yellow)
- Win detection for horizontal, vertical, and diagonal connections
- Draw detection when the board is full
- Visual column preview on hover
- Reset button to start a new game
- Responsive grid layout

## How to Play

1. Players take turns dropping colored discs into columns
2. Click on a column to drop your disc
3. The disc falls to the lowest available position in that column
4. Connect four discs horizontally, vertically, or diagonally to win
5. If the board fills up with no winner, the game ends in a draw

## Getting Started

Install dependencies:
```bash
npm install
```

Run the development server:
```bash
npm run dev
```

Build for production:
```bash
npm run build
```

## Tech Stack

- React 18 with TypeScript
- Vite for fast development and building
- CSS for styling

## Game Configuration

You can customize the game by modifying these constants in `src/App.tsx`:

- `ROWS`: Number of rows in the grid (default: 6)
- `COLS`: Number of columns in the grid (default: 7)
- `COUNT_TO_WIN`: Number of consecutive discs needed to win (default: 4)
- `PLAYER_TOKENS`: Colors for each player


## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```
