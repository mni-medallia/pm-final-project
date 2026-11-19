# Competitive Analysis & Journey Map

> **Module 2 · Lab 2 — ★ Deliverable 2.** Repo file `02-discovery/competitive-and-journey.md` — part of your submission.
> Do the lab in the **Module 2 · Exercise 2 Guide** (linked from the Module 2 deck), then click **⬇ Download .md** — it saves as this exact file. Commit it here.
> It becomes the **Competitive Analysis & Journey Map** slide of your Module 6 final deck. Builds on your `ai-synthesis.md` and your Module 1 `problem-hook.md`.

## Responses

- **Role, who are you solving for?:** The Fleet Dispatcher, who assigns and reassigns routes and tracks every stop on the RouteLogic dispatch board.
- **Goal, what is this user ultimately trying to achieve?:** To get route changes to drivers right away and see accurate stop status, so the operation runs from one source of truth.
- **Friction, the main barrier (moment of misery) stopping them:** Sync fails in both directions. A reassigned route takes 8 to 15 minutes to reach the driver and sends no push notification (BUG-2044), so the driver has already driven the wrong way. Stop status comes back 20 to 60 minutes late (BUG-2072), so a stop still shows "in progress" an hour after delivery.
- **External tools the user is forced to use:** A WhatsApp group with the drivers that the team calls "the real system" (UXR-02). Phone calls when a message goes unread. The dispatcher's own memory or notes to track which board statuses are wrong.
- **The process, the 3–5 manual steps they take:** (1) Reassign the route on the RouteLogic board, because the system of record requires it. (2) Retype the change (new stops, order, addresses) into the WhatsApp group, since the app won't notify the driver for up to 15 minutes. (3) Call the driver if the message isn't read, while the driver reads and reroutes from a chat message on the road. (4) Ask drivers to confirm each delivery in WhatsApp, because the board lags by up to an hour. (5) Reconcile the board against the chat thread by hand, mentally overriding stale "in progress" stops when answering customers or making the next reassignment.
- **Core frustration, where the process feels most "broken":** The dispatcher has become the sync layer. Every change is entered twice, the two copies drift apart, and the board they pay for is the one they trust least. WhatsApp leaves no structured record, so the delivery data that feeds RouteLogic's reporting is wrong or missing.
- **The evidence, a quote or behavior from the research:** "I can't trust the board" (UXR-09). The team keeps "a WhatsApp group as the real system" (UXR-02). BUG-2044 (8 to 15 minute route push delay, no notification) and BUG-2072 (20 to 60 minute status lag) confirm the cause.
- **Journey map, a shareable link or the map file you committed:** `02-discovery/journey-map.html` (source: `02-discovery/future-state-journey.md`)
