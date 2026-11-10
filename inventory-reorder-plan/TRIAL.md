# Inventory reorder plan: a trial on the invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs are the invented example's: its settings, supplier terms, stock export, weekly sales export and notes, in `public/example.md`. No client data was used. The assistant did not write the template. It read the template, then only the example's inputs, ran the instruction block and output format on them, and only then read the example's published output to compare.

**Edited after this run, 10 November 2026.** Following two independent reviews, the template and the published example were edited after the run recorded here, and the run was not repeated. The output and the observations below are left as recorded, so where they describe the template or the example they describe them as they stood at the time of the run. The edits are listed under "Edited after this run" at the end.

## Inputs used

The five inputs under "The inputs" in `public/example.md`: the settings, the supplier terms (3 suppliers), the stock export (9 items), the weekly sales export (30 rows, four weeks ending Sunday 18 October to Sunday 8 November 2026) and the notes (one one-off café order, one sold-out spell, no seasonal change).

## What came out

**INVENTORY REORDER PLAN: the Store, stock counted Sunday 8 November 2026**

- **For:** the owner. Prepared Monday 9 November 2026 from: sales export (weeks ending Sunday 18 October to Sunday 8 November, 30 rows), stock export (9 items), supplier terms (3 suppliers), settings, notes.
- **Column check:** all headers matched.
- **Settings:** safety days 7; days of cover per order 30; review every 7 days, next review Monday 16 November; overstock above 180 days of cover. Defaults used: count age limit 7 days; recent-rate question at 1.5 times the four-week rate.
- **Summary:** 3 draft purchase orders, $3,571.20. Order now: 4 items, 3 SHORT. Order at the next review: 1. No order needed: 1. Not moving: 1, $255.00. Overstocked: 1, $1,140.00, of which $418.00 above the limit. Too little history: 1. Left out by the data checks: 1.

**Data checks**

- TEA-09 is in the sales export (5 units, week ending 25 October) and not in the stock export. Left out of the plan.
- GEAR-02 has no rows in the sales export. Read as no sales.
- GEAR-03 has no row for the week ending 25 October. Read as no sales that week.

**Order now**

- **TEA-01** Breakfast blend tin (Supplier A). Sales: 154 in 28 days in stock = 5.50/day; last 7 days 39 = 5.57/day. On hand 60; nothing on order. Runs out by Wednesday 18 November at 5.57/day (10 days). Lead time 14 days: an order placed today arrives Monday 23 November. SHORT: 5 days with no stock. Safety stock 40 ((5.57 - 5.50) x 14 + 5.50 x 7 = 39.48, rounded up). Reorder point 117 (5.50 x 14 + 40). Stock position 60. Target 282 (117 + 5.50 x 30). Order 228 (222 needed, 19 packs of 12) = $1,482.00.
- **TEA-03** Earl grey tin (Supplier A). Sales: 84 in 28 days in stock = 3.00/day; last 7 days 21 = 3.00/day. On hand 24; 36 on order, arriving Thursday 12 November, counted (it arrives before the 24 on hand run out on Monday 16 November). Runs out by Saturday 28 November at 3.00/day (20 days). Lead time 14 days: an order placed today arrives Monday 23 November. Safety stock 21 ((3.00 - 3.00) x 14 + 3.00 x 7). Reorder point 63 (3.00 x 14 + 21). Stock position 60. Target 153 (63 + 3.00 x 30). Order 96 (93 needed, 8 packs of 12) = $652.80.
- **GEAR-01** Glass teapot 600 ml (Supplier B). Sales: 44 in 28 days in stock = 1.57/day; last 7 days 18 = 2.57/day, at least one and a half times the four-week rate (question 4). On hand 40; nothing on order. Runs out by Monday 23 November at 2.57/day (15 days). Lead time 21 days: an order placed today arrives Monday 30 November. SHORT: 7 days with no stock. Safety stock 32 ((2.57 - 1.57) x 21 + 1.57 x 7 = 31.99, rounded up). Reorder point 65 (1.57 x 21 + 32 = 64.97, rounded up). Stock position 40. Target 113 (65 + 1.57 x 30 = 112.10, rounded up). Order 78 (73 needed, 13 packs of 6) = $1,092.00.
- **FIL-02** Steel tea infuser (Supplier C). Sales: 43 in 22 days in stock = 1.95/day; left out: 6 sold-out days, 26 to 31 October, per the notes; last 7 days 14 = 2.00/day. On hand 12; nothing on order. Runs out by Saturday 14 November at 2.00/day (6 days). Lead time 7 days: an order placed today arrives Monday 16 November. SHORT: 2 days with no stock. Safety stock 14 ((2.00 - 1.95) x 7 + 1.95 x 7 = 14.00). Reorder point 28 (1.95 x 7 + 14 = 27.65, rounded up). Stock position 12. Target 87 (28 + 1.95 x 30 = 86.50, rounded up). Order 84 (75 needed, 7 packs of 12) = $344.40.

