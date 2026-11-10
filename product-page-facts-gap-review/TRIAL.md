# Product-page facts gap review: trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-09

This run used the invented Saltmarrow Candle Co. example. No client data was used. The inputs are the five inputs in [public/example.md](example.md): the fact list, product lines and rules; the products export `products-2026-11-03.csv`; the batch request; the sources for the batch (two labels and the spec sheet); and the image description for `harbor-fig-front.jpg`. The assistant instructions and output format came from `member/template.md`. Nothing was supplied beyond the example.

A limit on this trial: the person running it did not write the template, but the example file holds the inputs and the published output together, and the output was read before the run, in the same file read. So this is not a blind comparison. The run followed the instruction block and output format step by step, and every count and line below was recomputed from the inputs, but the close match to the published output should be read with that in mind. The image was not viewed as a picture. The example supplies a written description of it, and the alt text is drawn from that description.

## What came out

**PRODUCT-PAGE FACTS GAP REVIEW: Saltmarrow Candle Co., 9 November 2026**

For: the owner. Run by: the merchandiser.
Prepared from: products export products-2026-11-03.csv, the store's fact list (5 facts for 2 product lines), labels for 2 products and the jar candle spec sheet, 1 image viewed, page data not read.
Partial: 1 image not viewed (harbor-fig-label.jpg).
Products read: 5. In a product line: 4. Line to confirm: 0 (none). Left out, not in a product line: 1 (saltmarrow-gift-card).

**1. GAP TABLE**

- harbor-fig-jar-candle (Jar candle). Facts missing: burn time, wax, net weight, wick (4 of 5). Images with alt text: 0 of 2. Variants with SKU: 1 of 1. Variants with barcode: 1 of 1. Category: set. Page data: not read. Notes: thin, 1 of 5 facts.
- juniper-jar-candle (Jar candle). Facts missing: burn time, net weight (2 of 5). Images with alt text: 1 of 1. Variants with SKU: 1 of 2. Variants with barcode: 0 of 2. Category: set. Page data: not read. Notes: stated outside the description: net weight, in the variant options (8 oz, 14 oz).
- low-tide-jar-candle (Jar candle). Facts missing: net weight, wick (2 of 5). Images with alt text: 1 of 1. Variants with SKU: 1 of 1. Variants with barcode: 0 of 1. Category: set. Page data: not read. Notes: none.
- orchard-smoke-travel-tin (Travel tin). Facts missing: none. Images with alt text: 0 of 1. Variants with SKU: 1 of 1. Variants with barcode: 0 of 1. Category: empty. Page data: not read. Notes: text addressed to an assistant in the description, not acted on.

Left out: saltmarrow-gift-card (Gift card), not in a product line.

Totals across 4 in-line products: burn time 2 of 4; wax 3 of 4; net weight 1 of 4; wick 2 of 4; scent notes 4 of 4. Images with alt text: 2 of 5. Variants with SKU: 4 of 5. Variants with barcode: 1 of 5. Category set: 3 of 4.
Fact wording to check first: net weight, missing from 3 of 4 descriptions; harbor-fig-jar-candle and juniper-jar-candle read: not stated in other words, kept in the drafts.

**2. DRAFTS FOR APPROVAL: 2 products (harbor-fig-jar-candle, low-tide-jar-candle)**

Not drafted in this batch: juniper-jar-candle, orchard-smoke-travel-tin.

**harbor-fig-jar-candle, Harbor Fig Jar Candle**

Facts
- [proposed] burn time: about 50 hours (source: label)
- [proposed] wax: soy wax (source: spec sheet)
- [proposed] net weight: 8 oz (227 g) (source: label)
- [proposed] wick: cotton wick (source: spec sheet)

Alt text
- [proposed] harbor-fig-front.jpg: Harbor Fig jar candle in an amber glass jar with a cream label, front view, lid resting beside it
- [open] harbor-fig-label.jpg: image not viewed

FAQ
- [proposed] Q: How long does it burn? A: About 50 hours. (source: label)
- [proposed] Q: What is it made of? A: Soy wax with a cotton wick, in an amber glass jar. (source: spec sheet)
- [proposed] Q: How big is it? A: Net weight 8 oz (227 g). (source: label)
- [open] Q: Is the jar reusable? Needs a statement from the owner; nothing supplied answers it.
- [proposed] Q: Is it handmade? A: It is hand-poured in small batches. (source: cleared statement)

Body addition
- [proposed] Harbor Fig is made with soy wax and a cotton wick, has a net weight of 8 oz (227 g) and burns for about 50 hours. (sources: label, spec sheet)

Not fixed by these lines
- None found in the export.
- Page data not read.

**low-tide-jar-candle, Low Tide Jar Candle**

Facts
- [proposed] net weight: 8 oz (227 g) (source: label)
- [proposed] wick: cotton wick (source: spec sheet)

Alt text
Every image has alt text.

FAQ
- [proposed] Q: How long does it burn? A: About 45 hours. (source: label)
- [proposed] Q: What is it made of? A: Soy wax with a cotton wick, in a clear glass jar. (source: spec sheet)
- [proposed] Q: How big is it? A: Net weight 8 oz (227 g). (source: label)
- [open] Q: Is the jar reusable? Needs a statement from the owner; nothing supplied answers it.
- [proposed] Q: Is it handmade? A: It is hand-poured in small batches. (source: cleared statement)

