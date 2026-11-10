# Stock count reconciliation

After a physical count, the bookkeeper and the warehouse or store lead get every item counted beside the quantity and value in the books, each difference in units and money, what to check for it, and the items to recount. Nothing is adjusted until a person approves.

*Capability template · E-commerce and retail · Supply chain and inventory · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/stock-count-reconciliation/)*

## The outcome

The count and the books meet one item at a time rather than as a single total at the foot of a spreadsheet. Every stock item gets a line: what was on the shelf, what the books say, the difference in units, and its value at the books' own average cost. Short, over, agreed or needing a bookkeeping answer, each item is in exactly one place.

Each difference comes with a short list of what to look at, in the order a good bookkeeper would look. A delivery on the shelf that was never entered, a customer return back in stock, damaged goods pulled aside and never written off, a grey item counted as the blue one. Where the receiving, returns or damage notes already account for a difference, the reconciliation says so and shows which note. Unexplained loss is the last thing on the list, never the first, and no person is ever named.

Then it says what to count again before anyone touches the books, largest money first, and sets out each possible booking or adjustment with a blank approval line. The books change only when a person approves and enters it.

If the books keep no stock items at all, it says that plainly and stops. If the books' report will not open or stops part-way, it stops there too, rather than reporting that there is no stock.

## Who starts the work, and when

The bookkeeper starts it after a physical count: at month end, quarter end or year end, after a spot count of a few shelves, or whenever the shelves and the books seem to disagree. The warehouse or store lead supplies the count sheet and the movement notes and does the recounts it lists. It runs again on the recounted figures before anything is approved.

The owner, or whoever signs off stock adjustments, reads the actions and approves or holds each one.

## What they supply

- **The count sheet:** each item counted, with its location, quantity and the unit it was counted in.
- **The book stock report** for the count date, from the accounting or stock system: quantity and value for each item.
- **The stock item list:** every item the books track as stock, inactive ones included, so an item a report quietly leaves out still gets compared.
- **The settings:** when the count was made, whether it was a full count or a partial one, which locations were counted, unit conversions such as cartons to single units, the currency, who approves, and the business's recount levels.
- **Movement notes,** if kept: receipts, customer returns, damage, transfers and samples around the count date, each marked as entered in the books or not.

Each file's column headers are checked before anything else. If one does not match, the work stops and asks which column is which.

## What comes out

One reconciliation in a fixed order: a header that states the basis of the comparison, a summary with the net difference, any problems found in the files, every item line by line, what to check for each difference, bookkeeping queries, items counted but not in the books, items in the books but not counted, the recount list, the actions for the approver, and numbered questions for the bookkeeper. An empty section says "None."

Every figure can be traced to the count sheet, the book stock report or a movement note, and the bookkeeper can recheck any line with a calculator.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Supply chain and inventory](https://fullypowered.ai/functions/supply-chain-and-inventory/): the count is where the warehouse finds out whether its records hold up.
- [Finance and accounting](https://fullypowered.ai/functions/finance-and-accounting/): for a business that holds stock, it is often one of the largest figures on the balance sheet, and the books are only as good as the last count behind them.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/): online and physical stores where returns, damaged parcels and deliveries booked late pull the books away from the shelves.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/): brands holding their own finished goods, often across a warehouse and a fulfilment partner.
- [Manufacturing](https://fullypowered.ai/industries/manufacturing/): raw materials and finished goods counted against the books before the period closes.
- [Logistics and trade](https://fullypowered.ai/industries/logistics-and-trade/): distributors and wholesalers whose margin depends on stock they can find.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): when the year-end count has always meant a long weekend with a spreadsheet.
- [Growth and scaling](https://fullypowered.ai/situations/growth-and-scaling/): when more items, more locations and more people handling stock make the gaps harder to spot by eye.

It sits naturally beside the [month-end close checklist](https://fullypowered.ai/capabilities/month-end-close-checklist/), for a business that makes the stock count one of its close tasks, and the [inventory reorder plan](https://fullypowered.ai/capabilities/inventory-reorder-plan/), which works best on stock figures that have just been reconciled. [Bank reconciliation preparation](https://fullypowered.ai/capabilities/bank-reconciliation-preparation/) does the same careful matching for the bank account.

## What has to change for your company

- **Your export headers,** set once so the column check passes without a question.
- **Your recount levels:** the money value and the share of the book quantity that send an item back to be counted again.
- **Who approves adjustments,** and whether large ones need a second person.
- **Your count units and conversions,** for anything counted in cases, cartons or packs.
- **Your movement logs:** which you keep, and how each marks whether it has been entered in the books.
- **Your AI product.** It runs in ChatGPT, Claude, Copilot or Gemini from the files and notes you supply, with any accounting or stock system that can export them. It needs no connection to your books, changes nothing in them and never asks for a password.

## What has been checked

Fully Powered AI wrote this capability template in its own words, drawing on one published stock reconciliation method that is credited with this entry. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026, and the record of that run is published with the template. Earlier runs that day and an independent review found a few unclear points; the template and the example were corrected for them before the run recorded there, which is the run on the corrected version and was made by the assistant that applied the corrections. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on one or two past counts your bookkeeper remembers well, with hard cases written in advance: a renamed column, an item missing from the count sheet, a delivery on the shelf that was never entered, two similar items counted under each other's codes, a value in the books with no units behind it, and an empty item list. The bookkeeper checks every line against the exports before anyone approves an adjustment. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) sets those cases up, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

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

- [Inventory reorder plan](../inventory-reorder-plan/)
- [Month-end close checklist](https://fullypowered.ai/capabilities/month-end-close-checklist/)
- [Bank reconciliation preparation](https://fullypowered.ai/capabilities/bank-reconciliation-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