**Order at the next review**

- **TEA-02** Green sencha tin (Supplier A). Sales: 61 in 28 days in stock = 2.18/day (85 less the 24-unit one-off café order in the week ending 1 November, per the notes); last 7 days 15 = 2.14/day. Runs out by Friday 4 December at 2.18/day (26 days). Safety stock 16 ((2.18 - 2.18) x 14 + 2.18 x 7 = 15.26, rounded up). Reorder point 47 (2.18 x 14 + 16 = 46.52, rounded up). Stock position 58, above the reorder point and at or below the next-review line of 63 (47 + 2.18 x 7 = 62.26, rounded up): order at the review on Monday 16 November.

**No order needed**

- **FIL-01** Paper tea filters, pack of 100 (Supplier C). Four-week rate 4.50/day (126 in 28 days), recent 5.00/day (35 in 7 days). Stock position 140; reorder point 67; next-review line 99. Runs out by Sunday 6 December.

**Not moving**

- **GEAR-02** Bamboo tea scoop (Supplier B). No sales in the last 28 days; no rows in the sales export. On hand 85 x $3.00 = $255.00. Not reordered.

**Overstocked**

- **GEAR-03** Cast-iron kettle (Supplier B). Sales: 3 in 28 days in stock = 0.11/day. Stock position 30 = 272 days of cover, above 180. Units above the limit: 11 (30 - 0.11 x 180 = 10.20, rounded up) = $418.00. Cash in the item: 30 x $38.00 = $1,140.00. Not reordered.

**Too little history**

- **GEAR-04** Tea tray (Supplier B). On sale since Tuesday 27 October (13 days). Sales so far: 6 in the week ending 1 November, 9 in the week ending 8 November. On hand 25. No rate, date or order given. Can be rated from Monday 23 November.

**Draft purchase orders**

DRAFT, NOT SENT. **Supplier A.** PO number: to be assigned. Order date: Monday 9 November 2026, if approved today. Requested delivery: Monday 23 November 2026 (14-day lead time).

- TEA-01 Breakfast blend tin: 228 (19 packs of 12) at $6.50 = $1,482.00.
- TEA-03 Earl grey tin: 96 (8 packs of 12) at $6.80 = $652.80.
- Total: $2,134.80. Prices: last cost in the stock export as of Sunday 8 November 2026; supplier to confirm. Minimum order $300.00: reached.
- Approved to send: ______________ Date: ________

DRAFT, NOT SENT. **Supplier B.** PO number: to be assigned. Order date: Monday 9 November 2026, if approved today. Requested delivery: Monday 30 November 2026 (21-day lead time).

- GEAR-01 Glass teapot 600 ml: 78 (13 packs of 6) at $14.00 = $1,092.00.
- Total: $1,092.00. Prices: last cost in the stock export as of Sunday 8 November 2026; supplier to confirm. Minimum order $400.00: reached.
- Approved to send: ______________ Date: ________

DRAFT, NOT SENT. **Supplier C.** PO number: to be assigned. Order date: Monday 9 November 2026, if approved today. Requested delivery: Monday 16 November 2026 (7-day lead time).

- FIL-02 Steel tea infuser: 84 (7 packs of 12) at $4.10 = $344.40.
- Total: $344.40. Prices: last cost in the stock export as of Sunday 8 November 2026; supplier to confirm. Minimum order $400.00: below minimum by $55.60, see question 5.
- Approved to send: ______________ Date: ________

**Questions for the owner**

