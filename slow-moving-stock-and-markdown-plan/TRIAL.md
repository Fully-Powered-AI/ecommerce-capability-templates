# Slow-moving stock and markdown plan: tried on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Sonnet 5.5 (model ID claude-sonnet-5-5)
- **Date:** 2026-11-10

The inputs were the invented example in `public/example.md`: its settings, stock export, sales export and notes. No client data was used. The model that ran the template did not write it, and read only the example's inputs before producing the plan below. The example's own output was read afterwards, for comparison.

Arithmetic that is easy to get wrong (dates, rounding, floor prices) was checked with a short script; the plan itself was written by following the template's instruction block and output format.

## What came out

**SLOW-MOVING STOCK AND MARKDOWN PLAN: the Store, stock counted Sunday 3 January 2027**

- **For:** the owner. Prepared Monday 4 January 2027 from: sales export (Monday 5 October 2026 to Sunday 3 January 2027, 8 rows), stock export (8 items), settings, notes.
- **Column check:** all headers matched.
- **Dates:** reset Monday 1 March 2027, 8.1 weeks after the count. First markdown Monday 11 January 2027, 7.0 weeks before the reset, so steps are 2 weeks apart. Stop date Monday 15 February 2027.
- **Settings:** new-item window 30 days; markdown steps 20%, 35%, 50% off the full price; deeper start below 40% projected sell-through; margin floor 10%; stop 14 days before the reset; cover limit for kept lines 26 weeks. Defaults used: first markdown date, deeper-start line, stop gap.
- **Summary:** cash tied up at cost: dead stock $875.00 (2 items), slow stock $2,568.00 (2 items), kept lines $360.00 above the cover limit (1 item). Markdown plans: 3 items, 311 units, $3,243.00 at cost. On track: 1. Too new to judge: 1. Left out by the data checks: 1. No stock, not listed: 1.

**Data checks**

- SOCK-09 is in the sales export and not in the stock export. Left out of the plan; question 1.
- TEA-08 has no row in the sales export. Read as no sales; question 2.
- ORN-07 has none on hand. Not listed; counted in the summary.

**Dead stock**

- **CND-04** Pine candle (clear). First received Monday 19 October 2026 (10 weeks). Sold in the period 45; none in the last 4 weeks. On hand 75. Sell-through 37.5%. Cash at cost: 75 × $9.00 = $675.00. Markdown plan below.
- **TEA-08** Winter spice tea tin (keep). First received Monday 1 June 2026 (30 weeks). Sold in the period 0; none in the last 4 weeks; no row in the sales export. On hand 40. Sell-through 0.0%. Cash at cost: 40 × $5.00 = $200.00. Kept after the reset: no markdown planned (question 2).

**Slow stock**

- **SCF-02** Cashmere-blend scarf (clear). First received Monday 5 October 2026 (12 weeks). Sold in the period 34; last 4 weeks 6 = 1.50/week. On hand 96. Sell-through 26.2%. Weeks of cover 64.0, against 8.1 weeks to the reset. By the reset at this pace: 12 sold, 84 left, sell-through 35.4%. Cash at cost: 96 × $18.00 = $1,728.00. Markdown plan below.
- **HAT-01** Wool beanie (clear). First received Monday 5 October 2026 (12 weeks). Sold in the period 210; last 4 weeks 48 = 12.00/week. On hand 140. Sell-through 60.0%. Weeks of cover 11.7, against 8.1 weeks to the reset. By the reset at this pace: 97 sold, 43 left, sell-through 87.7%. Cash at cost: 140 × $6.00 = $840.00. Markdown plan below.

**Kept lines above the cover limit**

- **MUG-05** Stoneware mug (keep). Sold in the period 120; last 4 weeks 20 = 5.00/week. On hand 220. Sell-through 35.3%. Weeks of cover 44.0, above 26. Units within the limit: 130 (5.00 × 26 = 130.00, rounded up); above it: 90 × $4.00 = $360.00. Cash at cost in the item: $880.00. No markdown planned (question 3).

**On track**

- **GLV-03** Touchscreen gloves (clear). Last 4 weeks 40 = 10.00/week. On hand 60. Sell-through 71.4%. Weeks of cover 6.0, against 8.1 weeks to the reset; by the reset at this pace: 60 sold, 0 left.

**Too new to judge**

- **THR-06** Knitted throw (clear). First received Monday 14 December 2026 (20 days before the count). Sold so far 6; on hand 30. Not judged. Can be judged from Wednesday 13 January 2027.

**Markdown plans**

