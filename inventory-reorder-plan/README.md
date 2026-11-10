# Inventory reorder plan

The store owner or buyer gets one plan from the latest sales and stock exports: each item's sales rate, the day it could run out, its reorder point and safety stock, what to order, what is not moving, and a draft purchase order per supplier. Nothing is ordered until a person approves.

*Capability template · E-commerce and retail · Supply chain and inventory · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/inventory-reorder-plan/)*

## The outcome

Reordering becomes a short weekly decision instead of a scramble. Every item lands in one place on the plan: order now, order at the next review, no order needed, not moving, overstocked, or too new to judge. Items that will sell out before a fresh delivery could arrive are marked first, with the number of days they will be empty.

The arithmetic is written out beside each item: the sales rate over four weeks and over the last week, the earliest day the stock could run out, the safety stock, the reorder point, and the quantity in whole supplier packs with its cost. Anyone can check a line with a calculator in a minute and change one number with a reason.

The plan also counts the cash held in stock that is not selling. Items with no sales in four weeks and items holding far more than they sell are listed with the cash in them, and none of them is ever put on an order.

The plan ends with one draft purchase order per supplier and the questions only the owner can answer. The assistant prepares; a person approves each purchase order before it goes anywhere.

## Who starts the work, and when

The buyer, the operations lead or the owner of the store runs it once a week, or as often as the store reviews stock, straight after exporting sales and stock from the store system. It also runs after a stock count, or when a supplier changes its delivery time or minimum order.

The owner, or whoever signs off spending, reads the plan, answers its questions and approves each purchase order separately. Approving one supplier's order and holding another's is normal.

## What they supply

- **A weekly sales export:** units sold by item for the last four weeks, in weeks that end on the day of the stock count.
- **A stock export:** for each item, the supplier, units on hand, unit cost, pack size, units already on order and when they arrive, and the date it first went on sale.
- **Supplier terms:** each supplier's delivery time in days and its minimum order value.
- **The settings:** the date of the stock count, today's date, who approves purchase orders, and the store's numbers for safety days, days of cover per order, how often stock is reviewed and when stock counts as too much.
- **Notes:** days an item was sold out, one-off bulk orders to leave out, and anything else the buyer knows.

The export's column headers are checked first. If one does not match, the work stops and asks which column is which.

## What comes out

One plan in a fixed order: a summary with the total of the draft orders, the data checks, then each group of items with its figures, the draft purchase orders with an approval line on each, and a numbered list of questions for the owner. A group with nothing in it says "None."

Where a supplier's minimum order is not reached, the plan does not pad the order. It shows the smallest additions that would reach it, with their cost and the extra days of stock they buy, and the owner chooses.

A good plan can be checked line by line against the exports, and the owner can approve it in one sitting.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Supply chain and inventory](https://fullypowered.ai/functions/supply-chain-and-inventory/): sales rates, safety stock, reorder points and order quantities, worked from the store's own figures.
- [Operations and process improvement](https://fullypowered.ai/functions/operations-and-process-improvement/): a weekly stock decision on a fixed method, the same every time, whoever runs it.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/): online and physical stores where an empty shelf on a favourite costs orders and a slow line holds cash for months.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/): brands selling their own products, buying from a handful of suppliers with packs, minimums and delivery times.
- [Growth and scaling](https://fullypowered.ai/situations/growth-and-scaling/): when the range has grown past what the owner can reorder from memory.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): when reorder habits set years ago no longer match what sells.

It follows naturally from a [store facts file](https://fullypowered.ai/capabilities/store-facts-file/), which records who approves spending. Choosing a new supplier is [vendor quote comparison](https://fullypowered.ai/capabilities/vendor-quote-comparison/), and paying the bills that follow a delivery is [supplier bill review and payment run preparation](https://fullypowered.ai/capabilities/supplier-bill-review-and-payment-run-preparation/).

## What has to change for your company

- **Your export's column headers,** set once so the check passes without a question.
- **Your numbers:** safety days, days of cover per order, how often stock is reviewed, and the point at which stock counts as too much.
- **Who approves purchase orders,** and whether orders above a set amount need a second person.
- **Your purchase order details:** numbering, delivery address, payment terms, and how an approved order reaches the supplier.
- **How you record sold-out days and one-off bulk orders,** so the notes are ready when the plan runs.
- **Your AI product.** It runs in ChatGPT, Claude, Copilot or Gemini from the exports and notes you supply. It needs no connection to your store system, places no orders and never asks for a password.

## What has been checked

Fully Powered AI wrote this capability template in its own words, drawing on two published inventory methods credited with it. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026, and the record of that run is published with the template; it lists the edits made afterward, including the rounding rule for stock above the overstock limit, which have not been run again. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on two or three past weeks your buyer remembers well, plus hard cases written in advance, each with its expected behavior: an export with a renamed column, an item that was sold out for part of the month, a one-off wholesale order, stock already on order, a supplier minimum that is not reached. The buyer checks every quantity against the exports before anyone approves an order. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) builds that test set, and [What we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) shows the record.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete capability template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the capability drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related capabilities

- [Store facts file](../store-facts-file/)
- [Vendor quote comparison](https://fullypowered.ai/capabilities/vendor-quote-comparison/)
- [Supplier bill review and payment-run preparation](https://fullypowered.ai/capabilities/supplier-bill-review-and-payment-run-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
