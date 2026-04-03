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

All application logic lives in `src/App.jsx` — a single monolithic component. This is intentional; the project is a course starter designed to be refactored.

**State in App.jsx:**
- `transactions` — array of `{ id, description, amount, type, category, date }`. Note: `amount` is stored as a string.
- Form state: `description`, `amount`, `type`, `category`
- Filter state: `filterType`, `filterCategory`

**Features:** summary dashboard (income/expense/balance totals), add-transaction form with validation, filter by type and category, transaction table.

> Per README: the project intentionally contains bugs, poor UI, and messy code for teaching purposes.
