# ReplenishAI Prototype — Complete Test Guide

## Quick Access
- **URL:** `http://localhost:3000`
- **Hard Refresh:** `Cmd+Shift+R` (Mac) or `Ctrl+Shift+R` (Windows/Linux)

---

## 1. Navigation & Screen Flow

### Screen 1: Onboarding
**Access:** Initial page load

**Test the following:**
- [ ] Page loads with item grid showing 8 default items (Paper Towels, Dish Soap, Detergent, etc.)
- [ ] Item counter shows "03/10" (3 items pre-selected: Dish Soap, Detergent, Paper Towels)
- [ ] Click items to toggle selection (border turns blue, checkmark appears)
- [ ] Sidebar "Dashboard" and "View Plans" links navigate correctly
- [ ] "Initialize Experience" button → navigates to Smart Alert screen

---

## 2. Item Management (Onboarding Screen)

### Pre-populated Items
**Test:**
- [ ] Click unselected items to select them (blue border + checkmark appear)
- [ ] Click selected items to deselect them (blue border disappears)
- [ ] Counter updates in real-time (01/10, 02/10, etc.)

### Quantity Controls
**Test:**
- [ ] Click any selected item card to show glass overlay with "How many?" controls
- [ ] Click **+** button to increase quantity (1→2→3...→9 max)
- [ ] Click **−** button to decrease quantity (9→...→1 min)
- [ ] Quantity displays correctly on overlay

### Adding Custom Items
**Test:**
- [ ] Click the "+ Add Custom Item" card
- [ ] Type an item name (e.g., "Toothpaste")
- [ ] Press **Enter** to add it
- [ ] New item appears in grid with custom icon
- [ ] Item is automatically selected (blue border)
- [ ] Counter increments (e.g., 04/10)
- [ ] Repeat to add multiple custom items
- [ ] When reaching 10 items, counter flashes red and no more items can be added
- [ ] Try adding item #11 — should be rejected with red flash

---

## 3. Smart Alert Screen

**Access:** Click "Initialize Experience" from Onboarding

**Test the following:**
- [ ] Alert card displays:
  - Item: "Paper Towels"
  - Brand: "Bounty"
  - Price: "$14.99"
  - Supplier: "Amazon"
  - Confidence: "94%"
- [ ] "Approve Order" button → navigates to Delight/Dashboard screen
- [ ] "Swap Brand" button → reveals 3 brand alternatives:
  - Kirkland $12.49 (Walmart)
  - Viva $11.99 (Instacart)
  - Bounty $14.99 (Amazon) — pre-selected
- [ ] Click alternative brand → updates alert card, hides brand panel
- [ ] "Dismiss" button → hides action buttons, shows "Undo" link
- [ ] "Undo" link → restores action buttons
- [ ] Sidebar navigation works (Dashboard, View Plans)
- [ ] Mobile bottom navigation works (same buttons)

---

## 4. Delight / Dashboard Screen

**Access:** Click "Approve Order" from Smart Alert

**Test the following:**
- [ ] "Stockout Prevented!" confirmation appears
- [ ] Inventory health grid shows all selected items
- [ ] "Upgrade to Plus" prompt appears as card (item #9 if < 10 items)
- [ ] Achievement card shows "3 Stockouts Prevented This Month"
- [ ] "Upgrade to Plus" button in achievement card → opens modal
- [ ] Referral code section visible with "Share Code" button
- [ ] "Share Code" button → copies "replenish.ai/ref/j-curator-92" to clipboard
  - Button text changes to "Copied!"
  - Text reverts after 1.5s
- [ ] Sidebar and bottom navigation work
- [ ] Click "View Plans" → navigates to Upgrade screen

---

## 5. Upgrade Screen

**Access:** Click "Upgrade Now" button or "View Plans" from Dashboard

**Test the following:**
- [ ] Hero section displays with testimonial
- [ ] Free tier (10 items max) vs Plus tier ($7.99/mo) comparison visible
- [ ] Feature grid shows 4 features (Multi-Supplier Optimization, Calendar Sync, etc.)
- [ ] "Upgrade Now" button at bottom → opens upgrade confirmation modal

---

## 6. Upgrade Modal (Critical Test)

**This was the previously broken button — now fixed**

**Test the following:**
- [ ] Modal displays centered on screen
- [ ] Modal title: "Welcome to Plus!"
- [ ] Two buttons visible:
  - "Go to Dashboard" (blue gradient)
  - "Continue Browsing" (gray)
- [ ] **"Go to Dashboard" button** → closes modal + navigates to Dashboard
  - **This was the bug — should now work after hard refresh**
- [ ] **"Continue Browsing" button** → closes modal, stays on Upgrade screen
- [ ] Click outside modal → modal closes (backdrop click)
- [ ] Modal can be opened again without issues

---

## 7. Cross-Screen Navigation

**Test complete flow:**
1. Onboarding → Add 3+ custom items
2. Initialize Experience → Smart Alert
3. Swap brand once
4. Approve Order → Dashboard
5. Scroll through inventory health
6. Copy referral code
7. Click "Upgrade to Plus" → Modal opens
8. "Go to Dashboard" → Modal closes, back to Dashboard
9. Click "View Plans" → Upgrade screen
10. "Upgrade Now" → Modal opens
11. "Continue Browsing" → Modal closes, still on Upgrade screen
12. Sidebar "Dashboard" → Back to Dashboard
13. Sidebar "Orders" → Back to Smart Alert

---

## 8. Common Issues & Solutions

### Modal Not Closing
**Symptom:** "Go to Dashboard" button doesn't respond
**Fix:** Hard refresh (`Cmd+Shift+R`) to clear cache

### Items Not Adding
**Symptom:** Can't add custom items despite <10 items
**Possible cause:** JavaScript error — check browser console (`F12`)
**Solution:** Hard refresh

### Screen Navigation Broken
**Symptom:** Clicking buttons doesn't change screens
**Possible cause:** JavaScript disabled
**Solution:** Hard refresh, check browser console

### Styling Issues
**Symptom:** Colors/layout look wrong
**Possible cause:** Tailwind CSS CDN not loaded
**Solution:** Hard refresh, check Network tab (`F12`)

---

## 9. Browser Inspector Checklist

If testing and something feels off:

1. Open Developer Tools (`F12`)
2. Go to **Console** tab — look for red error messages
3. Go to **Network** tab — verify `cdn.tailwindcss.com` loaded (should be 200 OK)
4. Go to **Elements** tab — verify modals have `style="display:none"` or `style="display:flex"`

---

## Summary of Fully Functional Features

✅ **Navigation:** All screens accessible via buttons and sidebars  
✅ **Item Management:** Add/remove pre-populated and custom items (max 10)  
✅ **Quantity Controls:** +/− buttons on item cards  
✅ **Smart Alert:** Swap brands, approve, dismiss, undo  
✅ **Delight Screen:** Inventory display, referral copy, upgrade prompt  
✅ **Modal:** Opens/closes properly, "Go to Dashboard" now works  
✅ **Responsive Layout:** Desktop sidebar + mobile bottom navigation  

---

**Last Updated:** April 2, 2026  
**Status:** All features functional after CSS specificity fix
