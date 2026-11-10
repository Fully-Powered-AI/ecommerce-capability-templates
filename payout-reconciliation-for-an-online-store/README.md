# Payout reconciliation for an online store

Each month the bookkeeper gets every payout from the store's processors and marketplaces taken apart and tied to the bank: the orders, refunds, chargebacks and fees inside it, each fee checked against the agreed rate, every difference listed with its evidence. A person posts the entries and raises any dispute.

*Capability template · E-commerce and retail · Finance and accounting · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/payout-reconciliation-for-an-online-store/)*

## The outcome

A payout is a single number that hides a month of activity. Sales go in; refunds, chargebacks, the channel's fees, advertising and any money held back come out; whatever is left lands in the bank a day or two later. This capability opens every payout up and accounts for each part of it.

Each sale and refund is matched to its order. Each payout is added up from its own lines and found in the bank. Each fee is worked out again from the rate the channel published or agreed with you, so an overcharge of a few cents on one card payment is caught as surely as a wrong commission rate on a marketplace sale. Each channel gets one line that runs from gross sales down to the money paid out, and it either ties or shows the gap.

What does not fit is listed, numbered, with the row or line that shows it: a deposit nobody can place, an order that was paid for and never paid out, a fee above the rate. Where two differences look like the same event, the pack says so and leaves both on the list for a person to confirm.

The bookkeeper gets the figures for the month's entries by channel, and the owner gets the fee differences ready to raise. The AI assistant posts nothing, raises nothing, writes to no channel and settles no difference.

## Who starts the work, and when

The bookkeeper, or whoever runs the store's finances, starts it after the month ends, once the payout reports and the bank statement are in, and before the month is closed. It runs again if a missing report or a corrected export turns up.

The owner or finance lead reviews the pack and approves it. A person posts the entries and decides whether any fee difference is worth raising.

## What they supply

- **The payouts list** for the month from every processor and marketplace, and **each channel's payout report** line by line.
- **An order export** from the store's platform.
- **The bank statement export** for the account the payouts reach.
- **The fee schedule** for each channel, with where each rate comes from and its date.
- **Last month's open items:** payouts still on their way, orders not yet paid out, differences still open.
- **A few settings:** who prepares, approves, posts and decides on disputes; each channel's name on the bank statement; how long each channel usually takes to pay out a sale; how many business days a payout may take to arrive.

The capability names the column headings it expects in each export. If yours differ, it stops and asks which column is which rather than guessing.

## What comes out

1. **The result:** payouts, how many reached the bank, fee lines checked, differences found.
2. **A summary for each channel,** from gross sales to the money paid out, with its fee rate as a share of sales and a line that ties.
3. **Every payout and its deposit,** in the bank, still on its way with the date it is due, or not found.
4. **The orders check:** lines matched to orders, orders waiting for their payout, orders missing from every payout.
5. **The fee check,** channel by channel, with every fee above or below the rate.
6. **The differences,** each with its evidence and who looks into it.
7. **Last month's open items,** cleared or still open.
8. **Figures for the entries** by channel, and **the fee differences** for the owner to decide on.
9. **A coverage note** on what was read and what could not be checked.

A good pack lets the bookkeeper post the month and the owner decide on a fee dispute in one sitting.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Finance and accounting](https://fullypowered.ai/functions/finance-and-accounting/): the books should show gross sales and each kind of cost, never just the net sum that reached the bank.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/): a store paid by a card processor and one or more marketplaces has several payout schedules and fee tables to keep straight.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/): a brand selling direct and through marketplaces sees each channel's real cost side by side.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/): when a second channel or a busy season makes checking payouts by eye impossible.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): when the month's payout checks live in one person's spreadsheet and should live in a pack anyone can review.

It is the step before [bank reconciliation preparation](https://fullypowered.ai/capabilities/bank-reconciliation-preparation/), which then ties the whole bank account to the books, and it sits beside [chargeback response pack](https://fullypowered.ai/capabilities/chargeback-response-pack/), which answers a single card dispute.

## What has to change for your company

List the channels you are paid by and how each one appears on your bank statement. Set how long each usually takes to pay out a sale, so an order from the last few days of the month is shown as on its way rather than missing. Enter each channel's fees from its current pricing page, rate card or agreement, with the date, and update it when a channel announces new rates. Decide how small a fee gap is worth listing. Name who prepares, who approves, who posts and who decides on disputes. If your exports use different column headings from the defaults, name them. It is written to run in ChatGPT, Claude, Copilot or Gemini from files you supply, and needs no connection to your store, processors, marketplaces, bank or accounting system.

## What has been checked

Fully Powered AI wrote this capability template in its own words, drawing on two published methods that are credited with it. It was editorially reviewed on 10 November 2026. It was tried once on its invented example in Claude on 10 November 2026; the record of that run is published with it, and lists the ambiguities it met and the small edits made afterward, which have not been run again. That run covered an ordinary month; it did not reach a column heading that does not match, a foreign currency, a payout that does not add up or a request to post or adjust. It has not yet been tested in a client environment, and it has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on two or three past months your bookkeeper has already closed, with hard cases written in advance: an export whose headings differ, a payout on the last business day of the month, a deposit that matches nothing, a refund where the channel keeps part of its fee. The bookkeeper checks every fee difference by hand against the rate before anything is raised. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) builds that test set, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

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

- [Bank reconciliation preparation](https://fullypowered.ai/capabilities/bank-reconciliation-preparation/)
- [Chargeback response pack](../chargeback-response-pack/)
- [Month-end close checklist](https://fullypowered.ai/capabilities/month-end-close-checklist/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
