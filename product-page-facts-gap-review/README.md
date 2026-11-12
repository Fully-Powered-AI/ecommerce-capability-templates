# Product-page facts gap review

Product by product, your merchandiser sees what a shopper's AI assistant needs from each page and does not get: facts the description leaves out, images with no alt text, buyer questions left unanswered. Each gap comes with a sourced draft to fill it, waiting for the owner's approval.

*Workflow template · E-commerce and retail · Marketing and content · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflows/product-page-facts-gap-review/)*

## The outcome

When a shopper asks an AI assistant which candle, kettle or running shoe to buy, the assistant can only repeat what your product pages say. This review shows you, page by page, where it comes up empty. You see which of your own must-state facts each description leaves out, which images have no alt text for the shopper who cannot see them, and which of your buyers' usual questions the page never answers.

You also get the fix, ready to read. For the products you pick, every missing fact arrives with its value and the label or specification sheet it came from. Alt text, short answers to buyer questions and one plain paragraph of facts to add after your own copy come with it. Where nothing you supplied settles a point, the line is a question for the owner, not a guess. The things words cannot fix, such as a missing barcode or a theme that leaves out product markup, are listed with who fixes each.

Nothing reaches your store without you. The owner marks each line approved, edits it or deletes it, and a person puts the approved lines in.

## Who starts the work, and when

The merchandiser, or the owner of a small store, starts it when product pages feel thin, before a new range or a catalog push, when shoppers keep asking things the pages should answer, or after a visibility check has flagged weak product pages. Run it again on a fresh export once the approved lines are live, to see what moved.

The owner approves every drafted line and answers the open questions.

## What they supply

- **Your fact list.** For each product line, the facts every page should state and where each comes from: the label, the specification sheet or the owner.
- **Your rules.** Statements you have cleared, statements you never make and words you avoid.
- **Your buyers' questions.** Five to ten, in their own words.
- **Your products export** from the store admin, as a CSV file, or the product descriptions pasted in.
- **The batch.** The products to draft for this time.
- **The sources for that batch.** Labels, packaging text or specification sheets, and the product photos.
- **Optional:** saved copies of the product pages, to check their markup.

## What comes out

1. **A gap table.** Every product in one line each: the facts its description lacks, images with alt text, SKUs and barcodes, and whether the category is set, with the store's totals beneath. Gift cards and merchandise are named and set aside.
2. **Drafts for approval.** For each product in the batch: the missing facts with their sources, alt text for the images, answers to the buyer questions, and one paragraph to add after your description. Every line is marked proposed or open.
3. **What the drafts do not fix,** with where each is fixed and who acts.
4. **A coverage note** saying what was read, what was missing and what could not be judged.

A good review lets the owner check every proposed line against its source in a single sitting.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/): product pages are the store's most-read copy, and the facts on them are what every assistant and search engine repeats.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/): a growing catalog drifts out of step with its labels and specification sheets one product at a time.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/): a brand selling through its own store needs its pages to say what is on the pack.
- [Growth & scaling](https://fullypowered.ai/situations/growth-and-scaling/): when products are added faster than anyone can recheck the pages written last year.

## What has to change for your company

Write your fact list first: the review measures your pages against your list and carries no list of its own. Add the wording your pages already use for each fact, so a fact stated in your own words is not reported missing. Decide who approves product changes, who updates product records and who edits the theme. Set a batch size the owner can read in one sitting. If your platform's export uses different column headings from the defaults, name them. Choose how approved lines reach the store: by hand in the admin, or by an import a person builds from your own export and tries on one product first. It runs in ChatGPT, Claude, Copilot or Gemini from files you supply, and needs no connection to your store.

## What has been checked

Fully Powered AI wrote this workflow template from its own product-facts package, which it publishes openly. It was editorially reviewed on 9 November 2026. It was tried on its invented example on 9 November 2026 in Claude, and the record of that run is published with it. The run was not blind, because the published output had been read before it, and no picture was viewed: the example's one image was given as a written description, so the alt text rests on that description. Small edits made afterward to settle the gaps and ambiguities the run found have not been run again; the record lists them. It has not yet been tested in a client environment, and it has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on a handful of products your merchandiser knows well, with hard cases written in advance: a fact stated in your own words, a label that was not supplied, an image that cannot be viewed, a description that tells assistants what to say. The owner checks every proposed line against its source before anything goes live. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) builds that test set, and [what we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) describes the record we keep.

- Written by Fully Powered AI.
- Sources and rights reviewed.
- Editorially reviewed on 9 November 2026.
- Package format checked by script on every release.
- Tried once on its invented example in Claude on 9 November 2026. The record is in [TRIAL.md](TRIAL.md).
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

- [Competitor profile from public pages](https://fullypowered.ai/workflows/competitor-profile-from-public-pages/)
- [Customer reply drafting](https://fullypowered.ai/workflows/customer-reply-drafting/)
- [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
