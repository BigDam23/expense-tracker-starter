# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev       # Start dev server at http://localhost:5173
npm run build     # Production build
npm run lint      # ESLint
npm run preview   # Preview production build
```

No test framework is configured.

## Architecture

Single-component React app (`src/App.jsx`). All state, filtering logic, and rendering live in one `App` component — no child components exist yet. State consists of:

- `transactions` — array of `{ id, description, amount, type, category, date }` objects
- Form fields: `description`, `amount`, `type`, `category`
- Filter fields: `filterType`, `filterCategory`

The `amount` field is stored as a **string** (from the input's `value`), but the `totalIncome`/`totalExpenses` reducers use it in arithmetic without converting to a number — this is the intentional bug in the starter.

`App.css` defines a `.delete-btn` style but no delete functionality exists in the JSX yet.

## Course context

This is the starter project for a Claude Code course (codewithmosh.com). It intentionally ships with a bug (`amount` string vs. number), a minimal UI, and all code in a single file — these are meant to be fixed/improved as course exercises.