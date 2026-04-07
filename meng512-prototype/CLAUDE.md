# CLAUDE.md — Product Prototype Context

---

## Product Overview

**Product Name:** ReplenishAI

**Product Description:** ReplenishAI is an AI co-pilot that predicts when users will run out of household essentials and sends smart alerts before it happens — so users never face a mid-task shortage again. It learns each user's 30-day consumption cycle, sends context-aware notifications during natural shopping windows, and routes approved orders to the best supplier. Inventory tracking is managed by AI; purchase decisions stay with the user.

**Problem Statement:**
Busy students and young professionals constantly run out of household essentials at the worst possible moments — mid-shower, at 11 PM before laundry, 30 minutes before guests arrive. 100% of interviewed users discovered shortages mid-task. Managing a mental inventory of 25+ items alongside work, classes, and deadlines creates chronic cognitive overload; 72% of this cognitive household labor falls on one person. Existing solutions like Amazon Subscribe & Save use fixed cadences and can't adapt to irregular real-life usage, while reminder apps are purely reactive. The result: reactive emergency runs to convenience stores that cost 5–6× normal price. ReplenishAI solves the root cause — cognitive overload — not just logistics.

**Target Customer:**
Primary beachhead: Duke University students (undergrad + grad, ~10,700 students). Key personas:
- **Zion** (22, Student Leader): Hosts weekly gatherings, runs a packed schedule, discovers shortages 30 min before guests. Wants zero mental effort.
- **Hannah** (28, Project Manager): After managing projects all day, has no capacity to manage her pantry. Forgets basics like paper towels and dish soap. Wants predictive alerts.
- **Marcus** (35, Parent of two): Juggles kids, work, household. Mentally tracking 50+ items. Wants budget optimization and household-level coordination.

Across all personas, **time and routine protection consistently outranked price savings** as the #1 value driver.

---

## User Journey (Simplified for Prototyping)

**Scene 1 — Onboarding / Item Setup**
- What the user sees: A lightweight onboarding flow asking them to add their household essentials (paper towels, dish soap, laundry detergent, etc.). Free tier supports up to 10 items.
- What the user does: Adds items, sets preferences (preferred brands, budget sensitivity), connects their calendar (optional).
- What happens next: ReplenishAI begins learning the user's consumption patterns. A confirmation screen reassures them: "ReplenishAI gets smarter over time."

**Scene 2 — Smart Alert**
- What the user sees: A push notification sent at a natural shopping window (e.g., Sunday afternoon): "You'll likely run out of paper towels in 5 days. Want to reorder?"
- What the user does: Taps to open the alert. Reviews the suggested item, brand, supplier (Amazon/Walmart/Instacart), and price. Can approve, swap brands, or dismiss.
- What happens next: If approved, the order is routed to the selected supplier and tracked in real time.

**Scene 3 — Stockout Prevented / Delight Moment**
- What the user sees: A confirmation that the order has been delivered and their inventory is updated. The app logs the restocked item.
- What the user does: Optionally shares the experience ("I never ran out!") or refers a friend via the referral program ($5 credit).
- Outcome: User experiences the core value — they didn't run out, they didn't have to think about it. The ML model gets smarter. The user is nudged to upgrade to Plus when they hit the 10-item cap or after their 3rd prevented stockout.

**Scene 4 — Upgrade / Upsell (Optional)**
- What the user sees: An in-app prompt after hitting the 10-item free tier cap or after 3 prevented stockouts: "Unlock unlimited items + AI predictions — $7.99/mo."
- What the user does: Reviews the Plus tier features (unlimited items, AI predictions, calendar sync, price deals) and subscribes.
- Outcome: User converts to paid. Core revenue driver at 73% contribution margin.

---

## Customer Interview Insights

1. **Mid-task disruptions cause the sharpest emotional spikes** — scored 8–10/10 on frustration. Running out while mid-task (mid-shower, pre-hosting, 11 PM laundry) is the most viscerally painful moment. "Running out completely is the most frustrating — 10/10." — Zion
2. **Cognitive overload is the real pain, not just inconvenience** — users describe their mental load as "50 tabs open in my brain." The problem is managing inventory *on top of* demanding work and academic schedules. "After managing projects all day, I don't want to manage my pantry too." — Hannah
3. **Existing tools are fragile** — most users rely on memory or a Notes app, both of which fail when life gets busy. Reminder apps are reactive; Subscribe & Save doesn't adapt to irregular usage.
4. **The ideal state is universal: "essentials just there" with zero mental effort** — users don't want a better reminder; they want the problem to disappear. "I don't notice the gradual decline. I only notice the zero." — Zion
5. **Time and routine protection > price savings** — across every persona interviewed, protecting their time and preventing routine disruptions ranked higher than saving money as a motivator to use the product.

