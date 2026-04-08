# ReplenishAI

> Never run out of household essentials again.

ReplenishAI is an AI co-pilot that predicts when you'll run out of household essentials and sends smart reorder alerts before it happens — so you never face a mid-task shortage again.

---

## Live Demo

**[frankboamps.github.io/replenishAI/meng512-prototype/](https://frankboamps.github.io/replenishAI/meng512-prototype/)**

No login required. Open in any browser and start clicking.

---

## How to Access

### Option 1 — Live Website (Recommended)
Click the link below — no download, no install, no login:

**[frankboamps.github.io/replenishAI/meng512-prototype/](https://frankboamps.github.io/replenishAI/meng512-prototype/)**

Works on any modern browser (Chrome, Safari, Firefox, Edge).

### Option 2 — Run Locally
1. Click the green **Code** button on this page → **Download ZIP**
2. Unzip the file
3. Open `meng512-prototype/index.html` in your browser

That's it — no server, no dependencies, no setup required.

---

## How to Use the Prototype

The prototype simulates the full user journey across 4 screens. Use the top navigation bar (**Setup / Smart Alert / Dashboard / Upgrade**) to move between them.

### Step 1 — Setup: Add Your Household Items

1. You'll see a grid of common household products
2. **Click any card** to add it — a detail sheet will pop up asking for:
   - **Brand** (e.g. Dawn, Bounty, Tide)
   - **Pack size** (e.g. 32 oz, 6-pack)
   - **Preferred supplier** — Amazon, Walmart, or Instacart
   - **Monthly budget** — Low / Mid / High
3. Click **"Add to Tracking List"** to confirm
4. Use the **− / +** buttons on selected cards to set quantity
5. Click a selected card again to remove it
6. Free tier supports up to **10 items** — selecting more triggers the upgrade prompt
7. When ready, click **"Initialize ReplenishAI"** at the bottom to continue

### Step 2 — Smart Alert: Review a Reorder Suggestion

ReplenishAI has detected that your **Paper Towels** will run out in 5 days.

- **Approve Order** — confirms the reorder and routes it to Amazon
- **Swap Brand** — opens a brand picker to choose an alternative (Viva, Scott, Kirkland)
- **Dismiss** — skips this alert; ReplenishAI will remind you in 2 days

### Step 3 — Dashboard: Check Your Inventory Health

See all tracked items at a glance:
- **Color-coded status chips** — OPTIMAL / GOOD / LOW / REORDERING / RESTOCKED
- **Progress bars** — show percentage of stock remaining
- **Days remaining** — estimated days until stockout

### Step 4 — Upgrade: Unlock Plus

- Compare Free vs Plus tier features
- Click **"Upgrade Now"** to see the confirmation screen
- After upgrading, the item cap is removed and the dashboard unlocks advanced features

---

## The Problem

Busy students and young professionals constantly run out of household essentials at the worst possible moments — mid-shower, at 11 PM before laundry, 30 minutes before guests arrive. Managing a mental inventory of 25+ items alongside work, classes, and deadlines creates chronic cognitive overload.

- 100% of interviewed users discovered shortages **mid-task**
- 72% of household cognitive labor falls on **one person**
- Emergency convenience store runs cost **5–6× normal price**

Existing tools like Amazon Subscribe & Save use fixed cadences that can't adapt to irregular real-life usage. Reminder apps are purely reactive.

---

## The Solution

ReplenishAI learns each user's 30-day consumption cycle, sends context-aware notifications during natural shopping windows, and routes approved orders to the best supplier. **Inventory tracking is managed by AI; purchase decisions stay with the user.**

---

## Key Features

| Feature | Description |
|---------|-------------|
| Smart Item Setup | Add household essentials with brand, size, supplier preference, and budget |
| AI Predictions | Predicts stockout dates based on consumption patterns |
| Smart Alerts | Context-aware notifications sent at natural shopping windows |
| One-tap Reorder | Approve, swap brands, or dismiss — full control stays with the user |
| Inventory Dashboard | Real-time health bars showing days remaining per item |
| Referral Program | Share with friends, earn $5 credit per signup |

---

## Pricing

| Plan | Price | Items |
|------|-------|-------|
| Free | $0 | Up to 10 items |
| Plus | $7.99 / mo | Unlimited items + AI predictions + calendar sync + price deals |

---

## Repository Contents

```
├── meng512-prototype/        # Interactive web prototype
│   ├── index.html            # Single-file app (HTML + Tailwind CSS + JS)
│   ├── stitch/               # Design system exports
│   ├── README.md             # Prototype-specific documentation
│   └── TEST_GUIDE.md         # Manual QA checklist
├── ReplenishAI_GTM_Strategy_Team_1.pptx   # Go-to-market strategy deck
└── ReplenishAI_Revised.pptx               # Product pitch deck
```

---

## Target Users

- **Zion** (22, Student Leader) — hosts weekly gatherings, discovers shortages 30 min before guests
- **Hannah** (28, Project Manager) — after managing projects all day, has no capacity to manage her pantry
- **Marcus** (35, Parent of two) — mentally tracking 50+ items across work, kids, and household

**Primary beachhead:** Duke University students (~10,700 students)

---

## Course

Duke University — MENG 512 Product Management, Spring 2026
