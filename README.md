# Kick the Tires 🚗

**A used-car buying uncle for Claude: ranks cars by how much money they'll cost you by the time you sell, not by how shiny the deal looks.**

Most car-shopping tools stop at "good deal" or "great deal." Kick the Tires asks the question your car-dealer uncle would ask: *what will this car actually cost you over the time you own it?* Then it plans your Saturday.

## What it does

1. **Learns your preferences:** budget, distance (plus "I'd drive 50 miles for an amazing deal"), body type, how long you'll keep the car.
2. **Searches widely** and honestly. When a site blocks automated reading, it asks you to paste the listing instead of working around the block.
3. **Cuts the bad cars:** branded titles, prices too good to be true, sketchy private sellers, and powertrains on a [sourced, dated known-problem list](references/known-problems.md).
4. **Ranks by expected dollars lost:**
   `out-the-door price − estimated resale value at sale + expected repairs`
   It shows the calculation for every car, with a 100-point score explaining why.
5. **Verifies before you drive:** it runs VIN check-digit math, recalls and a photo read itself, and tells you which checks *you* need to do (history report, independent inspection). It never marks anything "verified" that it didn't check.
6. **Builds a hit list:** stops grouped by area, the best car first, questions to text each seller, and when to walk away.
7. **Makes a test-drive card for each car,** covering the universal checks plus that model's known weak point.
8. **Gives you a deal playbook:** negotiate the out-the-door price, handle financing, timing, and private-sale safety.

## Design choices

- **It ranks by dollars lost, not percentage scores.** When the score and the dollars disagree, the dollars win, and it says why.
- **Every check is labelled by who did it:** the agent or the buyer. Honest coverage beats confident guessing.
- **Sourced and dated:** every entry on the known-problem list links to an NHTSA document, a manufacturer bulletin or court records.
- **The buyer decides:** it never contacts a seller without showing you the exact message first, and never signs or pays.
- **US scope, stated plainly:** history reports, recall lookups and dealer laws are US-specific.

## Install

1. Download [`downloads/kick-the-tires.zip`](downloads/kick-the-tires.zip).
2. In Claude, go to **Settings → Capabilities → Skills → Upload skill** and choose the zip.
3. Start a chat: *"Help me find a reliable used car under $12k near Providence that will hold its value."*

## Tested

Built from a real used-car search in Rhode Island, then audited with Jacquard, an independent review skill. The audit found 10 issues: the dollars-lost formula was missing, verification claims couldn't be backed up, the problem list had no sources, US scope was assumed without being stated, and the rubric had no anchors. All 10 were fixed in v1.0.

## Limits

General guidance, not legal or financial advice. Always get an independent pre-purchase inspection. The known-problem list is a starting point. Check the specific VIN.

---

Built by **Courtenay** · [accelerant.studio](https://accelerant.studio) · [LinkedIn](https://www.linkedin.com/in/courtenayo/) · MIT licence