1. TEA-01 runs out by Wednesday 18 November; an order placed today from Supplier A arrives Monday 23 November, 5 days later. Is there an earlier delivery you want to ask Supplier A for?
2. GEAR-01 runs out by Monday 23 November; an order placed today from Supplier B arrives Monday 30 November, 7 days later. Is there an earlier delivery you want to ask Supplier B for?
3. FIL-02 runs out by Saturday 14 November; an order placed today from Supplier C arrives Monday 16 November, 2 days later. Is there an earlier delivery you want to ask Supplier C for?
4. GEAR-01 sold 18 in the last 7 days, 2.57 a day, against 1.57 a day over four weeks. The runs-out date uses 2.57; the order is sized on 1.57. Is last week a new trend or a one-off?
5. Supplier C's order is $344.40 against a $400.00 minimum, $55.60 short. Smallest additions that reach it: FIL-02, 2 more packs of 12: 24 units, $98.40, new total $442.80, 12 more days of cover at 1.95 a day. FIL-01 (no order needed yet), 1 pack of 24: 24 units, $57.60, new total $402.00, 5 more days of cover at 4.50 a day. Which, if either, do you want, or do you want to ask Supplier C to accept the smaller order?
6. TEA-09 sold 5 in the week ending 25 October and has no row in the stock export. Which product is it, and should it be in the stock export?
7. GEAR-02 has no sales in four weeks and 85 on hand, $255.00. What do you want done with it?
8. GEAR-03 holds 11 units above the 180-day limit, $418.00, and $1,140.00 in all. What do you want done with the extra stock?
9. GEAR-04 has been on sale 13 days: 6 sold in its first week, 9 in its second, 25 on hand, with a 21-day lead time from Supplier B. It can be rated from Monday 23 November. Is there anything you want to tell us about its expected sales?

Draft for the owner's decision. Nothing has been ordered, sent or changed in any system. Each purchase order goes to its supplier only after a person approves it.

## What was observed

**Every required part was produced.** Header, column check, settings, summary, data checks, all six groups, three draft purchase orders, questions, and the closing line. The assistant stopped for nothing: all headers matched, the newest sales week ends on the count date, the count is one day old, and there are no duplicate codes. The reviewer checklist passed on a recheck, with the points below.

**How the arithmetic was done.** The assistant worked the figures out and then checked them with a short throwaway Python script used as a calculator; the template does not require this. Every rate, point, target, pack count, cost and date matched.

**Difference from the published example, one figure.** The example gives 10 units above the limit for GEAR-03 ($380.00, summary and question 6). Following the instruction as written (position less rate x limit, rounded up: 30 - 19.80 = 10.20, so 11) gives 11 units and $418.00. The example rounds the 19.80 up to 20 first. The template's own acceptance test 7 expects 10, so the template's rule and its test disagree, and the example follows the test. This is a defect in the template (or its example), not a judgement call.

**Other differences from the example, all small.**
- The example lists three SHORT items in one question; this run wrote one question each, so the later questions are numbered differently. The template does not say which.
- The example's Settings line names no defaults; this run named the count age limit and the one-and-a-half-times threshold as defaults used, because the template says any default used is named in the header.
- The example's question about the new item asks for "an expected weekly figure so it can be planned sooner"; this run asked more openly. The template's wording for that question is not specified.
- The example says "about 12 more days" of cover; this run says 12, as the rule is rounded down.
- The example's questions 5 and 6 add "Is it on sale and is its stock tracked?"; this run did not.

**Ambiguities where the assistant had to choose.**
1. The rounding in "units above the limit" (above).
2. The reviewer checklist says each stock item appears in exactly one group or under Data checks. GEAR-02 and GEAR-03 appear in both (a group and a data check), as the procedure and the example require. The checklist line contradicts that.
3. "Can be rated from [date]" for a new item. The 28th day on sale is Monday 23 November, but the next weekly count is Sunday 29 November. The template does not say which to give; this run gave 23 November, as the example does.
4. Whether a minimum-order question lists the smallest packs of each item alone (done here) or the smallest combination. The wording "for each item" supports the first.
5. The two defaults in the header (count age limit, jump threshold) have no named place in the Settings line.
6. Step 12 does not say whether a question covers one item or a group. The SHORT items could be one question or three.
7. Step 6 says to recompute the runs-out date after counting stock on order; it does not say whether the SHORT test then uses the recomputed date. This run used it (TEA-03 is not short either way).
8. The "Left out by the data checks" count in the summary includes TEA-09, which is not an item in the stock export.

**Facts not in the inputs.** None found in this run's output. In the example's output, every fact traces to the inputs; the one inference is the question about GEAR-04's lead time, which is in the supplier terms.

