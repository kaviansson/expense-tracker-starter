# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev       # Start dev server (http://localhost:5173)
npm run build     # Production build
npm run preview   # Preview production build
npm run lint      # Run ESLint
```

## Architecture

Single-page React app (no backend, no persistence — data resets on refresh). Built with Vite + React 19.

**Component structure:**

- `App.jsx` — root component; owns the `transactions` array state and passes it down. Renders the three child components.
- `Summary.jsx` — receives `transactions`, computes `totalIncome`, `totalExpenses`, and `balance` internally.
- `TransactionForm.jsx` — owns its own form state (`description`, `amount`, `type`, `category`); calls `onAdd(transaction)` prop on submit.
- `TransactionList.jsx` — receives `transactions`, owns filter state (`filterType`, `filterCategory`) internally.

**Transaction shape:** `{ id, description, amount, type, category, date }` — `amount` is a number, `type` is `"income" | "expense"`.

**Shared constant:** `categories` array is currently duplicated in `TransactionForm.jsx` and `TransactionList.jsx`.