Largest cash at cost first. Prices are the full price less the step's percentage, to the cent. A step after the first is taken only if fewer units than its check figure have sold since the first markdown; otherwise the current price holds, the step and those after it move to the next check, 2 weeks later, and none is taken after the stop date. No forecast of extra sales is made.

**SCF-02** Cashmere-blend scarf. Full price $59.00, unit cost $18.00: margin $41.00 a unit (69.5%). Floor price $20.00 (10% margin). Starts at the second step: projected sell-through 35.4% is below 40%. Pace to clear by the reset: 96 ÷ 7.0 weeks = 13.71 a week.

- Step 1, Monday 11 January 2027: 35% off, $38.35. Margin $20.35 a unit (53.1%); if all 96 sold at this price, $1,953.60.
- Step 2, Monday 25 January 2027: 50% off, $29.50. Take it if fewer than 28 have sold since Monday 11 January 2027. Margin $11.50 a unit (39.0%); if all 96 sold at this price, $1,104.00.
- No further step: the markdown steps are used up.
- Stop date Monday 15 February 2027: no markdown after it. Prices hold until the reset on Monday 1 March 2027; what is left then is your choice (question 5).
- Owner's decision (approve / change / hold): ______________ Date: ________

**HAT-01** Wool beanie. Full price $24.00, unit cost $6.00: margin $18.00 a unit (75.0%). Floor price $6.67 (10% margin). Pace to clear by the reset: 140 ÷ 7.0 weeks = 20.00 a week.

- Step 1, Monday 11 January 2027: 20% off, $19.20. Margin $13.20 a unit (68.8%); if all 140 sold at this price, $1,848.00.
- Step 2, Monday 25 January 2027: 35% off, $15.60. Take it if fewer than 40 have sold since Monday 11 January 2027. Margin $9.60 a unit (61.5%); if all 140 sold at this price, $1,344.00.
- Step 3, Monday 8 February 2027: 50% off, $12.00. Take it if fewer than 80 have sold since Monday 11 January 2027. Margin $6.00 a unit (50.0%); if all 140 sold at this price, $840.00.
- No further step: the markdown steps are used up.
- Stop date Monday 15 February 2027: no markdown after it. Prices hold until the reset on Monday 1 March 2027; what is left then is your choice (question 5).
- Owner's decision (approve / change / hold): ______________ Date: ________

**CND-04** Pine candle. Full price $16.00, unit cost $9.00: margin $7.00 a unit (43.8%). Floor price $10.00 (10% margin). Starts at the second step: dead stock. Pace to clear by the reset: 75 ÷ 7.0 weeks = 10.71 a week.

- Step 1, Monday 11 January 2027: 35% off, $10.40. Margin $1.40 a unit (13.5%); if all 75 sold at this price, $105.00.
- Step 2, Monday 25 January 2027: 37.5% off, $10.00, at the floor. Take it if fewer than 22 have sold since Monday 11 January 2027. Margin $1.00 a unit (10.0%); if all 75 sold at this price, $75.00.
- No step after the floor.
- Stop date Monday 15 February 2027: no markdown after it. Prices hold until the reset on Monday 1 March 2027; what is left then is your choice (question 5).
- Owner's decision (approve / change / hold): ______________ Date: ________

**Questions for the owner**

1. SOCK-09 sold 18 in the period and 4 in the last 4 weeks, but has no row in the stock export. Which product is it, how many are on hand, and should it be in the stock export?
2. TEA-08, Winter spice tea tin, stays in the range after the reset. It has no sales in the period and no row in the sales export, with 40 on hand, $200.00 at cost. Is it on sale? What do you want done with it?
3. MUG-05, Stoneware mug, stays in the range after the reset. It holds 44.0 weeks of cover against a 26-week limit: 90 units, $360.00 at cost, above the limit, and $880.00 in the whole item. What do you want done with the extra stock?
4. THR-06, Knitted throw, is to clear by the reset but arrived 20 days before the count: 6 sold so far, 30 on hand. It can be judged from Wednesday 13 January 2027. Do you want it judged then?
5. At the current pace, SCF-02 would have 84 units left at the reset, HAT-01 43 and CND-04 75. After the stop date, Monday 15 February 2027, prices hold until the reset on Monday 1 March 2027. For any units still left then, the usual choices are: hold for next season, return to the supplier where the terms allow it, bundle with a line that sells, sell to a clearance buyer, or donate. What do you want for each item?

Draft for the owner's decision. No price has been changed and nothing has been published or sent. Each price change is made by a person, on its date, after the owner approves it.

