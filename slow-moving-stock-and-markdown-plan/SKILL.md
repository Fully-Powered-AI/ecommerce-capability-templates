---
name: "slow-moving-stock-and-markdown-plan"
description: "Prepare one plan for a store before a seasonal reset from its sales export, its stock export and its settings: each item's sell-through, weekly sales rate and weeks of cover, which items are dead, slow, on track, too new to judge or kept after the reset with too much stock, the cash at cost tied up in each, and, for every dead or slow item that has to be cleared, a markdown plan in dated steps with the price, the margin each step leaves, the sales figure that decides whether the next step is taken, and the date after which no further markdown is made. Every figure traces to an input, and the arithmetic is written out beside each item. The assistant prepares; the owner decides every price change. It never changes a price, publishes a sale, emails customers or changes a stock record."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "Fully Powered AI"
  capability: "Slow-moving stock and markdown plan"
---

# Slow-moving stock and markdown plan

This is the technical file for a Fully Powered capability template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example with invented data is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

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

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
