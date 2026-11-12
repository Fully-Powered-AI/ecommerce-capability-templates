# Product landed cost worksheet

After an import shipment lands, the owner or bookkeeper gets one worksheet: freight, duty, brokerage, insurance and inbound fees from the invoices spread over each product by a stated method, the landed unit cost beside the cost the store records, and the margin left. A person updates any cost.

*Workflow template · E-commerce and retail · Supply chain and inventory · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/product-landed-cost-worksheet/)*

## The outcome

Every imported product carries its true cost, not just the factory price. Once a container is in the warehouse and the invoices are in, the worksheet gathers every charge the shipment ran up, from ocean freight to the receiving fee, and places each one on the products that caused it, by the method the store chose: value, units, weight or volume.

What comes back is the landed cost of one unit of each product, written out so anyone can follow it with a calculator. Beside it sits the cost the store has on record today, the difference, and the gross margin the current selling price leaves at each. Products whose cost has moved more than the store's chosen percentage are flagged, and so is any product the store holds with no cost at all, which its margin reports have been counting as pure profit.

Duty is recorded exactly as the broker's entry shows it, product by product. The worksheet never decides how goods are classified, what duty should have been or any other customs question. Those go to the customs broker, written up with the facts from the entry. The owner approves the new costs, and the bookkeeper enters them.

## Who starts the work, and when

The owner, the operations lead, the buyer or the bookkeeper of an online store that imports its products runs it once a shipment has been received and its charge invoices have arrived, before the new stock starts selling where possible. It runs again, as a new version, when a late invoice for the same shipment turns up, and never counts a charge twice.

The owner reads it, answers its questions and approves the costs to enter. The bookkeeper enters them in the store and records the shipment in the books.

## What they supply

- **The supplier's invoice lines** for the shipment, as an export: each product's units and unit price, plus unit weight or volume when a charge is spread that way.
- **The receiving record:** units received of each product.
- **The store's cost export:** each product's recorded cost, selling price and units on hand before the shipment.
- **The charge invoices:** the forwarder's freight invoice, the cargo insurance, the customs broker's entry and invoice, and any port or receiving fees.
- **The settings:** the method for each type of charge, the store's costing method, the taxes the books reclaim, exchange rates where an invoice is in another currency, the cost change worth flagging and the lowest margin the owner accepts.
- **Notes:** anything the owner wants put to the broker.

The export's column headers are checked first. If one does not match, the work stops and asks which column is which.

## What comes out

One worksheet in a fixed order: a summary, the checks, a register of every invoice line and where it went, the split of each charge with its arithmetic, the landed unit cost of each product, the comparison with the recorded cost and the margins, questions for the broker and for the owner, and a draft list of costs to enter with an approval line. A section with nothing in it says "None."

The worksheet stops rather than guesses when units received do not match the invoice, an invoice is in a currency with no rate given, a charge fits no known type or the broker's figures disagree with each other.

In a good worksheet every charge ties back to the invoices to the cent, and the owner can approve it in one sitting.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Supply chain and inventory](https://fullypowered.ai/functions/supply-chain-and-inventory/): the cost of each unit of stock, built up from the shipment that brought it.
- [Finance and accounting](https://fullypowered.ai/functions/finance-and-accounting/): the stock value for the books and the gross margin by product, worked out the same way every time.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/): online stores that import what they sell and price it from a cost they can trust.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/): brands that have their products made abroad and ship them in by container.
- [Logistics and trade](https://fullypowered.ai/industries/logistics-and-trade/): trading businesses that buy overseas and sell online, where freight and duty are a large share of cost.
- [Growth and scaling](https://fullypowered.ai/situations/growth-and-scaling/): when shipments arrive too often to cost by hand in a spreadsheet.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): when product costs were set years ago and freight and duty have moved since.

It sits beside the [inventory reorder plan](https://fullypowered.ai/workflows/inventory-reorder-plan/), which decides what to order next, and [supplier spend analysis](https://fullypowered.ai/workflows/supplier-spend-analysis/), which looks at spend across a whole period. Checking the bills before they are paid is [supplier bill review and payment run preparation](https://fullypowered.ai/workflows/supplier-bill-review-and-payment-run-preparation/).

## What has to change for your company

- **Your export's column headers,** set once so the check passes without a question.
- **Your method for each charge type,** for example freight by weight and insurance by value.
- **Your costing method,** latest landed cost or weighted average, agreed with your accountant.
- **The taxes your books reclaim,** such as import VAT or GST, so they are kept out of product cost.
- **Your flag and your floor:** how big a cost change is worth flagging, and the lowest margin you accept.
- **Who approves and who enters,** and whether a large cost change needs a second approver.
- **Your AI product.** It runs in ChatGPT, Claude, Copilot or Gemini from the files you supply. It needs no connection to your store, your books or your broker, changes nothing and never asks for a password.

## What has been checked

Fully Powered AI wrote this workflow template in its own words, drawing on a published cost-tracking method credited with it. It was editorially reviewed on 10 November 2026. It was tried on its invented example on 10 November 2026 in two runs in Claude, the second after small clarifications to its instructions; the record is published with it and notes that both runs followed a clean path, so none of the stop conditions was exercised. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on two or three past shipments your bookkeeper has already costed, plus hard cases written in advance, each with its expected behavior: a renamed column, a short delivery, duty passed on by the broker as well as shown on the entry, an invoice in another currency, a late receiving invoice. The bookkeeper checks every figure against the invoices before anyone approves a cost. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) builds that test set, and [What we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) shows the record.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 10 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 10 November 2026. The record is in [TRIAL.md](TRIAL.md).
- Not yet tested in a client environment.

## What is in this folder

- [TEMPLATE.md](TEMPLATE.md): the complete workflow template. Roles, inputs, the procedure, exceptions and stop conditions, the output format, a reviewer checklist, acceptance tests, the instructions for an AI assistant and what to customize.
- [EXAMPLE.md](EXAMPLE.md): a worked example with invented data.
- [TRIAL.md](TRIAL.md): what came out when the template was tried on its example.
- [SKILL.md](SKILL.md): the technical file, for AI products that load packaged instructions from a folder.
- [SOURCES.md](SOURCES.md): what the workflow template drew on, with licences.
- [LICENSE](LICENSE): MIT. Use it, change it, make it yours.

## Start using it

1. Read [EXAMPLE.md](EXAMPLE.md) to see what a good result looks like.
2. Open [TEMPLATE.md](TEMPLATE.md) and set every item under "What to customize" to your own rules, roles and limits.
3. Give your AI assistant the instruction block and the output format from the template, with your own limits in place of the ones the instructions leave open in square brackets. Paste them in as custom instructions in ChatGPT, Claude, Copilot or Gemini, or copy this whole folder into a product that loads `SKILL.md` packages. This folder stands alone; you do not need the rest of the repository.
4. Run it on past work first, using the reviewer checklist and acceptance tests in the template, before anyone relies on it.

## Related workflow templates

- [Inventory reorder plan](../inventory-reorder-plan/)
- [Supplier spend analysis](https://fullypowered.ai/workflows/supplier-spend-analysis/)
- [Supplier bill review and payment-run preparation](https://fullypowered.ai/workflows/supplier-bill-review-and-payment-run-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
