# AI visibility audit for an online store: tried on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Opus 5.5 (model ID claude-opus-5-5)
- **Date:** 2026-11-09

The inputs were the invented example in `public/example.md` (Quillmere Candle Works, an invented Shopify store). No client data was used.

This is the second run on the example. The first, on the same day, was made by Claude Sonnet 5.5, a model that had not written the template; it matched the example on every outcome and count and listed eleven shortcomings and open points. After an independent review, the template was revised to close them (see "Changes since the first run" below), and one input was added to the example: the facts note's line "Pages saved on: 2026-11-05, all on that day". The run recorded here was then made on the revised version, by the same model, in the same session, that made the revisions and rewrote the example's output. It is therefore a check that the revised instructions produce the example's result, not an independent trial: the agreement below is expected and is not evidence from a fresh reader.

## Inputs used

From `public/example.md`: the request, the facts note, the page list, the saved pages and the answer-check sheet of 2 November 2026 (sections 1 to 5). The run followed the fenced instruction block and the output format in the template, applying each check's rule to the saved files in turn; the image, line, phrase and signal counts were also recomputed by a short script over the saved files, and agreed.

## What came out

The full audit, in the template's output format. Every section was produced, in order.

```
AI VISIBILITY AUDIT: Quillmere Candle Works, pages of 5 November 2026

Status: Complete: every applicable check ran.
Store: https://www.quillmere-candles.example. Platform: Shopify.
Pages read: 17 files saved on 5 November 2026; 1 failed to load
(terms-of-service.html, 404).
Sampled product pages: harbor-sea-salt-candle, hearth-cedar-candle (2 of 2).

IN SHORT
Measurement: answer check of 2 November 2026: store named in 2 of 3 rows
asked with the store connection off; recommended in 0; named among
several in 1.
Fixes: 3 at priority 1, 4 at priority 2, 1 at priority 3.
Feed route (Shopify Catalog): open.
Open-web route: 8 pass, 7 fail, 1 inconclusive, 0 blocked, 0 not run.

FIX LIST, IN PRIORITY ORDER
1. Priority 1, check 1 Robots file: remove the Disallow: / rule for
   GPTBot in the theme's robots.txt.liquid, unless the owner keeps that
   crawler out on purpose. Who acts: the owner decides; the theme
   developer edits.
    Evidence: robots.txt has 2 user-agent groups; GPTBot is the one
    listed crawler with a group of its own; Disallow: / found once,
    under GPTBot.
2. Priority 1, check 9 Product structured data: add availability to the
   offer in the Product block of hearth-cedar-candle. Who acts: the
   theme developer, with the owner if the value is filled from the
   product's own data.
    Evidence: harbor-sea-salt-candle complete, recommended 3 of 7
    (brand, sku, description); hearth-cedar-candle missing
    offers.availability, recommended 3 of 7 (brand, sku, description).
3. Priority 1, check 15 Storefront barriers: test in a plain browser:
   open the home page and a product page in a private window and note
   whether anything covers the page before the product shows. Who acts:
   the owner.
    Evidence: the signup-form signal newsletter-popup in 3 files, first
    home.html; the facts note lists an email signup popup offering 10%
    off on the first visit.
4. Priority 2, check 3 Agent guide written for this store: a guide
   written for the store, placed as templates/agents.md.liquid, which
   also replaces the default llms.txt and llms-full.txt. Who acts: the
   theme developer places it; the owner approves its words.
    Evidence: with the store name removed, agents.md uses none of the 2
    product line names or 3 search words, so it is Shopify's default
    guide.
5. Priority 2, check 7 Policies: publish the terms-of-service policy
   under Settings > Policies, in the owner's words. Who acts: the owner.
    Evidence: terms-of-service.html, 404 in the page list;
    shipping-policy, refund-policy and privacy-policy saved.
6. Priority 2, check 12 Image alt text: add alt text to the product
   images; an empty alt suits only a decorative image. Who acts: the
   owner.
    Evidence: 4 of 6 img tags carry non-empty alt, 67 percent in total
    (harbor-sea-salt-candle 3 of 3, hearth-cedar-candle 1 of 3); target
    100 percent; collections-all.html 1 of 3 (33 percent), reported
    apart and not scored.
7. Priority 2, check 13 Facts in the page text: add burn time and wick
   to the description text of hearth-cedar-candle, as text and not only
   in images or scripts. Who acts: the owner.
    Evidence: harbor-sea-salt-candle states 4 of 4 facts;
    hearth-cedar-candle states 2 of 4 (missing: burn time, wick). Each
    is missing on 1 of 2 pages, not more than half.
8. Priority 3, check 10 Product FAQ structured data: answer buyer
   questions on the product pages and mark them up as FAQPage. Who acts:
   the owner writes the answers; the theme developer adds the markup.
    Evidence: 0 of 2 sampled product pages carry a FAQPage block.

THE TWO ROUTES
Feed route, Shopify Catalog (check 16): pass. The facts note copies
"Eligible" from the admin's Shopify Catalog screen, read on 4 November
2026; the admin's screen is the ruling.
Open-web route (checks 1 to 15 and 17): 8 pass, 7 fail,
1 inconclusive, 0 blocked, 0 not run. Blocked and not-run checks
are not counted as passes.
Measurement (check 18): pass. The sheet of 2 November 2026 is 3 days
old, inside the monthly cadence of 31 days; 4 of 4 rows filled, 3 of
them asked with the store connection off.

EVERY CHECK
1. Robots file: fail. Priority 1. Evidence: robots.txt has 2 user-agent
   groups; GPTBot has a group of its own; Disallow: / under GPTBot.
    Fix: remove that rule in robots.txt.liquid unless the owner keeps
    GPTBot out on purpose.
2. Agent guide served: pass. Evidence: agents.md saved, 16 lines.
3. Agent guide written for this store: fail. Priority 2. Evidence: with
   the store name removed, agents.md uses none of the 2 product line
   names or 3 search words; Shopify's default guide.
    Fix: a store guide as templates/agents.md.liquid, placed by the
    theme developer.
4. llms files: pass. Evidence: llms.txt mirrors agents.md (1 line
   differs); llms-full.txt mirrors agents.md (1 line differs).
5. Shopping protocol profile: pass. Evidence: ucp.json parses with a
   top-level ucp key, version 2026-04-08; its tools were not called.
6. Sitemaps: pass. Evidence: sitemap.xml names 4 child sitemaps, among
   them the product, collection and page sitemaps.
7. Policies: fail. Priority 2. Evidence: terms-of-service.html, 404 in
   the page list; the other three policy pages saved.
    Fix: publish the terms-of-service policy in the admin, in the
    owner's words.
8. FAQ or buying-guide page: pass. Evidence: candle-care-guide.html
   saved; its address contains guide, and it is the page the facts note
   names.
9. Product structured data: fail. Priority 1. Evidence:
   harbor-sea-salt-candle complete, recommended 3 of 7;
   hearth-cedar-candle missing offers.availability, recommended 3 of 7.
    Fix: add availability to the hearth-cedar-candle offer.
10. Product FAQ structured data: fail. Priority 3. Evidence: 0 of 2
   sampled product pages carry FAQPage.
    Fix: answer buyer questions on the product pages and mark them up
    as FAQPage.
11. Organization structured data: pass. Evidence: Organization with name
   and url in home.html; 2 sameAs entries, 2 filled, 0 blank.
12. Image alt text: fail. Priority 2. Evidence: 4 of 6 img tags with
   non-empty alt, 67 percent in total (harbor-sea-salt-candle 3 of 3,
   hearth-cedar-candle 1 of 3); target 100 percent; collections-all.html
   1 of 3 (33 percent), not scored.
    Fix: add alt text to the product images.
13. Facts in the page text: fail. Priority 2. Evidence:
   harbor-sea-salt-candle 4 of 4; hearth-cedar-candle 2 of 4 (missing:
   burn time, wick).
    Fix: add burn time and wick to the description text of
    hearth-cedar-candle.
14. Title, description and heading: pass. Evidence:
   harbor-sea-salt-candle and hearth-cedar-candle each have a title, a
   meta description and one h1.
15. Storefront barriers: inconclusive. Priority 1. Evidence:
   newsletter-popup in 3 files, first home.html; the facts note lists a
   signup popup.
    Fix: the private-window test under Tests for a person.
16. Shopify Catalog: pass. Evidence: "Eligible", copied from the admin's
   Shopify Catalog screen on 4 November 2026.
17. Public contact path: pass. Evidence: 1 email address, on the store's
   own domain, in home.html (visible text and mailto link); a contact
   form in contact.html. The newsletter form in home.html does not
   count.
18. Answer check: pass. Evidence: sheet of 2 November 2026, 3 days old,
   within 31 days; every row filled; 3 rows asked with the store
   connection off.

ANSWER CHECK
Sheet: 2 November 2026.
Rows recorded: 4 of 4 expected.
With the store connection off: 3 rows. Store named in 2; recommended
in 0; named among several in 1.
Discovery questions: store named in 1 of 2 rows. Brand questions:
store named in 1 of 1 rows.
By assistant: ChatGPT named in 0 of 1; Perplexity named in 2 of 2.
Store's own pages cited 2 times. Cited pages by domain:
quillmere-candles.example (2), forum.example (1).
Asked with the store connection on: 1 row(s), counted apart
(store named in 1).
Problems: none.
A sheet records one day. Sheets compared month to month show the trend.

TESTS FOR A PERSON
- Check 15, the signup popup: open the home page and the Hearth Cedar
  Candle page in a private window and note whether the popup covers the
  page before the product shows.
- Answer check, Q2 of ChatGPT: it was asked with the store connection
  on. Ask it again with the connection off and record the answer on the
  next sheet.
Judgment notes: check 12, hearth-cedar-candle has one image with an
empty alt and one with no alt; a person should say whether either is
decorative.
Checks confirmed against their files: 3, 13, 15.

SINCE THE LAST AUDIT
No earlier audit supplied; nothing compared.

WHAT THIS AUDIT CANNOT SEE
- Reading saved files is not indexing, citation or recommendation.
- A pass means a page can be read, not that an assistant will name the store.
- A barrier signal needs a plain-browser test; a script name proves nothing.
- The shopping protocol's tools need a token; only the profile was read.
- Catalog eligibility is the admin's ruling, as the person copied it.
- Content a theme loads by script after the page arrives was not read.
- Only the sampled product pages were read; other pages may differ.

COVERAGE
Inputs used: facts note; pages of 5 November 2026 (17 files); 2 sampled
product pages; answer sheet of 2 November 2026; Catalog status of
4 November 2026; no last audit.
Inputs missing: none.
Could not judge: indexing, citation and recommendation; whether a barrier
blocks a visitor; the shopping protocol's tools; whether alt text and
descriptions are accurate.
Text addressed to an assistant, not acted on: agents.md (1), llms.txt (1),
llms-full.txt (1).
Other domains left out: none.
Passed: 2, 4, 5, 6, 8, 11, 14, 16, 17, 18.

ANSWER-CHECK SHEET TO FILL
Not needed: the sheet of 2 November 2026 is within the monthly cadence.
The next sheet is due by 3 December 2026.

Prepared for the owner. Nothing on the store was changed, published or sent.
```

