# Swiggy Smart Handoff (Concept Prototype)

An interactive product concept that improves last-mile delivery in gated residential societies, such as apartment complexes with multiple entrances.

> **Disclaimer:** This is an independent concept prototype for product thinking and portfolio purposes. It is not an official Swiggy product and does not use real Swiggy data, GPS, payments or backend services.

**Live demo:** https://swiggysmarthandoff.vercel.app/

## The problem

In gated societies, delivery partners often reach the wrong or a closed gate, get stuck, call the customer repeatedly, and arrive late. Customers re-enter the same address and gate instructions on every order, and have no idea why their delivery has slowed down.

## The concept

Smart Handoff works as an intelligent layer inside the existing ordering journey, not as an extra process.

- **Saved access preferences:** society, tower, flat, preferred gate and instructions are entered once and reused automatically.
- **Recommended entrance:** a suggestion based on recent, anonymised delivery reports (for example, "Gate C may be the easiest entrance right now"), with one-tap acceptance.
- **Clear ETAs:** society arrival and doorstep arrival are shown separately.
- **Access issue handling:** if a gate is blocked, the customer is notified, the route switches to an alternative gate and the doorstep ETA updates.
- **Community-powered intelligence:** partner reports feed back into future recommendations. Reports are treated as recent signals, not guaranteed live facts, and conflicting reports lead to a cautious recommendation.

## Prototype scope

Six screens across two views:

| View | Screens |
|---|---|
| Customer | Smart Handoff at checkout, recommended entrance, live tracking, access issue notification |
| Delivery partner | Delivery access details with society map, alternative route and handoff |

Scenario: Green Valley Society, Sector 62, Noida. Customer address Tower 4, Flat 803. Gate A (main), Gate B (east, usually closed after 10 PM), Gate C (service). Road C is under construction.

## Demo walkthrough

1. In the **Customer** view, check the saved details and tap **Review entrance**.
2. Accept **Use Gate C**.
3. Switch to **Delivery partner**. The partner starts near Gate A.
4. Tap **Gate blocked**. The partner is rerouted to Gate C.
5. Switch back to **Customer**. The access update appears and the doorstep ETA moves from 8:40 PM to 8:50 PM.
6. In the partner view, tap **Complete handoff**.
7. Tap **Reset demo** to start again.

Use **Simulate first-time user** on the checkout screen to see the empty preference form.

## How it works

- Shared in-memory state keeps the customer and partner views in sync.
- A simple rules engine ranks gates from recent reports, flags conflicting reports and suggests an alternative gate when one is blocked.
- Saved preferences and simulated reports are stored in the browser's local storage.
- The society map is a stylised SVG, with no external map APIs.

## Tech

Single-file static site: plain HTML, CSS and JavaScript. No build step, no dependencies, no backend.

## Run locally

Open `index.html` in any modern browser.

## Deploy

Hosted on Vercel as a static site. To deploy your own copy, import the repository at vercel.com/new, set the Framework Preset to **Other** and leave the build settings empty.

## Author

Built by Jaspreet as a product concept exercise.