## What was observed

- **Every required part was produced.** Header, column check, dates, settings, summary, data checks, five groups, three markdown plans, five questions and the closing line. No stop condition applied: all headers matched, the reset date was given, and no item code was repeated.
- **Nothing came out that the template told the assistant to stop for.** The only things set aside were the left-out item (SOCK-09), the zero-stock item (ORN-07) and the too-new item (THR-06), all as the template directs.
- **Every figure traced to the inputs.** No fact appears in the output that is not in the inputs, apart from the dates and weekday names the template has the assistant work out, and the invented product names as given.
- **Differences from the published example's output.** Only two, and neither changes a figure, a date or a price. First, question 5: the example does not give the units each planned item would have left at the reset at the current pace; this run did (84, 43, 75), because the template asks for facts and a question; the example's question asks "Which do you want for each?", this run "What do you want for each item?". Second, ordinary wording in the data checks: this run's SOCK-09 line leaves out its sales figures (18 in the period, 4 in the last 4 weeks), which the example gives; its SOCK-09 and TEA-08 lines say "question 1" and "question 2" where the example says "see question 1" and "see question 2"; and it added "counted in the summary" to the ORN-07 line. Every other line, number and date is the same as the example's output, including the order of groups and plans.
- **Reviewer checklist.** Items 1 to 8 hold on a read of this output. Item 9 (owner approval before any price changes) cannot be shown by a single run; the output leaves a blank decision line on each plan and says nothing has been changed.

### Where the instructions were ambiguous, or the template fell short