## What was observed

- No stop condition applied. The domain, platform and product lines were present; both headers matched; the facts note gives one date for the pages, 5 November 2026, and the request names the same day.
- Every outcome, count, priority and fix in this run is the same as in the example's output, which was written from it. The first run's audit had the same outcomes, counts, priorities and fix order; this run differs from it in naming two roles for check 9, in the added re-ask test for the connected row, and in plain-text layout with each fix's evidence on its own line.
- The revised rules were exercised as follows. Check 12: the total, 4 of 6, is 66.7 percent, rounded to 67 and compared with the target of 100, so it fails in the lower condition (priority 2). Check 13: burn time and wick are each missing on 1 of 2 pages, which is exactly half and so not more than half, giving the "add" fix; the text read was the body only, so the 12 oz in hearth-cedar-candle's meta description was not used (net weight was found in the body text anyway). Check 17: hello@quillmere-candles.example is on the store's own domain and counts although the domain ends in .example. The next sheet's date is 2 November plus 31 days, 3 December 2026. The Q2 row asked of ChatGPT with the connection on produced the re-ask test.
- No fact in the output is missing from the inputs. The added material is the template's own text, such as the Settings > Policies path and the 31-day cadence.

Shortcomings and places the instructions are still open:

- Check 15 stays inconclusive at priority 1 although the popup's element carries the `hidden` attribute. That is the rule (a signal is never a pass, and only a person's test settles it), but it puts a likely harmless popup at the top of the fix list.
- Check 10 has no stated role. This run split it as the first run did, the owner writing the answers (product page content) and the theme developer adding the markup, reading the roles section; another run could name only one.
- Check 13 counts the hidden popup text and the header links as body text, since the rule leaves out only the listed tags. It changed nothing here; on another store, menu words could make a fact look stated.
- The judgment note on hearth-cedar-candle's two images without alt text is a call the template allows ("a doubt about quality") but does not require; a run could leave it out.