**One limit on how independent this trial is.** The template's acceptance tests, which this run read before running, share some figures with the example (the $344.40 order against a $400 minimum, 272 days of cover). They did not change any figure produced, but they were visible.

The template says nothing was yet tried on its example in a named AI product; this record is that one run. It does not test the template in a client environment or as a packaged version.

## Edited after this run

Made on 10 November 2026 after an independent review. None of these edits has been run.

- **Units above the overstock limit (the defect above).** Step 5 and item 5 of the instruction block now say: units within the limit are the four-week rate times the limit, rounded up to whole units, and units above the limit are the stock position less the units within it. The template was changed, not the example: for GEAR-03 this gives 20 within the limit and 10 above it, $380.00, as the published example and acceptance test 7 already gave. This run, following the earlier wording, gave 11 and $418.00; under the new wording it would have given 10. The Overstocked line of the output format now spells out that working, and test 7 now names the 20 units within the limit.
- **Settings line (ambiguity 5 and the second small difference).** The count age limit and the recent-rate jump threshold are now named settings with defaults (7 days; one and a half times the four-week rate), and the Settings line gives all six numbers followed by "Defaults used". The published example's Settings line now names those two as defaults used, as this run did.
- **SHORT items and how questions are grouped (ambiguity 6 and the first small difference).** All SHORT items now share one question, as in the published example; this run's three separate questions would now be one. Every other question covers one item, or one supplier for a minimum, and an item with both a data-check question and a Not moving or Overstocked question gets one question, in the later place. The example's question about GEAR-02 already asked both.
- **"Can be rated from" (ambiguity 3).** Now defined as a new item's 28th day on sale, first on sale plus 27 days: Monday 23 November for GEAR-04, as both this run and the example gave. An item short of days in stock is said to be ratable once it has been in stock 14 of the last 28 days.
- **"Left out by the data checks" (ambiguity 8).** Now defined as every item code the data checks leave out, including codes found only in the sales export, so TEA-09 counts, as both this run and the example counted it.
- **Reviewer checklist item 2 (ambiguity 2).** Now reads that every stock item appears in exactly one group, or is left out under Data checks.
- **The example's question 3.** "About 12" and "about 5" more days of cover are now "12" and "5", as the rule rounds down and as this run wrote them.
- **Wording only.** The Purpose sentence on showing the arithmetic was reworded, the acceptance tests now say which of them share cases with this example, and the version notes now record this run.

Ambiguities 4 and 7 were left as they were: the wording "for each item" already supports this run's reading of the minimum-order question, and step 6 defines the runs-out date after stock on order is counted.

### Second set, after the second review

Made on 10 November 2026 after a second independent review. None of these edits has been run either. None changes a figure, a group or a purchase order in the example; the only change to the published example's output is one clause in its question 5.

- **SHORT outside Order now.** Step 6, step 8 and items 6 and 8 of the instruction block now say that an item can be SHORT in Order at the next review or No order needed, when stock on order arrives after the stock on hand runs out; it keeps SHORT on its line and in the summary, and its days with no stock end at the earlier of the arrival date for an order placed today and the day the uncounted stock on order arrives. The output format has a SHORT slot on those two lines, an optional SHORT count beside them in the summary, and an optional "until the stock on order arrives" on the Order now line. No item in the example is in this position.
- **A missing sales week.** The Inputs section now says a missing week is listed under Data checks, as step 2 and the example already do, rather than "on the item's line".
- **What three questions ask (the third and fifth small differences above).** Step 12 and item 12 now say what a Not moving, an Overstocked and a Too little history question give and ask. A Not moving item with no sales rows is asked whether it is on sale; a Too little history item is asked for an expected weekly figure so it can be planned sooner, as the example asked. The example's question 5 no longer asks whether GEAR-02's stock is tracked: it now asks "Is it on sale? If so, what do you want done with it?" This run asked only the second part.
- **A blank unit cost or pack size.** The item is now listed under Data checks; its Order line gives the units needed with "cost not stated" or "pack size not stated"; the purchase order names it as left off, and its total and minimum check count only the lines on it; it is never offered as an addition toward a minimum. No item in the example has a blank cost or pack size.
- **Filing and credits.** The primary function is now Supply chain and inventory, and the credit for the upstream package's main file now names a summary that leads with the total to order and the count of items about to run out.
