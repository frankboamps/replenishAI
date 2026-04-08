# ReplenishAI — Interactive Prototype

A clickable web prototype for **ReplenishAI**, an AI co-pilot that predicts when users will run out of household essentials and sends smart reorder alerts before it happens.

Built for the Duke MENG 512 Product Management course.

---

## Live Demo

**GitHub Pages:** [frankboamps.github.io/replenishAI](https://frankboamps.github.io/replenishAI/meng512-prototype/)

Or open locally — no build step required:
```
meng512-prototype/index.html
```
Just double-click or drag into any browser.

---

## What This Prototype Covers

| Screen | What to Try |
|--------|-------------|
| **Setup** | Click any item card → fill in brand, size, supplier, and budget → add to tracking list |
| **Smart Alert** | Review a predicted low-stock alert, swap brands, approve or dismiss the order |
| **Dashboard** | See inventory health bars, days remaining, and restock status for all tracked items |
| **Upgrade** | Explore Plus tier ($7.99/mo) features; trigger the upgrade confirmation modal |

---

## Key Interactions

- **Adding an item:** Click a product card → a detail sheet slides up asking for brand, pack size, preferred supplier (Amazon / Walmart / Instacart), and monthly budget → confirm to add
- **Removing an item:** Click a selected (blue-bordered) card to deselect it instantly
- **Quantity control:** Use the − / + buttons on selected cards to set how many units you track
- **Free tier cap:** Selecting more than 10 items triggers the Plus upgrade nudge
- **Brand swap:** On the Smart Alert screen, tap "Swap Brand" to pick an alternative before approving
- **Approve order:** Routes the mock order to the selected supplier and logs a prevented stockout on the Dashboard

---

## Product Context

**Problem:** Busy students and young professionals run out of household essentials at the worst moments — mid-shower, before guests arrive, late at night. 100% of interviewed users said they discover shortages mid-task.

**Solution:** ReplenishAI learns each user's 30-day consumption cycle, sends context-aware alerts during natural shopping windows, and routes approved reorders to the best supplier. The user stays in control of purchase decisions; the AI handles inventory tracking.

**Target user:** Duke University students and young professionals (primary beachhead: ~10,700 students).

**Business model:**
- Free tier: up to 10 tracked items
- Plus tier: $7.99/mo — unlimited items, AI predictions, calendar sync, price optimization

---

## File Structure

```
meng512-prototype/
├── index.html          # Single-file prototype (HTML + Tailwind CSS + vanilla JS)
├── stitch/             # Stitch design system exports (colors, components, layout)
├── CLAUDE.md           # AI assistant context and permissions
├── TEST_GUIDE.md       # Manual QA checklist for all screens and interactions
└── README.md           # This file
```

---

## Design System

Colors follow the ReplenishAI brand palette:

| Token | Hex | Usage |
|-------|-----|-------|
| Primary | `#003d9b` | Buttons, active states, selections |
| Secondary | `#006c47` | Success / restocked indicators |
| Background | `#f8f9fb` | Page background |
| Warning | `#ffb950` | Low-stock alerts |

Typography: **Inter** — all weights from 300 to 900.

---

## Out of Scope (Prototype Only)

- No real ML or backend — consumption data is mocked
- No real supplier API calls — Amazon / Walmart / Instacart are simulated
- No authentication — user is assumed to be onboarded
- No real payment processing — Plus upgrade is a mock confirmation screen
- No calendar integration — referenced in UI but not functional

---

## Team

Duke MENG 512 — Product Management  
Spring 2026
