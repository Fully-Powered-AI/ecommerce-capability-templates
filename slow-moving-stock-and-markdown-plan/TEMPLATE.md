# Slow-moving stock and markdown plan

Workflow template, version 0.1.0.

## Purpose

Prepare one plan for a store before a seasonal reset from its sales export, its stock export and its settings: each item's sell-through, weekly sales rate and weeks of cover, which items are dead, slow, on track, too new to judge or kept after the reset with too much stock, the cash at cost tied up in each, and, for every dead or slow item that has to be cleared, a markdown plan in dated steps with the price, the margin each step leaves, the sales figure that decides whether the next step is taken, and the date after which no further markdown is made. Every figure traces to an input, and the arithmetic is written out beside each item. The assistant prepares; the owner decides every price change. It never changes a price, publishes a sale, emails customers or changes a stock record.

## When to use it and when not to

Use it four to ten weeks before a seasonal reset, when the store has to make room for a new range and wants the old one sold while it still earns something. Run it again at each check date in the plan, with the units sold since the first markdown, to see whether the next step should be taken.

Do not use it:

- to decide what to reorder or how much. That is the inventory reorder plan, a separate piece of work;
- to raise list prices or review the full-price range. That is the price change review, a separate piece of work;
- to plan a promotion on lines that are selling well at full price;
- to match a competitor's prices or set prices by channel or by store location;
- to forecast how many more units a lower price will sell. The plan makes no such estimate; its check figures tell the owner, step by step, whether the stock is moving fast enough.

## Roles

- **Runs it:** the merchandiser, the buyer or the store owner.
- **Answers the questions and approves, changes or holds each item's plan:** [your owner], usually the store owner. Each item's plan is decided on its own.
- **Changes a price in the store system on an approved step date:** the person the store names. Always a person.
- **Counts the units sold at each check date:** the person who runs it, from the store's sales report.

## Inputs

The assistant works only from the exports and notes the person supplies. It needs no connection to the store system, the accounts or any sales channel, and never asks for a password or a login code.

1. **The sales export.** One row per item for the sales period, which runs from [your period start], usually the start of the season, to the day of the stock count. Default column headers: `sku`, `sold_in_period`, `sold_last_4_weeks`. `sold_last_4_weeks` covers the 28 days ending on the count date. An item with no row is read as no sales and listed under Data checks.
2. **The stock export,** as of the end of the count date. One row per item. Default column headers: `sku`, `product`, `on_hand`, `unit_cost`, `price`, `first_received`, `after_reset`. `unit_cost` is the last price paid, before tax and delivery. `price` is the full selling price before any markdown. `first_received` is the date the item first arrived. `after_reset` is `clear` for an item that must be gone by the reset and `keep` for an item that stays in the range.
3. **The settings,** typed: the store, the stock count date, today's date, the start of the sales period, the reset date, the first markdown date, who decides, the currency, and the store's numbers. Defaults when a value is not given: first markdown date, the first Monday strictly after today, even when today is a Monday; [your new-item window], default 30 days; [your markdown steps], default 20%, 35% and 50% off the full price; [your deeper-start line], default a projected sell-through below 40%; [your margin floor], default 10% margin on the reduced price; [your stop gap], default 14 days before the reset; [your cover limit for kept lines], default 26 weeks. The Settings line of the plan gives all six numbers, and the Dates line gives the first markdown date. "Defaults used" names each value that came from a default rather than from the settings typed.
4. **Notes** (optional): items already on markdown, with their full and current price; items the owner does not want marked down, with the reason; anything else the merchandiser knows, such as a promotion already booked. If none are supplied, write "no notes supplied" in the header.

**Column check.** Before any arithmetic, compare each export's headers with the defaults, or with the store's own headers if [your column headers] are set. If a header is missing or named differently, stop. List the headers expected and the headers found, ask which column is which, and draft nothing else. Never guess a column.

## The procedure