1. **"The first Monday after today" when today is a Monday.** Today was Monday 4 January 2027; this run took Monday 11 January, reading "after" as strictly after. The template does not say. The example agrees, but a reader could take today.
2. **Step numbering when a plan starts at the second step.** The template numbers steps from "Step 1 is on the first markdown date" but also speaks of starting "at the second step". In this run, SCF-02 and CND-04 start at the 35% step and that step is labelled "Step 1", which is what the example does. The words "second step" then mean two different things (the second of the settings' steps, and the second dated step). A reader can get this wrong.
3. **Weeks to the reset: rounded or exact.** The template says one decimal place, so 8.1 was used in the projection. Using 57 ÷ 7 unrounded can change the units sold by the reset when the rate is high. It made no difference on this data.
4. **Kept lines in the summary.** "Kept lines [amount] above the cover limit" could mean the cash above the limit ($360.00) or the cash in the whole kept line ($880.00). This run used the first, matching the example. The template does not say.
5. **A step at the floor that is barely below the step before it.** CND-04's second step is $10.00, at the floor, against $10.40 for the first: a 40 cent drop. The template's rules produce this correctly, but it gives the owner a step of little use, and the template says nothing about merging or dropping such a step. It does show the margin and the check figure, so the owner can see it.
6. **Check figure for a step that moves.** The rule says a held step and those after it move to the next check, and none is taken after the stop date, but the check figure for a moved step is not restated. It is not stated whether the figure rises with the later date (it should, since it is pace times weeks since the first markdown) or stays. This run did not need it.
7. **Items with no sales row.** An item missing from the sales export but marked `keep` (TEA-08) is read as no sales and so lands in Dead stock with a sell-through of 0.0%. That follows the template, but it presents an item that may simply be missing from the export as dead. The question asks, which is the safeguard.
8. **"Defaults used" and the first markdown date.** The Settings line has six numbers, and "Defaults used" is meant to list values that came from a default. The first markdown date is shown on the Dates line, not on the Settings line, but it also counts in "Defaults used". Slightly confusing, though the example does the same.
9. **Pace compared with current sales rate.** The check figure is the pace needed to clear on hand by the reset (HAT-01: 20 a week), while the item is selling 12 a week. That is intended, but the output never shows both side by side, so an owner might not see that a held step could be the usual case at the current rate. The template does not ask for it.

None of these stopped the run. Items 1, 2 and 4 are the ones most worth fixing in the template, by saying in a sentence what is meant.

## Edited after this run

Made on 10 November 2026 after an independent review. None of these edits has been run. The output and the observations above are left as the run produced them, with one correction: the comparison with the published example under "What was observed" first named only the ORN-07 wording among the data-check differences, and was corrected on review to name the SOCK-09 and TEA-08 wording as well. Where the observations compare this run with the example, they describe the example as it stood at the time of the run.

Each edit in the first list below settles a point the run found open, in the way the run and the example had already handled it. None changes a date, a figure, a group, a price, a check figure or a question on the example. Two change the wording a run prints, as noted.

- **The first markdown date (ambiguity 1).** The default is now "the first Monday strictly after today, even when today is a Monday", in the inputs and in the instruction block. Monday 11 January 2027, as this run and the example took.
- **Step numbering (ambiguity 2).** Step 8 and item 8 of the instruction block now speak of the first and second markdown percentage, not the first and second step, and say that steps are numbered by date, so the first dated step is Step 1 whichever percentage it uses, as this run and the example numbered them. The plan line in the output format now reads "Starts at the second markdown percentage, [n]%: ...". This changes what a run prints: the example's SCF-02 and CND-04 lines now read "Starts at the second markdown percentage, 35%: ..."; this run printed "Starts at the second step: ...". The acceptance tests use the same words.
- **Rounded weeks (ambiguity 3).** Step 3 and item 3 now say every later sum uses the two week figures as rounded to one decimal place; step 5 says the projection uses that figure (8.1 here), as this run did.
- **Kept lines in the summary (ambiguity 4).** Step 6, item 6 and the Summary line of the output format now say the kept-lines amount is the cash at cost in the units above the limit only, not the whole item: $360.00 here, as this run and the example gave. The printed line is unchanged.
- **A moved step's check figure (ambiguity 6).** Step 11, item 11 and the head of the markdown plans in the output format now say a held step's check figure is worked out again for its new date: pace times weeks from the first markdown to the new date, rounded up. This run did not need it. This changes what a run prints: the example's sentence at the head of the plans now adds "with the check figure worked out again for the new date", which this run's did not have.
- **What three questions give (no ambiguity was listed).** Item 13 of the instruction block now says, as the procedure already did, what a Dead keep, a Kept lines and a Too new question give and ask, including whether an item with no sales row is on sale. The example's questions 2 to 4 and this run's already did so.
- **Instruction block wording.** The closing paragraph now names login codes beside bank details, card numbers and passwords, as the Exceptions section did. Item 14 now spells out the closing draft line as the output format gives it, and item 15 now adds, as the procedure did, that a check-date report gives only the figures supplied and changes no plan without the owner. This run's closing line already matched the output format.
- **A floor step barely below the step before (ambiguity 5).** Left as the run produced it: the step is kept and shown with its margin and check figure. "What to customize" now offers a smallest worthwhile step for stores that would rather drop such a step and say so on the line.
- **Related pieces of work and labels.** The profile and the template now name the price change review for raising list prices. The profile's "What has been checked", the version notes and the acceptance tests now say the template was tried once on this example and that these edits have not been run again.

Ambiguities 7, 8 and 9 were left as they were: the question on an item with no sales row is the safeguard for 7, the Dates and Settings lines already say where each value sits for 8, and for 9 an item's weekly rate and its pace to clear were both printed, on its group line and on its plan line. Ambiguity 9 was taken up in the second list below.

A second independent review on 10 November 2026 led to the edits in this second list. None of them has been run either. Two change what a run prints on the example, as noted; neither changes a date, a figure, a group, a price or a check figure.

- **Units left at the reset in question 5.** Step 13 and item 13 of the instruction block now say the left-at-the-reset question gives each planned item's units left at the reset at the current pace (all its units on hand for a dead item). This run already gave them, unasked. This changes what a run prints: the example's question 5 now opens "At the current pace, SCF-02 would have 84 units left at the reset, HAT-01 43 and CND-04 75.", as this run's did.
- **Pace beside the current rate (ambiguity 9).** Step 11, item 11 and the plan line of the output format now print the pace to clear beside the item's weekly rate now (0.00 for dead stock), so the owner can see that a taken step is the likely case at the current rate. This changes what a run prints: the example's plan lines now end "against 1.50 a week now" (SCF-02), "against 12.00 a week now" (HAT-01) and "against 0.00 a week now" (CND-04); this run's did not.
- **Item 2 of the instruction block** now says, as procedure step 2 did, that an item with a blank cost or price is still worked out where possible, and that the summary's "Left out by the data checks" counts every item code the checks leave out, including codes found only in the sales export. This run already did both.
- **Acceptance test 2** now states the 8.1 weeks to the reset its expected 35.4% depends on.
- **Credits.** The credit to the product analytics method now reads "deeper cuts for stock that is selling less", without "older": the template deepens the opening step for dead stock or a low projected sell-through, never for age.
- **Price endings.** "What to customize" now says the rounding rule has to be added to step 9 and to item 9 of the instruction block, since the procedure has no setting for it.
