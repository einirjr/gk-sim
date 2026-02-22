# Fish Market Simulator (Godot) — Roadmap / Milestones

> Goal: Build a small, playable harbour + fish market simulation with a clear core loop:
> **Buy fish → process → sell → upgrade**

## Core Loop (1-liner)
Build and empire by making good decisions at the fish market → buy fish → process according to market demand → sell products → reinvest $$$

---

## Milestone 0 — Foundation ✅
**Outcome:** A controllable character in a top-down world.
- [x] Godot project created + Git repo
- [x] Player top-down movement
- [x] Camera follow
- [x] World markers (visual reference)
- [x] MarketArea zone + interact key works (prints)

---

## Milestone 1 — Basic UI/UX (no prints)
**Outcome:** Player gets clear prompts + simple HUD.
- [ ] CanvasLayer UI root
- [ ] “Press E” prompt appears when inside MarketArea (and later ShedArea)
- [ ] HUD: Money + Inventory counters visible (placeholder values ok)
- [ ] Input mapping consolidated (`move_*`, `interact`)

**Definition of Done:** No debug prints needed to understand what to do.

---

## Milestone 2 — Player state: Money + Inventory
**Outcome:** Core data exists and updates reliably.
- [ ] PlayerData (money, raw_fish, processed_fish)
- [ ] Central place to store state (e.g., Autoload `GameState` or `PlayerData` node)
- [ ] HUD reads from state
- [ ] Simple debug controls (optional): add/remove money for testing

**Definition of Done:** Money & inventory persist while playing and are shown on HUD.

---

## Milestone 3 — Market v0 (static prices)
**Outcome:** Buying works.
- [ ] Market panel UI opens on interact
- [ ] Raw fish price (static)
- [ ] Buy 1 / Buy 10 buttons (or slider)
- [ ] Validation: can’t buy if not enough money
- [ ] Close market panel (Esc / button)

**Definition of Done:** Player can buy raw fish and money decreases correctly.

---

## Milestone 4 — Processing Shed v0 (value-add)
**Outcome:** Processing converts raw → processed over time.
- [ ] Add ShedArea zone + interact
- [ ] Shed panel UI
- [ ] Process 1 fish action with timer
- [ ] Validation: can’t process if no raw fish
- [ ] Result: raw decreases, processed increases

**Definition of Done:** Full loop is playable:
**Buy raw → process → hold processed**.

---

## Milestone 5 — Selling v0 (static price)
**Outcome:** Player can earn money.
- [ ] Sell processed fish at static price
- [ ] Sell 1 / Sell all
- [ ] Money increases, processed decreases

**Definition of Done:** Full economy loop is playable:
**Buy → process → sell → profit**.

---

## Milestone 6 — Market v1 (supply & demand)
**Outcome:** Prices change over time in a predictable way.
- [ ] MarketModel with:
  - [ ] supply (affected by boats/arrivals)
  - [ ] demand (time-based or seasonal)
  - [ ] price curve with min/max clamp
- [ ] Display price trend (↑ ↓ or % change)
- [ ] Simple “Boat arrival” simulation (timer adds supply)

**Definition of Done:** Player can notice and react to price changes.

---

## Milestone 7 — Operating costs + progression
**Outcome:** There is pressure + growth.
- [ ] Daily/periodic costs (lease on shed)
- [ ] Simple upgrades:
  - [ ] Faster processing
  - [ ] Better yield or higher sell price
- [ ] Basic “day tick” (time passes)

**Definition of Done:** Player can grow capacity and manage costs.

---

## Milestone 8 — Simple win condition + events
**Outcome:** A complete small game loop.
- [ ] Win condition (choose one):
  - [ ] Reach cash target
  - [ ] Reach company value target
  - [ ] Survive X days
- [ ] Random events (pick 2–3):
  - [ ] Storm (lower supply)
  - [ ] High demand week (raise prices)
  - [ ] Equipment failure (slower processing)

**Definition of Done:** There is a clear “end” and replayable variation.

---

## Tech Notes / Principles
- Keep scenes modular (Player, Market, Processing, UI panels).
- Prefer data-driven values (prices, timers) in resources/constants.
- Avoid feature creep: ship each milestone before expanding.
- Git: small commits, `main` stays playable.