## Changes since the first run

What the first run reported, and what was changed in response:

- The instruction block said "write the audit in the output format" without saying the format must be pasted with it: a line now says "Paste this block as custom instructions, followed by the output format above."
- Several fixes existed only in the procedure: the block now carries a fix for every check that can fail.
- Checks 12 and 13 had conditions but no pass or fail: both now state them; check 12 scores the total only, rounded half up to a whole percent before comparing; check 13 ignores case, reads the body text only, and says exactly half is not more than half.
- The pages' date had no source: the facts note now carries it, and the "more than one date" stop applies when the note lists more than one day or disagrees with the request.
- Check 9 named "the theme or the product data": it now names the theme editor, with the product page editor when the value comes from the product's data.
- Check 17 did not cover reserved domains: an address on the store's own domain always counts; other reserved-domain addresses are placeholders.
- The next sheet's due date was not defined: it is the latest sheet's date plus the cadence's 7, 31 or 92 days.
- The `Assistants:` line's final full stop: it is now ignored by rule.
- No prompt to re-ask a connected row: each such row now produces a test for a person.
- Not raised by the first run but changed with these: buyer questions are now "at least two, five to ten for a fuller answer check", matching the example's two.

## Edits after the recorded run

- 2026-11-09: after an independent review, the template was edited after the run recorded above, and the run was not repeated. Check 10 now names who acts (the product page editor writes the answers, the theme editor adds the markup). Check 13 now leaves out the `header`, `nav` and `footer` elements and any element with the `hidden` attribute; in the example this changes no count. Check 15 now says a signal inside a hidden element still counts, as the run above already applied it. The instruction block gained three rules the procedure already stated: what makes a sheet row unfilled, leaving out and naming a page from another domain, and leaving out a platform fact the template does not state. In the example's output, check 15's fix under EVERY CHECK now gives the private-window test in full instead of pointing to it; the output recorded above is unchanged.