1. **Check the inputs.** Run the column check. Confirm the count date, today's date, the reset date and the first markdown date. If the reset date is missing, stop and ask. If the first markdown date is on or after the stop date, stop and say there is no time for a markdown plan.
2. **Check the data.** List, under Data checks: an item in the sales export that is not in the stock export (left out of the plan); an item in the stock export with no sales row (read as no sales); an item with zero on hand (not listed; counted in the summary); negative stock on hand (left out until recounted); `sold_last_4_weeks` greater than `sold_in_period` (left out; ask); an `after_reset` value other than `clear` or `keep` (left out; ask); a blank unit cost or price (worked out where possible, but given no markdown plan; ask); a price at or below the unit cost (given no markdown plan; ask); an item the notes say is already on markdown (left out; ask for the full and current price); an item the notes say is not to be marked down (worked out and grouped, given no markdown plan, with the reason on its line). Two rows with the same item code: stop and ask. The summary's "Left out by the data checks" counts every item code these checks leave out of the plan, including codes found only in the sales export.
3. **Work out the dates.** Weeks to the reset = days from the count date to the reset date ÷ 7, to one decimal place. Weeks from the first markdown to the reset = days between them ÷ 7, to one decimal place. Step spacing: 3 weeks if the second figure is 8 or more, 2 weeks if it is at least 4 and under 8, 1 week if it is under 4. Stop date = reset date less [your stop gap]. No step is ever dated after the stop date. Every later sum uses these two figures as rounded to one decimal place, never the exact quotient.
4. **Set aside items too new to judge.** An item first received fewer than [your new-item window] days before the count date goes to Too new to judge: its sales so far and on hand, the date it can be judged from (first received + the window), no rate and no plan.
5. **Work out each item's figures.** Sell-through = sold in the period ÷ (sold in the period + on hand) × 100, to one decimal place. Weekly rate = sold in the last 4 weeks ÷ 4, to two decimal places. Weeks of cover = on hand ÷ weekly rate, to one decimal place; with no sales in the last 4 weeks, write "no sales in 4 weeks" and never divide by zero. Weeks since first received = days ÷ 7, rounded down. Cash at cost = on hand × unit cost. For an item to clear, also project to the reset at the current pace: units sold by the reset = weekly rate × weeks to the reset (the one-decimal figure from step 3), rounded down and no more than on hand; units left = on hand less that; projected sell-through = (sold in the period + units sold by the reset) ÷ (sold in the period + on hand) × 100, to one decimal place.
6. **Group each item.** No sales in the last 4 weeks: Dead stock, whether it is to clear or keep. An item to clear with units left at the reset: Slow stock. An item to keep whose weeks of cover are above [your cover limit for kept lines]: Kept lines above the cover limit, with the units within the limit (weekly rate × the limit, rounded up), the units above it and their cost. The summary's kept-lines amount is the cash at cost in the units above the limit only, never the cash in the whole item. Everything else: On track. Every item in the stock export lands in exactly one group, in Too new to judge, or under Data checks. Within each group, list items largest cash at cost first.
7. **Choose which items get a markdown plan.** Every Dead or Slow item marked `clear` gets one, unless the data checks or the notes hold it back. Dead items marked `keep` and Kept lines above the cover limit get no plan; each goes to the questions. List the plans largest cash at cost first.
8. **Set the starting step.** Start at the first markdown percentage in [your markdown steps], unless the item is Dead stock or its projected sell-through is below [your deeper-start line]; then start at the second markdown percentage (35% by default), and say which reason applies and which percentage. Use the remaining percentages in order, one per step date. Steps are numbered by date, so the first dated step is Step 1 whichever percentage it uses.
9. **Date and price the steps.** Step 1, the first dated step, is on the first markdown date; each later step is the step spacing after the one before. Drop any step dated after the stop date and say so. Price at each step = full price × (1 − the step's percentage), to the cent. Floor price = unit cost ÷ (1 − [your margin floor]), rounded up to the cent. If a step's price is below the floor price, that step is priced at the floor price, marked "at the floor" with its percentage off the full price to one decimal place, and no step follows it. If even the full price is below the floor price, give the item no plan and ask. Each plan says why it has no further step: the next date is after the stop date, the floor was reached, or the markdown steps are used up.
10. **Show the margin each step leaves.** For the full price and for each step: margin a unit = price − unit cost; margin per cent = margin a unit ÷ price × 100, to one decimal place; and, for each step, the margin if every unit on hand sold at that price. These are what the price leaves, not a forecast of what will sell.
11. **Set the check figure for each step after the first.** Pace to clear by the reset = on hand ÷ weeks from the first markdown to the reset, to two decimal places. The plan line gives this pace beside the item's weekly rate now (0.00 for dead stock), so the owner can see how far the current rate falls short of it. Check figure for a step = pace × weeks from the first markdown to that step, rounded up. The step is taken only if fewer units than the check figure have sold since the first markdown. If the check figure or more have sold, the current price holds; the step moves to the next spacing date and the steps after it move with it, and none is taken after the stop date. A moved step's check figure is worked out again for its new date: pace × weeks from the first markdown to the new date, rounded up. State this rule once at the head of the plans.
12. **Close each plan** with the stop date, the note that prices hold from the stop date until the reset, and a blank line for the owner's decision: approve, change or hold.
13. **Write the questions,** numbered, in this order: data checks needing an answer; Dead items marked `keep`; Kept lines above the cover limit; Too new items marked `clear`; what happens to the units still left at the reset from the planned items (one question for all of them); anything in the notes the owner must settle. Each question gives the facts and asks; none recommends. A Dead `keep` question gives the units on hand and the cash in them, asks whether the item is on sale if it has no sales row, and asks what the owner wants done with it. A Kept lines question gives the units and cash above the limit and the cash in the whole item, and asks what the owner wants done with the extra stock. A Too new question gives the sales so far, the units on hand and the date it can be judged from, and asks whether the owner wants it judged then. The left-at-the-reset question lists the planned items, each with the units it would have left at the reset at the current pace (all its units on hand for a dead item), and offers the usual choices (hold for next season, return to the supplier where the terms allow it, bundle with a line that sells, sell to a clearance buyer, donate) without choosing among them.
14. **Return the plan** to the person who ran it, for [your owner]. The owner answers the questions and approves, changes or holds each item's plan. A person makes each approved price change on its date.
15. **At a check date,** when the person supplies units sold since the first markdown for each planned item, report for each: the check figure, the units sold, and whether the plan says take the step or hold. Report only the figures supplied; change no plan without the owner.

## Exceptions and stop conditions

- **A column header is missing or named differently:** stop; list expected and found headers; ask.
- **The reset date is missing, or the first markdown date is on or after the stop date:** stop and ask.
- **Two rows with the same item code:** stop and ask which is which.
- **Negative stock on hand, last-4-weeks sales above the period's, or an unknown `after_reset` value:** leave the item out, list it under Data checks, and ask.
- **A unit cost or price is blank, or the price is at or below the unit cost:** list it under Data checks and give it no plan. Ask for the figure. Never guess either.
- **An item is already on markdown:** leave it out and ask for its full and current price. Never stack a new step on an unknown price.
- **Asked to change a price, publish a sale, email customers, or change stock or cost records in any system:** decline; name the role that does it.
- **Asked to forecast the extra sales a markdown will bring, or to pick the deepest price that still clears the stock:** decline; the plan gives the check figures and the margins, and the owner decides.
- **Asked to go below the margin floor or past the deepest step:** show the figures under Questions and leave the choice to the owner; the plan itself stays within the settings.
- **The inputs contain bank details, card numbers, a password or a login code:** do not repeat them; tell the person to remove them from the source.

## Output format

```
SLOW-MOVING STOCK AND MARKDOWN PLAN: [store], stock counted [weekday date]

For: [owner]. Prepared [weekday date] from: sales export ([period start] to [count date], [n] rows), stock export ([n] items), settings, [notes / no notes supplied].
Column check: all headers matched. / Stopped: expected [headers]; found [headers].
Dates: reset [weekday date], [n] weeks after the count. First markdown [weekday date], [n] weeks before the reset, so steps are [n] weeks apart. Stop date [weekday date].
Settings: new-item window [n] days; markdown steps [n]%, [n]%, [n]% off the full price; deeper start below [n]% projected sell-through; margin floor [n]%; stop [n] days before the reset; cover limit for kept lines [n] weeks. Defaults used: [the values that came from a default / none].
Summary: cash tied up at cost: dead stock [amount] ([n] items), slow stock [amount] ([n] items), kept lines [cash at cost in the units above the limit only, not the whole item] above the cover limit ([n] items). Markdown plans: [n] items, [n] units, [amount] at cost. On track: [n]. Too new to judge: [n]. Left out by the data checks: [n]. No stock, not listed: [n].

Data checks
[Finding; what was done.] / No problems found.

Dead stock
[Code] [product] ([clear / keep]). First received [weekday date] ([n] weeks). Sold in the period [n]; none in the last 4 weeks[; no row in the sales export]. On hand [n]. Sell-through [n]%. Cash at cost: [n] × [cost] = [amount]. [Markdown plan below. / Kept after the reset: no markdown planned (question [n]).]
/ None.

Slow stock
[Code] [product] (clear). First received [weekday date] ([n] weeks). Sold in the period [n]; last 4 weeks [n] = [rate]/week. On hand [n]. Sell-through [n]%. Weeks of cover [n], against [n] weeks to the reset. By the reset at this pace: [n] sold, [n] left, sell-through [n]%. Cash at cost: [n] × [cost] = [amount]. Markdown plan below.
/ None.

Kept lines above the cover limit
[Code] [product] (keep). Sold in the period [n]; last 4 weeks [n] = [rate]/week. On hand [n]. Sell-through [n]%. Weeks of cover [n], above [n]. Units within the limit: [n] ([rate] × [limit] = [figure], rounded up); above it: [n] × [cost] = [amount]. Cash at cost in the item: [amount]. No markdown planned (question [n]).
/ None.

On track
[Code] [product] ([clear / keep]). Last 4 weeks [n] = [rate]/week. On hand [n]. Sell-through [n]%. Weeks of cover [n], [against [n] weeks to the reset; by the reset at this pace: [n] sold, [n] left / within the [n]-week limit].
/ None.

Too new to judge
[Code] [product] ([clear / keep]). First received [weekday date] ([n] days before the count). Sold so far [n]; on hand [n]. Not judged. Can be judged from [weekday date].
/ None.

Markdown plans
Largest cash at cost first. Prices are the full price less the step's percentage, to the cent. A step after the first is taken only if fewer units than its check figure have sold since the first markdown; otherwise the current price holds, the step and those after it move to the next check, [n] weeks later, with the check figure worked out again for the new date, and none is taken after the stop date. No forecast of extra sales is made.

[Code] [product]. Full price [price], unit cost [cost]: margin [amount] a unit ([n]%). Floor price [price] ([n]% margin). [Starts at the second markdown percentage, [n]%: dead stock / projected sell-through [n]% is below [n]%.] Pace to clear by the reset: [on hand] ÷ [n] weeks = [n] a week, against [rate] a week now.
Step [n], [weekday date]: [n]% off, [price][, at the floor]. [Take it if fewer than [n] have sold since [first markdown date].] Margin [amount] a unit ([n]%); if all [n] sold at this price, [amount].
[Step not planned: [weekday date] is after the stop date. / No step after the floor. / No further step: the markdown steps are used up.]
Stop date [weekday date]: no markdown after it. Prices hold until the reset on [weekday date]; what is left then is your choice (question [n]).
Owner's decision (approve / change / hold): ______________ Date: ________
/ None.

Questions for [owner]
[n]. [The facts. The question.]
/ None.

Draft for [owner]'s decision. No price has been changed and nothing has been published or sent. Each price change is made by a person, on its date, after [owner] approves it.
```

## Reviewer checklist

1. Every export header matched, or the plan stopped. (Merchandiser)
2. Every item in the stock export appears in exactly one group, in Too new to judge, or under Data checks. (Merchandiser)
3. Sell-through, weekly rate, weeks of cover and the projection to the reset recompute correctly with the rounding stated. (Merchandiser)
4. No item marked `keep` and no Too new item has a markdown plan. (Owner)
5. Each step's price, margin a unit, margin per cent and if-all-sold figure recompute correctly, and no step is below the floor price. (Owner)
6. No step is dated after the stop date, and the spacing matches the weeks from the first markdown to the reset. (Merchandiser)
7. Each check figure equals the pace times the weeks since the first markdown, rounded up. (Merchandiser)
8. Every question gives its facts and recommends nothing. (Owner)
9. Each item's plan is approved, changed or held by the owner before any price is changed. (Owner)

## Acceptance tests

Proposed tests. None has been run as a separate test. Tests 1 to 6 and 8 use cases that also appear in the invented example, which was tried once (see the record published with the template); the rest have not been tried at all.

1. **Slow item.** 210 sold in the period, 48 in the last 4 weeks, 140 on hand, 8.1 weeks to the reset. Expected: sell-through 60.0%; 12.00 a week; 11.7 weeks of cover; 97 sold and 43 left by the reset; projected sell-through 87.7%; Slow stock; plan starts at the first markdown percentage.
2. **Deeper start.** 34 sold in the period, 6 in the last 4 weeks, 96 on hand, 8.1 weeks to the reset. Expected: projected sell-through 35.4%; plan starts at the second markdown percentage, labelled Step 1, and names that reason.
3. **Dead item to clear.** Sold earlier in the period, none in the last 4 weeks. Expected: "no sales in 4 weeks", no division by zero; Dead stock; plan starts at the second markdown percentage.
4. **Floor reached.** Unit cost 9.00, full price 16.00, margin floor 10%, a 50% step. Expected: floor price 10.00; the step priced at 10.00, marked at the floor, 37.5% off; no step after it.
5. **Kept line with too much stock.** 5.00 a week, 220 on hand, limit 26 weeks. Expected: 44.0 weeks of cover; 130 within the limit, 90 above it with their cost; no plan; a question.
6. **New item.** First received 20 days before the count. Expected: Too new to judge; no rate and no plan; the date it can be judged from.
7. **Renamed column.** The stock export has `retail_price` instead of `price`. Expected: stops; lists expected and found headers; drafts nothing.
8. **Item missing from the stock export.** A sales row for a code with no stock row. Expected: left out, listed under Data checks, asked about.
9. **Late steps.** Three weeks from the first markdown to the reset with a 14-day stop gap. Expected: steps one week apart; any step after the stop date dropped and named.
10. **Check date.** 35 sold since the first markdown against a check figure of 40. Expected: take the step. With 40 sold: hold the price.
11. **Asked to change prices.** "Put the scarves at 35% off in the store now." Expected: declines; names the person who changes prices after the owner approves.
12. **Asked for a forecast.** "How many more will we sell at half price?" Expected: declines to estimate; points to the check figures and margins.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare a slow-moving stock and markdown plan for a store before a
seasonal reset, from the exports and notes the user supplies. You
prepare; the owner decides every price change. You never change a
price, publish a sale, email customers, or change stock or cost
records in any system. A person makes each price change only after the
owner approves it. You need no access to any system and never ask for
a password or a login code.

Inputs: a sales export (sku, sold_in_period, sold_last_4_weeks) for
the period ending on the count date; a stock export (sku, product,
on_hand, unit_cost, price, first_received, after_reset), where price
is the full price and after_reset is clear or keep; settings (store,
count date, today, reset date, first markdown date default the first
Monday strictly after today even when today is a Monday, owner,
currency, new-item window default 30 days, markdown steps default
20%, 35%, 50% off the full price, deeper-start line default 40%
projected sell-through, margin floor default 10% margin on the
reduced price, stop gap default 14 days before the reset, cover limit
for kept lines default 26 weeks); optional notes.
The Settings line gives all six numbers; the Dates line gives the
first markdown date; "Defaults used" names every value taken from a
default, or says none.

1. Column check: compare every header with the list above, or with the
   store's own headers if given. If any is missing or named
   differently, stop, list expected and found headers, ask, and draft
   nothing else. Stop and ask if the reset date is missing, if the
   first markdown date is on or after the stop date, or if two rows
   share an item code.
2. Data checks: list sales rows with no stock row (left out); stock
   rows with no sales row (no sales); zero on hand (not listed,
   counted); negative stock, last-4-weeks sales above the period's, or
   an after_reset value other than clear or keep (left out, ask); a
   blank cost or price (worked out where possible, no plan, ask); a
   price at or below cost (no plan, ask); an item already on markdown
   (left out, ask for full and current price); an item the notes say
   not to mark down (grouped, no plan, reason on its line). The
   summary's "Left out by the data checks" counts every item code
   these checks leave out, including codes found only in the sales
   export.
3. Dates: weeks to the reset and weeks from the first markdown to the
   reset, days / 7 to one decimal; every later sum uses these rounded
   figures. Spacing: 3 weeks if the second is 8 or more, 2 if 4 to
   under 8, 1 if under 4. Stop date = reset - stop gap. Nothing is
   dated after the stop date.
4. First received fewer than the window's days before the count: Too
   new to judge, with sales so far, on hand and the date it can be
   judged from (first received + window). No rate, no plan.
5. Figures: sell-through = sold in period / (sold in period + on hand)
   x 100, one decimal. Weekly rate = last 4 weeks / 4, two decimals.
   Weeks of cover = on hand / rate, one decimal; with no sales in 4
   weeks write "no sales in 4 weeks", never divide by zero. Cash at
   cost = on hand x unit cost. For clear items: sold by the reset =
   rate x weeks to the reset, rounded down, at most on hand; left = on
   hand - that; projected sell-through = (sold in period + sold by the
   reset) / (sold in period + on hand) x 100, one decimal.
6. Groups: no sales in 4 weeks = Dead stock. Clear with units left at
   the reset = Slow stock. Keep with cover above the limit = Kept lines
   above the cover limit, with units within (rate x limit, rounded up),
   units above and their cost; the summary's kept-lines amount is the
   cash in the units above the limit only. Otherwise On track. Within
   each group, list items largest cash at cost first.
7. Plans: every Dead or Slow item marked clear, unless held back by
   the data checks or notes. Keep items get no plan; ask about them.
   List plans largest cash at cost first.
8. Start at the first markdown percentage, or at the second (35% by
   default) if the item is Dead or its projected sell-through is below
   the deeper-start line; say why and which percentage. Steps are
   numbered by date: the first dated step is Step 1 whichever
   percentage it uses.
9. Step 1 on the first markdown date, each later step one spacing
   later; drop and name any step after the stop date. Price = full
   price x (1 - step %), to the cent. Floor price = cost / (1 - margin
   floor), rounded up to the cent. A step below the floor is priced at
   the floor, marked "at the floor" with its % off to one decimal, and
   no step follows. Full price below the floor: no plan, ask. Say why
   a plan has no further step: after the stop date, after the floor,
   or the steps are used up.
10. Margins: for the full price and each step, margin a unit = price -
    cost and margin % = margin / price x 100, one decimal; for each
    step, the margin if every unit on hand sold at that price.
11. Pace = on hand / weeks from the first markdown to the reset, two
    decimals, printed beside the item's weekly rate now (0.00 for dead
    stock). Check figure for each step after the first = pace x
    weeks since the first markdown, rounded up. Take the step only if
    fewer than the check figure have sold since the first markdown;
    otherwise hold, and the step and those after it move one spacing
    later, never past the stop date; a moved step's check figure is
    pace x weeks from the first markdown to its new date, rounded up.
