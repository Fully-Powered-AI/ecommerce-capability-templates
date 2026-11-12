# Slow-moving stock and markdown plan

Before a seasonal reset, the merchandiser or store owner gets one plan from the sales and stock exports: each item's sell-through and weeks of cover, the cash tied up in dead and slow stock, and a markdown plan in dated steps with the margin each leaves and a date to stop. The owner decides every price.

*Workflow template · E-commerce and retail · Supply chain and inventory · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflow templates/slow-moving-stock-and-markdown-plan/)*

## The outcome

The end of a season stops being a guess about what to discount and by how much. Every item is placed in one group: dead, slow, on track, too new to judge, or a line you are keeping that holds far more than it sells. Each line shows its sell-through, its weekly sales rate, how many weeks the stock on hand would last, and the cash at cost sitting in it, so the money is visible before anyone talks about percentages.

For every dead or slow item that has to be gone by the reset, the plan lays out the markdown in steps: the date of each step, the new price, the margin it leaves per unit and in per cent, and the margin if every unit sold at that price. No step goes below the margin floor you set, and no step is dated after the stop date, so the last price has time to work before the new range arrives.

Each step after the first comes with a plain check: how many units must have sold since the first markdown by that date. If that many or more have sold, the price holds. If fewer have, the next step is taken. Nobody has to argue about whether the scarves are moving.

The owner approves, changes or holds each item's plan. The AI assistant prepares the figures; it never touches a price in the store.

## Who starts the work, and when

The merchandiser, the buyer or the store owner runs it four to ten weeks before the reset, straight after exporting sales and stock for the season. The same person runs it again on each check date with the units sold since the first markdown, to see which steps to take.

The owner, or whoever decides prices, reads the plan, answers its questions and decides each item separately. Approving the plan for one line and holding another is normal.

## What they supply

- **A sales export:** for each item, units sold over the season so far and over the last four weeks.
- **A stock export:** for each item, units on hand, unit cost, full price, the date it first arrived, and whether it is to be cleared by the reset or kept in the range.
- **The settings:** the stock count date, the reset date, the first markdown date, who decides, and the store's numbers for markdown steps, the margin floor, how close to the reset markdowns stop, and how much cover a kept line may hold.
- **Notes:** items already on markdown, items the owner does not want marked down, and anything else the merchandiser knows.

The export's column headers are checked first. If one does not match, the work stops and asks which column is which.

## What comes out

One plan in a fixed order: a summary of the cash tied up in dead, slow and overstocked lines, the data checks, each group of items with its figures, the markdown plans with an approval line on each, and a numbered list of questions for the owner. A group with nothing in it says "None."

The plan makes no forecast of how many extra units a lower price will sell. It shows what each price leaves in margin and when to check, and the owner chooses. Lines that stay in the range get no markdown; they arrive as questions, with the stock and cash above the limit, because what to do with them is a buying decision as much as a pricing one.

A good plan can be checked line by line against the exports, and the owner can decide it in one sitting.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Supply chain and inventory](https://fullypowered.ai/functions/supply-chain-and-inventory/): sell-through, weeks of cover and the cash held in stock, worked from the store's own exports.
- [Analytics and reporting](https://fullypowered.ai/functions/analytics-and-reporting/): one fixed view of the range before each reset, the same every season, whoever runs it.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/): online and physical stores with seasonal ranges, where last season's stock takes the space and cash the next one needs.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/): brands selling their own products, clearing a season's colors and styles before the next drop.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): when markdowns have always been set by feel and the margin they give away is never counted.
- [Growth and scaling](https://fullypowered.ai/situations/growth-and-scaling/): when the range has grown past what the owner can review item by item from memory.

It sits beside the [inventory reorder plan](https://fullypowered.ai/workflows/inventory-reorder-plan/), which decides what to buy; this plan decides how to clear what has not sold. Raising list prices is the [price change review](https://fullypowered.ai/workflows/price-change-review/), a separate piece of work. The [store facts file](https://fullypowered.ai/workflows/store-facts-file/) records who decides prices.

## What has to change for your company

- **Your export's column headers,** set once so the check passes without a question.
- **Your numbers:** the markdown steps, the margin floor, how many days before the reset markdowns stop, the new-item window and the cover limit for kept lines, perhaps different by category.
- **Your price endings,** if prices must end in .99 or .95, with the margins rechecked at the rounded price.
- **Who decides prices,** and whether a markdown deeper than a set percentage needs a second person.
- **Your end-of-line choices:** whether suppliers take returns, whether you sell to clearance buyers, and where you donate.
- **Your AI product.** It runs in ChatGPT, Claude, Copilot or Gemini from the exports and notes you supply. It needs no connection to your store system, changes no prices and never asks for a password.

## What has been checked

Fully Powered AI wrote this workflow template in its own words, drawing on two published retail methods credited with it. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026, and the record of that run is published with the template; it lists the edits made afterward, which clarify wording the run had to interpret and have not been run again. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a past season your merchandiser remembers well, plus hard cases written in advance, each with its expected behavior: an export with a renamed column, an item that stopped selling a month ago, a step that would fall below the margin floor, a kept line with half a year of stock, an item that arrived last week. The merchandiser checks every price and margin against the exports before the owner decides. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) builds that test set, and [What we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) shows the record.

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
- [Price change review](https://fullypowered.ai/workflow templates/price-change-review/)
- [Store facts file](../store-facts-file/)
- [Pilot acceptance-test preparation](https://fullypowered.ai/workflow templates/pilot-acceptance-test-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
