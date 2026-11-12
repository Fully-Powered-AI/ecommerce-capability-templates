# Store guide for AI shopping assistants

The person who runs an online store gets the plain-language guide a shopper's AI assistant reads about the store: what it sells, for whom, which product line suits which need, and where the policies are. Every line traces to the approved store facts file, and a person places it.

*Workflow template · E-commerce and retail · Marketing and content · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflow templates/store-guide-for-ai-shopping-assistants/)*

## The outcome

When a shopper asks an AI assistant about your store, the assistant has your own description to read instead of a generic one. On Shopify, your store already serves a default guide to these assistants, and it says nothing about what you sell. This workflow template writes the replacement: your business in your own words, your product lines and who each one is for, the facts each product page carries, the statements you stand behind word for word, your policy and help pages, and the things the store never claims.

Every sentence comes from the store facts file you approved, and the report shows where each line came from. No adjective, comparison or benefit gets in that you have not cleared. No email address, phone number or price goes in. And nothing in it asks an assistant to recommend you. Its purpose is accuracy: an assistant that reads it describes your store the way you would.

The draft comes back checked and ready to paste. A person on your team places it, and you decide when it goes live.

## Who starts the work, and when

The operator or the owner starts it once the store facts file is approved, usually right after it. It runs again whenever the facts file changes what you sell, what you claim, who buys or which pages you publish, so the guide never drifts from the file. An AI visibility audit that finds the platform's default guide is another good moment.

The owner reads and approves the guide before anyone places it.

## What they supply

- **Your approved store facts file.** The guide says only what this file carries.
- **A list of your store's page addresses,** copied from your sitemap and footer, so every link in the guide can be checked before it goes live.
- **The text of the guide your store serves today,** if you have it, so the report can say what is being replaced.
- **Your earlier draft,** when it is a revision.

## What comes out

One report, in a fixed order:

1. **The guide,** between two marker lines, ready to paste into your theme.
2. **Where each line came from:** the facts file section behind every sentence.
3. **The checks:** links, contact details, prices, words you avoid, comparisons, and any word that makes a claim, flagged for you rather than quietly changed.
4. **A short list for the owner** to read the guide against: the statements you never make and the words you avoid.
5. **Step-by-step placing instructions** for the person on your team who handles theme files, with how to undo it.
6. **Coverage:** what was used, what was missing and what no check can judge.

Good looks like this: you can read the guide aloud and agree with every line, and nothing in it surprises you.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/): your own description of the store, in your words, reaching every assistant that reads it.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/): online stores, where a shopper's AI assistant may read about the store before the shopper ever visits it.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/): brands selling direct, where every sentence about the product carries the brand's name.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): a store still serving the platform's default guide years after launch.
- [Startups & new ventures](https://fullypowered.ai/situations/startups-and-new-ventures/): a new store that can describe itself accurately to assistants from its first week.

## What has to change for your company

- **Your claim words.** The list of words flagged for the owner, such as "premium" or "best", tuned to your category.
- **Your platform.** It is written for Shopify. On another platform, the file goes where that platform serves a plain-text guide, links are written in full, and the placing steps are your platform's.
- **The shopping rules.** The section on how assistants shop on your store follows Shopify's guidance as Fully Powered AI recorded it on 21 October 2026. Compare it with Shopify's help pages each quarter.
- **Your help pages,** and whether a warranty or subscription page joins the policy list.
- **Your roles,** if someone other than the operator places theme files.
- **Your AI product.** It runs in ChatGPT, Claude, Copilot or Gemini from the files you supply; it needs no connection to your store and never asks for a password.

## What has been checked

Fully Powered AI wrote this workflow template from its own work on store guides, already public under the MIT licence. It was editorially reviewed on 9 November 2026. It was tried once on its invented example in Claude on 9 November 2026; the record is published with it and lists the ambiguities the run found. One run covered only the complete-inputs case. Small clarifications were added after that run, on how policy labels are written, which links are counted and how lines are traced; the record lists these edits, which have not been run again. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on your own facts file, plus hard cases written in advance, each with its expected behavior: a claim word in your own business line, a policy page missing from the address list, a contact address that is only an email, a request to add a line you have not cleared. The owner reads the guide line by line, and the operator opens every link after placing it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) builds that test set, and [What we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) shows the record.

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

- [Store facts file](../store-facts-file/)
- [AI visibility audit for an online store](../ai-visibility-audit-for-an-online-store/)
- [Product-page facts gap review](../product-page-facts-gap-review/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
