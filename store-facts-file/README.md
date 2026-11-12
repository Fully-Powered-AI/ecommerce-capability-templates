# Store facts file

The person who runs an online store builds the one file every other store workflow template reads first: what the store sells, the facts each product page should state, the statements it stands behind, buyers' questions, policies, roles and access. Nothing on the store is changed.

*Workflow template · E-commerce and retail · Marketing and content · version 0.1.0 · [Workflows Directory](https://fullypowered.ai/workflow templates/store-facts-file/)*

## The outcome

Your store gets one source of truth that every piece of AI-assisted work starts from. Product lines in your own words. The facts a careful buyer checks before buying, and how your pages word them. The exact statements you stand behind, and the ones you never make. Your buyers' real questions, the way they really type them. The policy pages, the apps, who approves what, and how later work gets at your data.

Each line says whose word it is: something you said, something read from your own files and confirmed, a default you accepted, or an item left open, which the setup report lists with who checks it and where. So every workflow template that follows, from a product-page review to a reply to a customer, works from your facts instead of guessing, and stops to ask when a line it needs is still open.

The assistant proposes and you decide. Only the statements you clear go into the file; the assistant's own wording is never recorded as yours, and nothing on the store is touched.

## Who starts the work, and when

The owner or the operator, whoever runs the store day to day, starts it once before any other store workflow template, with the owner taking part for the products, the buyers and the statements. It takes one conversation; the file is ready at the end of it, with any open items listed.

It runs again whenever something changes: a new product line, a new policy page, a different reviews app, a role that moves to someone else. A revision touches only the lines that change. The owner approves the file before anything else reads it.

## What they supply

- **You, in the conversation.** The file holds what you say; nothing is drafted in your name.
- **Your store basics,** read from your admin with the date: name, web address, platform and plan, currency, where you sell and ship.
- **A product list export,** if you have one. It suggests your product lines; the column names are checked first, and you are asked if they differ.
- **Text from a few product pages,** if you want the statements on them walked one by one.
- **The links from your storefront footer:** policy pages, FAQ pages, the contact address.
- **Your existing file,** when it is a revision.

## What comes out

Two things, in a fixed order:

1. **The store facts file,** eleven numbered sections: the store, what it sells, statements and words, buyers and their questions, apps and tools, pages and policies, people and roles, access, numbers and rhythms, AI shopping channels, and a dated decisions log. Every line marked.
2. **A setup report:** whether the file is ready, the decisions made today, every open item with what to check, where and who checks it, how the product-page statements were settled, the results of the file's own checks, and exactly which inputs were used and which were missing.

Good looks like this: you can read any line aloud and say "yes, that is us", and the next workflow template never has to ask what you sell.

See the worked example with invented data in [EXAMPLE.md](EXAMPLE.md).

## Where it fits

- [Marketing and content](https://fullypowered.ai/functions/marketing-and-content/): the facts, the words and the cleared statements every product page, campaign and reply draws on.
- [Operations and process improvement](https://fullypowered.ai/functions/operations-and-process-improvement/): one maintained file of roles, approvals, access and thresholds that later store work runs on.
- [E-commerce and retail](https://fullypowered.ai/industries/ecommerce-and-retail/): online stores, where shoppers and their AI assistants judge a product by what its page states.
- [Consumer brands](https://fullypowered.ai/industries/consumer-brands/): brands selling direct, where every claim about the product carries the brand's name.
- [Established businesses](https://fullypowered.ai/situations/established-businesses/): a store that has run for years, with facts spread across pages, apps and one person's memory.

## What has to change for your company

- **Your fields.** Add any line your store needs, such as wholesale terms or gift wrapping, in the section it belongs to.
- **Your export's column names,** set once so the check passes without a question.
- **Your defaults:** whether competitor comparisons are ever allowed, who clears a new statement, your review rhythms and your stock and late-order numbers.
- **Your roles,** including any your store has beyond owner, operator, support and finance.
- **Your platform's names** for its AI shopping screens.
- **Where the file lives** and who keeps it current.
- **Your AI product.** It runs in ChatGPT, Claude, Copilot or Gemini from what you type and the files you supply; it needs no connection to your store and never asks for a password.

## What has been checked

Fully Powered AI wrote this workflow template from its own store-setup work, already public under the MIT licence. It was editorially reviewed on 9 November 2026. It was tried once on its invented example in Claude on 9 November 2026, with the owner's answers read from a written conversation rather than given by a live person; the record is published with it. The rule for open items was changed after that run, and small clarifications were added; the record lists these edits, which have not been run again. It has not yet been tested in a client environment. It has not yet been tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.

Testing in your environment means running it on your own store, plus hard cases written in advance, each with its expected behavior: an export whose column names differ, a page sentence you will not stand behind, a person's name given where a role belongs, a request to change a product in the store. The owner reads the finished file line by line before anything relies on it. [Pilot acceptance-test preparation](https://fullypowered.ai/workflows/pilot-acceptance-test-preparation/) builds that test set, and [What we test before we call an AI workflow ready](https://fullypowered.ai/insights/what-we-test-before-a-workflow-is-ready/) shows the record.

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

- [Customer reply drafting](https://fullypowered.ai/workflow templates/customer-reply-drafting/)
- [Website findability audit](https://fullypowered.ai/workflow templates/website-findability-audit/)
- [Launch checklist](https://fullypowered.ai/workflow templates/launch-checklist/)

## Make it yours

This is the starting version. Fully Powered AI adapts workflow templates to how your company works, proves them on real work and rolls them out to the roles that use them. [Talk with us](https://fullypowered.ai/contact/).
