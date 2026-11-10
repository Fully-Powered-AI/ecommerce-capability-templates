# AI visibility audit for an online store

A store owner or marketer gets a dated audit of how the store reads to AI assistants and shopping agents, from its own saved public pages: eighteen fixed checks with evidence, a fix list in priority order, and a record of what the assistants actually said. Nothing on the store is changed.

*Capability template · E-commerce and retail · Marketing and content · version 0.1.0 · [Capabilities Directory](https://fullypowered.ai/capabilities/ai-visibility-audit-for-an-online-store/)*

## The outcome

You stop wondering whether ChatGPT can see your store and start fixing what is actually in the way. The audit reads the pages an assistant reads: the robots file, the store's guide for shopping assistants, the sitemaps, the policies, the product pages and the structured data behind them. Every check ends in a plain outcome and one sentence of evidence that points to the saved file, so your theme developer can go straight to the line.

Failures arrive as a short fix list in three levels. First, whatever stops an assistant reading the store or its facts at all. Then whatever leaves it little to quote. Then polish. Each fix says who makes it.

The audit is honest about its edges. It keeps apart the two ways a store reaches an assistant's answer, the Shopify Catalog feed and the open web, and says which door is open. A page you did not save is reported as not read, never as a failure or a pass. It never promises that an assistant will recommend you, and gives no score. The one real measurement is your answer check: the questions your buyers ask, put to the assistants on one day, with what each said and which pages it cited. The audit counts that record and keeps it beside the fixes, so next month's audit shows what moved.

## Who starts the work, and when

The store owner, the marketer or whoever runs the store starts it: when someone wonders why assistants never mention the store, whenever the theme or the installed apps change, on either side of a round of fixes, and otherwise each quarter. The answer check runs monthly by default.

That person writes a short facts note, saves the store's public pages or approves the list the assistant reads, and reviews the audit. The owner decides every fix and every choice the audit hands back, such as whether a crawler is kept out on purpose. The assistant reads what it is given. It logs in nowhere, asks for no password and changes nothing on the store.

## What they supply

- **A facts note.** The store's name and address, its product lines, the words buyers use, the facts every product page should state, the questions buyers ask, and who decides and who edits the store. A [store facts file](https://fullypowered.ai/capabilities/store-facts-file/) already holds most of it.
- **The store's public pages, saved on one date,** from a fixed list: the robots file, the guide for shopping assistants, the sitemaps, the home page, the policies, the FAQ or guide page and a sample of product pages. With the list goes a note of which pages failed to load.
- **The Shopify Catalog status,** copied from the store's admin with the date, for a Shopify store.
- **The answer-check sheet,** when you have filled one: each buyer question asked of each assistant, with whether the store was named and which pages were cited.
- **The last audit,** if there is one, to compare.

## What comes out

One dated audit, in a fixed order:

1. **In short:** the answer check's result, the number of fixes at each priority, and whether each route into an assistant's answer is open.
2. **The fix list,** in priority order, each fix with the evidence and the person who acts.
3. **All eighteen checks,** each with its outcome and evidence.
4. **The answer check,** counted: how often the store was named and cited, with questions that name the store counted apart from those that do not.
5. **Tests for a person,** such as opening the store in a private window to see whether a popup covers it.
6. **What changed since the last audit, what the audit cannot see, and exactly what was read.**
7. **A blank answer-check sheet** when the next one is due.

Good looks like this: anyone can check any line against the saved file it names in under a minute, and nothing in the audit claims more than those files show. Fixes to product descriptions and images go naturally to a [product-page facts gap review](https://fullypowered.ai/capabilities/product-page-facts-gap-review/).

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/), where a shopper may put the question to an assistant before ever reaching the store.
- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/), which owns how the store is found and what its pages say.
- [Analytics and reporting](https://fullypowered.ai/functions/analytics-and-reporting/), which keeps the monthly answer check and the audits that compare across dates.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/), with a working store, a catalog and a theme that has collected years of changes nobody has rechecked.

If the site sells nothing online, use the [website findability audit](https://fullypowered.ai/capabilities/website-findability-audit/) instead; it is written for any company's site.

## What has to change for your company

- **Your facts note.** Write it once, keep it current and decide who owns it. The checks compare your pages with your own words, so the note sets the standard.
- **Who decides and who edits.** Name the person who approves changes, the person who edits the theme and the person who edits product pages; each fix is addressed to one of them.
- **How many product pages to read.** Five by default. A store with several page designs should sample each.
- **The answer check.** Choose the assistants your buyers use and the rhythm, monthly by default, and ask from an account that is not connected to the store.
- **Your platform.** The audit is written for Shopify stores. Elsewhere, thirteen of its eighteen checks still apply, and the five that only make sense on Shopify are marked as not run.
- **Saving or fetching.** It is written to run in ChatGPT, Claude, Copilot or Gemini from pages you save. If your assistant can read raw page source, it may fetch the pages itself, after showing you the list.

## What has been checked

Fully Powered AI wrote this capability template. It was editorially reviewed on 9 November 2026. It was tried on its invented example in Claude on 9 November 2026 in two runs: the first, by a model that had not written it, found places where the instructions were open; they were closed, and the second run, recorded with it, was made on the revised version by the model that revised it. A few clarifications made after that run, without a rerun, are listed in its record. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on your own store's saved pages, plus hard cases written in advance, each with its expected behavior: a page that was not saved, a robots rule that shuts out a crawler, a product page with no availability in its structured data, an answer sheet asked from a connected account. A person checks every outcome against the saved files before anyone relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/capabilities/pilot-acceptance-test-preparation/) builds that test set, and [What we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) shows the record.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 9 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 9 November 2026. The record is in [TRIAL.md](TRIAL.md).
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
- [Product-page facts gap review](../product-page-facts-gap-review/)
- [Website findability audit](https://fullypowered.ai/capabilities/website-findability-audit/)

## Make it yours

This is the starting version. Fully Powered AI adapts capabilities to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