---

## Design & Style Preferences

**Visual Style:** Clean and minimal with a friendly, modern feel. Approachable for a Gen Z student audience but polished enough for professional users. Not overly playful — the product solves a real daily pain, so the UI should feel confident and calm, not gimmicky.

**Color Palette:** Teal/seafoam + clean white/off-white with subtle dark navy accents. Suggested palette inspired by the brand:
- Primary: `#028090` (teal)
- Secondary: `#00A896` (seafoam/mint)
- Background: `#F8FAFB` (near-white)
- Accent/CTA: `#21295C` (midnight navy)

**Reference Apps / Inspiration:** Notion (clean, minimal, structured), Superhuman (fast, opinionated, delightful interactions), Venmo (campus-viral, peer-spread mechanics), Any.do or Todoist (task-style UX for approving/dismissing suggestions).

---

## Technical Notes for Claude Code

**Prototype Type:** Web app (HTML/CSS/JS or React) — full browser viewport, not mobile-app chrome

**Branding:** Generic — no university-specific references, copy, or email verification. Use neutral language like "your campus" or "your household" only if contextually needed.

**Framework Preference:** React preferred for component reuse (alert cards, item lists, onboarding steps). Vanilla JS acceptable for a simpler MVP.

**Key Behaviors to Prototype:**
- [ ] User can add household items to a tracked list (up to 10 on free tier)
- [ ] User sees a smart alert card showing a predicted low-stock item with supplier options and price
- [ ] User can approve, swap brand, or dismiss the alert
- [ ] User sees a "stockout prevented" confirmation / delight screen after approving
- [ ] Upgrade prompt appears after hitting the 10-item cap or 3 approved alerts (Plus tier: $7.99/mo)
- [ ] Referral prompt appears on the delight screen ("Share with a friend, get $5 credit")

**What NOT to build (out of scope for today):**
- [ ] No real ML / backend — use mock consumption data and hardcoded alert triggers
- [ ] No real supplier API calls — mock the supplier options (Amazon, Walmart, Instacart) with static data
- [ ] No login/auth — assume user is already onboarded
- [ ] No real payment processing — mock the Plus upgrade confirmation screen
- [ ] No calendar integration — can reference it in UI but doesn't need to actually sync

---

## Claude Permissions

### Allowed Without Permission

**Reading and Searching**
- Read any file in the working directory
- Search files with Glob, Grep, or equivalent
- Run read-only shell commands: `git status`, `git log`, `git diff`, `ls`, `cat`, `which`, `env`

**Writing Code**
- Edit existing files to fix bugs, implement features, or refactor per the request
- Create new files when clearly required by the task
- Write tests and supporting files needed to complete the task

**Running Local Commands**
- Run tests (`pytest`, etc.)
- Install dependencies (`pip install`)
- Run linters and formatters (`black`, `flake8`, etc.)
- Start or stop the local dev server

---

### Requires Explicit Permission

**Git and Version Control**
- `git commit` -- creating any commit
- `git push` -- pushing to any remote
- `git reset --hard` or any destructive reset
- Deleting branches local or remote
- Amending already-pushed commits

**Destructive Local Operations**
- Deleting files or directories (`rm`, `rm -rf`)
- Overwriting uncommitted work
- Clearing data files (registry.json, audit.json, demo_state.json)
- Killing processes

**Infrastructure and Config**
- Modifying environment variables or secrets
- Changing Railway deployment config

---

### Standing Rules

- Never auto-commit. Always confirm the commit message and scope first.
- Never force-push unless explicitly told to for that specific situation.
- If an action is ambiguous, ask before proceeding.
- One approval is not blanket approval. Each risky action needs its own confirmation.
- If a test fails, fix the root cause. Do not bypass with `--no-verify` or skip the test.
- Do not add dependencies not listed in Architecture Decisions without asking first.

---

## Design System

Reference the `stitch/` folder for all design instructions before writing any UI code.
Stitch may generate various file types — check for any design files, exports, assets,
or markdown it has produced (e.g. DESIGN.md, component files, style exports, screenshots).

### How to use it
- Treat Stitch output as the source of truth for visual design: colors, typography,
  spacing, components, layout patterns, and overall aesthetic.
- Follow Stitch designs closely, but **do not ignore the prompt**. If the user's
  prompt asks for something Stitch doesn't cover, use good judgment to stay
  consistent with the established style while fulfilling the request.
- If Stitch output conflicts with an explicit prompt instruction, **follow the prompt**
  and try to reconcile it with the design system where possible.
- If no Stitch files are found, ask the user before proceeding with your own design choices.
