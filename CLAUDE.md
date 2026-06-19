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

React + Vite app composed of four components. `App` owns the shared `transactions` state and passes it down; each child owns only what is private to it.

```
App
├── Summary          — calculates and displays totalIncome, totalExpenses, balance
├── TransactionForm  — owns form state; calls onAdd(transaction) on submit
└── TransactionList  — owns filter state; receives transactions and filters locally
```

**State ownership:**
- `App` — `transactions: { id, description, amount, type, category, date }[]`. `amount` is always a number.
- `TransactionForm` — `description`, `amount`, `type`, `category` (reset after submit)
- `TransactionList` — `filterType`, `filterCategory`

`categories` is a local constant duplicated in `TransactionForm` and `TransactionList` (not yet shared).

`App.css` defines a `.delete-btn` style but no delete functionality exists yet.

## Course context

This is the starter project for a Claude Code course (codewithmosh.com). It ships with a minimal UI and is meant to be built out through course exercises.