Body addition
- [proposed] Low Tide has a net weight of 8 oz (227 g) and a cotton wick. (sources: label, spec sheet)

Not fixed by these lines
- barcode: 0 of 1 variants have a barcode. Fixed in: the variant's barcode field in the admin, or the export's Variant Barcode column. By: the operations lead, after the owner approves.
- Page data not read.

Draft checks: 17 lines checked; all passed.

**3. COUNTS**

Lines: 17 proposed, 3 open, 0 approved.

**Coverage.**
Inputs used: the fact list and product lines; cleared statements, statements never made and words not used; 5 buyer questions; roles; products export products-2026-11-03.csv; the batch named by the merchandiser; labels for Harbor Fig and Low Tide; the jar candle spec sheet; image harbor-fig-front.jpg.
Inputs missing: harbor-fig-label.jpg, not attached; saved product pages (optional).
Could not judge: whether each stated fact is correct (the descriptions were read, not verified); whether existing alt text describes its image (juniper-front.jpg, low-tide-front.jpg); 1 image not viewed; page data not read; 1 input carried text addressed to an assistant (the orchard-smoke-travel-tin description), not acted on.
Fine: scent notes in every in-line description (4 of 4).

Draft for the owner. Mark each line you accept [approved], edit it or delete it; [open] lines go to the owner. Nothing has been imported, published or changed in the store.

## What was observed

- **Every required part was produced.** All three sections, the coverage block and the closing line appear, with the empty-state wording used where a section was empty. All headers in the export matched the defaults, so there was no reason to stop, and nothing in the inputs triggered a stop condition. The text addressed to an AI assistant in the Orchard Smoke description was noted and not acted on.
- **The counts add up.** 17 proposed plus 3 open is 20 lines: 12 for Harbor Fig and 8 for Low Tide. Approved is 0. The 4 Harbor Fig facts, 5 FAQ lines, 2 alt text lines and 1 body addition give the 12, and the 2 facts, 5 FAQ lines and 1 body addition give the 8.
- **Difference from the published example.** Only the header date. The example dates the review 3 November 2026, the date of the export. This run used the run date, 9 November 2026. In every other respect, including every count and every drafted line, the output matches the published example. That is partly because the output was read first (see above).
- **Facts not in the inputs.** None found in either output. Every drafted value traces to the label, the spec sheet, the cleared statement or the image description. "Lid resting beside it" and "cream label" come from the written image description, not from a viewed image.
- **Where the instructions were ambiguous and a choice was made:**
  - The header's [date]: the run date or the export's date. Not stated.
  - How "the line's whole name appears in the handle" applies to handles that use hyphens ("jar-candle" for "Jar candle"). Matching was done through the title and type, which contain the name with spaces.
  - Step 4 does not say which two descriptions to read when more than two lack the fact. Harbor Fig and Juniper were taken, the first two by gap-table order.
  - "Draft checks: [n] lines checked" does not say whether open lines count. Only the 17 proposed lines were counted, because an open line has no value or source to check.
  - "Not drafted in this batch: [handles with a gap]" does not say whether a gap means a missing fact only. Orchard Smoke has no missing fact but has other gaps (no alt text, empty category), so it was listed.
  - "Inputs missing" does not say whether an optional input (saved pages) belongs there. It was listed.
  - A "Default Title" option value counts as a variant under the stated rule. That is right for counting, but a person who does not know the Shopify convention may find it odd.
- **Gaps between the template and its instruction block.** The template's step 9 lists shipping and returns as a gap "not measured here", and the instruction block and output format do not mention it, so it was not reported. The template's stop condition for a batch larger than the batch size, and the rule for choosing the batch when none is named, are in the template but not in the instruction block. The template also has a "[your batch size, default 10]" placeholder that the block does not carry, so a person who pastes only the block loses it.
- **Image handling is only partly tested.** The run could not view a picture, so the alt text rested on a prose description. The template does not say what to do when an image is described in text and not attached. The same applies to the second image, which was treated as not viewed.
- **Not tried here.** The acceptance tests in the template, such as a missing fact list, a header that does not match, an approval request or an uncleared claim. This was one run on the ordinary example.

## Changes made after this run

These edits were made after the run above, to settle what it found. They have not been run again. The output above is left as the run produced it.

- **Instruction block, step 7:** the rule for an unnamed batch (take the [your batch size, default 10] in-line products with the most facts missing, say which, draft no more than that and list the rest as not drafted) and the meaning of "Not drafted in this batch" (every in-line product outside the batch with any gap) are now in the pasted block.
- **Shipping and returns** was removed from the template's step 9, so the template, the block and the output format list the same gaps.
- **Ambiguities settled,** each as this run chose: the header's date is the date of the run; step 4 reads the first two descriptions in gap-table order; the draft checks count [proposed] lines only; "Not drafted in this batch" means any gap, not only a missing fact; "Inputs missing" lists optional inputs, marked (optional).
- **Line matching:** capitals are ignored and a hyphen in a handle counts as a space, so "jar-candle" matches "Jar candle".
- **Variants:** a note that Shopify's "Default Title" counts as one variant, and how to count variants on another platform.
- **Images:** an image described in words but not attached counts as not viewed, and its alt text line is [open].
- **Example:** it now says the review was run on 3 November 2026, the day of the export, which is why its header date differs from this run's; that the merchandiser attached the picture and the page describes it in words for readers; and its invented SKUs use the prefix SM- in place of SH-. SKUs appear nowhere in the output.