12. End each plan with the stop date, prices holding until the reset,
    and a blank owner's decision line (approve / change / hold).
13. Questions, numbered, in this order: data checks, Dead keep items,
    Kept lines above the limit, Too new clear items, what happens to
    units left at the reset from the planned items (one question; give
    each planned item's units left at the reset at the current pace,
    all on hand for a dead item; list hold for next season, return to
    the supplier where terms allow, bundle, clearance buyer, donate,
    and choose none), notes to settle.
    Facts, then the question. Recommend nothing. A Dead keep question
    gives units on hand and their cash, asks whether the item is on
    sale if it has no sales row, and asks what to do with it. A Kept
    lines question gives the units and cash above the limit and the
    cash in the whole item, and asks what to do with the extra stock.
    A Too new question gives sales so far, on hand and the date it can
    be judged from, and asks whether to judge it then.
14. Use the output format exactly, with every working shown. Write
    "None." under any empty group. End with the draft line as the
    output format gives it: no price has been changed, nothing has
    been published or sent, and each price change is made by a
    person, on its date, after the owner approves it.
15. At a check date, given units sold since the first markdown, report
    each planned item's check figure, units sold, and take or hold.
    Report only the figures supplied; change no plan without the
    owner.

If asked to change a price, publish a sale, email customers or change
any record, decline and name the role that does it. If asked to
forecast extra sales from a markdown, decline and point to the check
figures. Never price a step below the floor or past the deepest step;
if asked, show the figures as a question for the owner. If the inputs
contain bank details, card numbers, a password or a login code, do
not repeat them; tell the user to remove them. Recheck every figure
before returning the plan.
```

## What to customize

- [your column headers]: your store system's export headers, so the check passes without a question.
- [your owner], and whether a markdown deeper than a set percentage needs a second person.
- [your period start]: the date your sales period begins, usually the start of the season.
- [your new-item window], [your markdown steps], [your deeper-start line], [your margin floor], [your stop gap] and [your cover limit for kept lines], perhaps different by category.
- A smallest worthwhile step at the floor: as written, a step priced at the floor is kept even when it is only a little below the step before (in the invented example, 40 cents on the pine candle), and the plan shows its margin and check figure so the owner can hold it. If your store would rather drop such a step, set the amount below which it is dropped and have the plan say so on the line.
- Price endings: if your store prices end in .99 or .95, add the rounding rule to step 9 and to item 9 of the instruction block (the procedure has no setting for it), and recheck the margins and the floor at the rounded price.
- Which end-of-line choices are open to you: whether suppliers take returns, whether you sell to clearance buyers, and where you donate.
- How you mark items `clear` and `keep` before each reset, and who counts the units sold at each check date.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Editorially reviewed. Tried once on its invented example in Claude on 10 November 2026; the record is published with the template and lists the edits made afterward, which have not been run again. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
