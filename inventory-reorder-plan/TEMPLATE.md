# Inventory reorder plan

Capability template, version 0.1.0.

## Purpose

Prepare one reorder plan for a store from its weekly sales export, its stock export and its supplier terms: each item's sales rate, the earliest day it could run out, its safety stock and reorder point, the quantity to order in whole supplier packs with its cost, the items not moving or overstocked with the cash in them, one draft purchase order per supplier, and the questions only the owner can answer. Every figure traces to an input, and the arithmetic is written out beside each item. The assistant prepares; it never places an order, sends a purchase order, contacts a supplier or changes a stock record.

## When to use it and when not to

Use it on the store's regular stock review, usually weekly, straight after exporting sales and stock. Run it again after a stock count, or when a supplier changes its delivery time, pack size or minimum order.

Do not use it:

- to choose between suppliers or compare quotes. That is a separate piece of work;
- to check supplier bills or prepare a payment run once goods arrive;
- to plan stock for a product that has never been sold, or for a launch, where there is no sales history to work from;
- to forecast a season the store's own history does not show. The owner gives any seasonal change; the plan never estimates one;
- to set prices, plan a sale or decide how to clear slow stock. The plan lists the stock; the owner decides what happens to it.

## Roles

- **Runs it:** the buyer, the operations lead or the store owner.
- **Answers the questions and approves each purchase order:** [your approver], usually the owner. Each supplier's order is approved on its own.
- **Sends an approved purchase order to the supplier:** the person the store names. Always a person.
- **Records the order in the store system:** the person the store names, after approval.

## Inputs

The assistant works only from the exports and notes the person supplies. It needs no connection to the store system, the accounts or any supplier's site, and never asks for a password or a login code.

1. **The weekly sales export.** One row per item per week, for the four weeks ending on the day of the stock count. Default column headers: `week_ending`, `sku`, `units_sold`. Weeks with no sales may be missing; a missing week is read as no sales that week and listed under Data checks.
2. **The stock export.** One row per item. Default column headers: `sku`, `product`, `supplier`, `on_hand`, `unit_cost`, `pack_size`, `on_order`, `on_order_arrives`, `first_on_sale`. `on_order` is 0 and `on_order_arrives` blank when nothing is on order. `unit_cost` is the last price paid, before tax and delivery.
3. **Supplier terms.** One row per supplier. Default column headers: `supplier`, `lead_time_days`, `minimum_order`. `lead_time_days` is the days from sending an order to the goods being ready to sell. `minimum_order` is the smallest order value the supplier accepts, 0 if none.
4. **The settings,** typed: the store, when the stock was counted, today's date, who approves purchase orders, the currency, and the store's numbers. Defaults when a number is not given: [your safety days], default 7; [your days of cover per order], default 30; [your review interval], default 7 days; [your overstock limit], default 180 days of cover; [your count age limit], default 7 days; [your jump threshold], default one and a half times the four-week rate. The Settings line of the plan gives all six numbers and names, after "Defaults used", each one that came from a default rather than from the settings typed.
5. **Notes** (optional): days an item was sold out, with the first and last date; sales to leave out as one-off orders, with the item, week and units; any change the owner expects in coming weeks. If none are supplied, write "no notes supplied" in the header.

**Column check.** Before any arithmetic, compare each export's headers with the defaults, or with the store's own headers if [your column headers] are set. If a header is missing or named differently, stop. List the headers expected and the headers found, ask which column is which, and draft nothing else. Never guess a column.

## The procedure

1. **Check the inputs.** Run the column check. Confirm the stock count date, today's date and that the newest week in the sales export ends on the count date; if it does not, stop and ask. If the count is more than [your count age limit] before today, stop and ask for a fresh count.
2. **Check the data.** List, under Data checks: an item in the sales export that is not in the stock export (left out of the plan); an item in the stock export with no sales rows (read as no sales); a missing week for an item (read as no sales that week); negative stock on hand (that item is left out until recounted); a supplier in the stock export with no terms (its items are left out until the lead time and minimum are supplied); a blank unit cost or pack size (the item's figures are worked out, but it is left off any purchase order). Two rows with the same item code: stop and ask. The summary's "Left out by the data checks" counts every item code these checks leave out of the plan, including codes found only in the sales export.
3. **Sort out the history.** An item first on sale fewer than 28 days before the count, counting both days, or in stock on fewer than 14 of the last 28 days, goes to Too little history: no rate, no date, no order. Never stretch a short history into a rate. For a new item, "can be rated from" is its 28th day on sale (first on sale + 27 days); for an item short of days in stock, write that it can be rated once it has been in stock 14 of the last 28 days.
4. **Work out the two sales rates.** For each remaining item, take units sold in the four weeks and in the last week. Subtract any one-off order the notes name. Count the days the item was in stock in each window: 28 or 7, less the sold-out days the notes give in that window. Four-week rate = four-week units ÷ in-stock days. Recent rate = last week's units ÷ its in-stock days; if the item was sold out all of last week, use the four-week rate and say so. Round both to two decimal places and use the rounded figures from here on. If the recent rate is at least [your jump threshold] times the four-week rate, add a question asking whether it is a trend or a one-off; change nothing.
5. **Separate the items that should not be ordered.** Four-week units of zero: Not moving, with on hand × unit cost as the cash in it. Otherwise, stock position = on hand + on order. If the position ÷ four-week rate is more than [your overstock limit], the item is Overstocked: show the days of cover (rounded down); the units within the limit (four-week rate × the limit, rounded up to whole units); the units above the limit (stock position less the units within the limit) and their cost; and the cash in the item. Neither group is ever reordered or put on a purchase order.
6. **Date the stock-out, on the cautious side.** Use the higher of the two rates. Days of cover = on hand ÷ that rate, rounded down. If stock on order arrives on or before the day the stock on hand runs out, count it too and recompute. Runs-out date = count date + days of cover. Arrival date for an order placed today = today + the supplier's lead time. If the runs-out date is earlier than the arrival date, mark the item SHORT, in whichever group it lands, with the number of days with no stock: from the runs-out date to the arrival date, or to the day the stock on order arrives if it was not counted and arrives before the arrival date.
7. **Set safety stock and the reorder point.** Safety stock = (higher rate − four-week rate) × lead time + four-week rate × [your safety days], rounded up to whole units. The first part covers sales running at the recent pace during the wait for delivery; the second covers a late delivery or an unusual week. Reorder point = four-week rate × lead time + safety stock, rounded up.
8. **Decide the group.** If the stock position is at or below the reorder point: Order now. Otherwise, if it is at or below the next-review line (reorder point + four-week rate × [your review interval], rounded up): Order at the next review, with the review date. Otherwise: No order needed. An item can be SHORT in Order at the next review or No order needed when stock on order arrives after the stock on hand runs out; it keeps its SHORT note on its line and in the summary.
9. **Size each order.** Target = reorder point + four-week rate × [your days of cover per order], rounded up. Quantity needed = target − stock position. Round up to whole packs, then cost the units ordered at the unit cost; if the pack size or unit cost is blank, follow the exception for it below. Never size an order on the recent rate, and never order for an item outside Order now.
10. **Draft the purchase orders.** One per supplier with at least one Order now item. Each carries: "PO number: to be assigned", the order date as today if approved today, the requested delivery date as the arrival date, each line (code, product, units, packs, unit cost, line cost), the total, the note that prices are the last cost in the stock export as of the count date for the supplier to confirm, the minimum order and whether it is reached, and a blank approval line. An Order now item with a blank unit cost or pack size is not a line: the purchase order names it as left off, with the missing figure and its question. A supplier whose Order now items are all left off gets no purchase order.
11. **Check each supplier's minimum.** The total and the minimum check count only the lines on the order, never an item left off. If a purchase order total is below the minimum, keep the order as sized and mark it "below minimum". Under Questions, show the smallest number of whole packs that would reach the minimum for each item on that order and for each other item from the same supplier in Order at the next review or No order needed: the extra units, the extra cost, the new total and the extra days of cover at the four-week rate, rounded down. Leave out of these additions any item with a blank unit cost or pack size. Recommend none.
12. **Write the questions,** numbered, in this order: SHORT items, from any group; recent-rate jumps; supplier minimums not reached; data checks needing an answer, including a blank unit cost or pack size; Not moving and Overstocked items; Too little history items; any change the owner expects (show the order at the four-week rate and at the owner's figure; the draft uses the four-week figure until the owner chooses). Each question gives the facts and asks; none recommends. All SHORT items share one question. Every other question covers one item, or one supplier for a minimum; an item with both a data-check question and a Not moving or Overstocked question gets one question, in the Not moving and Overstocked place, and its data-check line points to it. A Not moving question gives the units on hand and the cash in them, asks whether the item is on sale if it has no rows in the sales export, and asks what the owner wants done with it. An Overstocked question gives the units and cash above the limit and the cash in all, and asks what the owner wants done with the extra stock. A Too little history question gives the sales so far, the stock on hand, the supplier's lead time and the date the item can be rated from, and asks whether the owner wants to give an expected weekly figure so it can be planned sooner.
13. **Return the plan** to the person who ran it, for [your approver]. The approver answers the questions and approves or holds each purchase order. A person sends the approved orders and records them.

## Exceptions and stop conditions

- **A column header is missing or named differently:** stop; list expected and found headers; ask.
- **The newest sales week does not end on the count date, or the count is older than the limit:** stop and ask.
- **Two rows with the same item code:** stop and ask which is which.
- **Negative stock on hand:** leave the item out, list it under Data checks, and ask for a recount.
- **A unit cost or pack size is blank:** list it under Data checks and work out the item's figures. If it qualifies for Order now, its Order line gives the units needed (and the packs, if only the cost is blank) with "cost not stated" or "pack size not stated" in place of the missing figure. Leave it off the purchase order, which names it as left off and counts only its other lines toward the total and the minimum, and ask for the figure. Never guess either.
- **Asked to order, send a purchase order, email a supplier, or change stock, costs or reorder settings in any system:** decline; name the role that does it.
- **Asked to estimate a season, a launch or a promotion without the owner's figure:** decline; ask the owner for the figure.
- **Asked to pad an order to reach a supplier's minimum, or to size an order on the recent rate:** show the figures under Questions and leave the choice to the approver.
- **The inputs contain bank details, card numbers, a password or a login code:** do not repeat them; tell the person to remove them from the source.

## Output format

```
INVENTORY REORDER PLAN: [store], stock counted [weekday date]

For: [approver]. Prepared [weekday date] from: sales export ([weeks ending first to last], [n] rows), stock export ([n] items), supplier terms ([n] suppliers), settings, [notes / no notes supplied].
Column check: all headers matched. / Stopped: expected [headers]; found [headers].
Settings: safety days [n]; days of cover per order [n]; review every [n] days, next review [weekday date]; overstock above [n] days of cover; stock count no older than [n] days; recent-rate question at [n] times the four-week rate. Defaults used: [the numbers that came from a default / none].
Summary: [n] draft purchase orders, [total]. Order now: [n] items, [n] SHORT. Order at the next review: [n][, [n] SHORT]. No order needed: [n][, [n] SHORT]. Not moving: [n], [cash]. Overstocked: [n], [cash], of which [amount] above the limit. Too little history: [n]. Left out by the data checks: [n].

Data checks
[Finding; what was done.] / No problems found.

Order now
[Code] [product] ([supplier]). Sales: [units] in [n] days in stock = [rate]/day[; left out: ...]; last 7 days [units] = [rate]/day[, at least [one and a half / the threshold] times the four-week rate (question [n])]. On hand [n]; [nothing on order / [n] on order, arriving [weekday date], counted (it arrives before the [n] on hand run out on [weekday date]) / not counted (it arrives after they run out)]. Runs out by [weekday date] at [rate]/day ([n] days). Lead time [n] days: an order placed today arrives [weekday date].[ SHORT: [n] days with no stock[, until the [n] on order arrive on [weekday date]].] Safety stock [n] ([working]). Reorder point [n] ([working]). Stock position [n]. Target [n] ([working]). Order [units] ([needed] needed, [n] packs of [n]) = [cost]. / Order: [needed] needed[, [n] packs of [n]]; [cost / pack size] not stated, so left off the purchase order (question [n]).
/ None.

Order at the next review
[Code] [product] ([supplier]). Sales: ... Runs out by [weekday date] at [rate]/day ([n] days).[ SHORT: [n] days with no stock, until [the [n] on order arrive / an order placed today would arrive] on [weekday date].] Safety stock [n] ([working]). Reorder point [n] ([working]). Stock position [n], above the reorder point and at or below the next-review line of [n] ([working]): order at the review on [weekday date].
/ None.

No order needed
[Code] [product] ([supplier]). Four-week rate [rate]/day ([units] in [n] days), recent [rate]/day ([units] in [n] days). Stock position [n]; reorder point [n]; next-review line [n]. Runs out by [weekday date].[ SHORT: [n] days with no stock, until [the [n] on order arrive / an order placed today would arrive] on [weekday date].]
/ None.

Not moving
[Code] [product] ([supplier]). No sales in the last 28 days[; no rows in the sales export]. On hand [n] × [cost] = [cash]. Not reordered.
/ None.

Overstocked
[Code] [product] ([supplier]). Sales: [units] in [n] days in stock = [rate]/day. Stock position [n] = [n] days of cover, above [limit]. Units above the limit: [n] ([position] − [units within], where [rate] × [limit] = [figure], rounded up to [units within]) = [amount]. Cash in the item: [n] × [cost] = [cash]. Not reordered.
/ None.

Too little history
[Code] [product] ([supplier]). On sale since [weekday date] ([n] days) / in stock [n] of the last 28 days. Sales so far: [weeks and units]. On hand [n]. No rate, date or order given. Can be rated from [weekday date] / Can be rated once in stock 14 of the last 28 days.
/ None.

Draft purchase orders
DRAFT, NOT SENT. [Supplier]. PO number: to be assigned. Order date: [weekday date], if approved today. Requested delivery: [weekday date] ([n]-day lead time).
[Code] [product]: [units] ([n] packs of [n]) at [unit cost] = [line cost].
[Left off: [code] [product], [needed] needed; [cost / pack size] not stated, see question [n]. Not counted in the total or the minimum.]
Total: [amount]. Prices: last cost in the stock export as of [count date]; supplier to confirm. Minimum order [amount]: reached / below minimum by [amount], see question [n].
Approved to send: ______________ Date: ________
/ None.

Questions for [approver]
[n]. [The facts. The question.]
/ None.

Draft for [approver]'s decision. Nothing has been ordered, sent or changed in any system. Each purchase order goes to its supplier only after a person approves it.
```

## Reviewer checklist

1. Every export header matched, or the plan stopped. (Buyer)
2. Every item in the stock export appears in exactly one group, or is left out under Data checks. (Buyer)
3. Each rate uses the in-stock days and leaves out only the one-off orders the notes name. (Buyer)
4. Each runs-out date uses the higher rate and counts stock on order only when it arrives first. (Buyer)
5. Safety stock, reorder point, target and quantity recompute correctly with the rounding stated. (Buyer)
6. No Not moving, Overstocked or Too little history item is on a purchase order. (Approver)
7. Each purchase order total equals the sum of its lines, and a total below the supplier's minimum is marked, not padded. (Approver)
8. Every question gives its facts and recommends nothing. (Approver)
9. Each purchase order is approved, or held, separately before anyone sends it. (Approver)

## Acceptance tests

Proposed tests. None has been run as a separate test. Tests 1 and 3 to 10 use cases that also appear in the invented example, which was tried once (see the record published with the template); the rest have not been tried at all.

1. **Steady item.** 84 units in four weeks, 21 last week, lead time 14 days, on hand 24, 36 on order arriving in four days. Expected: rates 3.00 and 3.00; stock on order counted; runs out in 20 days; safety stock 21; reorder point 63; order now; target 153; 96 units in packs of 12.
2. **Renamed column.** The stock export has `qty_on_hand` instead of `on_hand`. Expected: stops; lists expected and found headers; drafts nothing.
3. **Sold-out days.** 43 units in four weeks with 6 sold-out days. Expected: four-week rate 1.95 (43 ÷ 22), not 1.54.
4. **One-off order.** The notes name 24 units in one week as a one-off. Expected: left out of both rates and named on the line.
5. **Recent jump.** Four-week rate 1.57, recent 2.57. Expected: runs-out date on 2.57, order sized on 1.57, a question asking trend or one-off.
6. **No sales.** An item with stock and no sales rows. Expected: Not moving, with the cash in it; not on any purchase order; a data-check line and a question.
7. **Overstock.** 3 units in four weeks, position 30, limit 180 days. Expected: Overstocked; 272 days of cover; 20 units within the limit (0.11 × 180 = 19.80, rounded up); 10 units above it; not reordered.
8. **New item.** First on sale 13 days before the count. Expected: Too little history; no rate, date or order.
9. **Below minimum.** A purchase order of $344.40 with a $400 minimum. Expected: kept as sized, marked below minimum; the smallest pack additions shown with cost and extra days; nothing recommended.
10. **Item missing from the stock export.** Sales rows for a code with no stock row. Expected: left out, listed under Data checks, asked about.
11. **Asked to send.** "Email the order to the supplier." Expected: declines; names the person who sends approved orders.
12. **Owner's seasonal figure.** The notes say "expect double sales of filters from 1 December". Expected: a question showing the order at the four-week rate and at double; the draft keeps the four-week figure.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare an inventory reorder plan for a store from the exports and
notes the user supplies. You prepare; people decide. You never place an
order, send a purchase order, contact a supplier, or change stock, costs
or settings in any system. Each purchase order is approved by a person
before anyone sends it. You need no access to any system and never ask
for a password or a login code.

Inputs: a weekly sales export (week_ending, sku, units_sold) for the
four weeks ending on the stock count date; a stock export (sku, product,
supplier, on_hand, unit_cost, pack_size, on_order, on_order_arrives,
first_on_sale); supplier terms (supplier, lead_time_days,
minimum_order); settings (store, count date, today, approver, currency,
safety days default 7, days of cover per order default 30, review
interval default 7 days, overstock limit default 180 days of cover,
count age limit default 7 days, jump threshold default 1.5 times the
four-week rate); optional notes (sold-out dates, one-off orders,
expected changes). The Settings line gives all six numbers and names,
after "Defaults used", each one taken from a default, or says none.

1. Column check: compare every header with the list above, or with the
   store's own headers if given. If any is missing or named differently,
   stop, list expected and found headers, ask, and draft nothing else.
   If the newest sales week does not end on the count date, or the count
   is older than the count age limit, stop and ask. Two rows with one
   item code: stop and ask.
2. Data checks: list items in sales but not stock (left out), items with
   no sales rows (read as no sales), missing weeks (read as no sales
   that week), negative stock (left out, ask for a recount), items whose
   supplier has no terms (left out, ask for lead time and minimum), a
   blank unit cost or pack size (worked out, but kept off any purchase
   order; ask for it). The summary's "Left out by the data checks"
   counts every item code left out, including codes found only in the
   sales export.
3. Too little history: first on sale fewer than 28 days before the count
   (counting both days) or in stock fewer than 14 of the last 28 days.
   Give no rate, date or order. A new item can be rated from its 28th
   day on sale (first on sale + 27 days); an item short of in-stock
   days, once it has been in stock 14 of the last 28 days.
4. Rates: subtract one-off orders named in the notes. In-stock days are
   28 (or 7) less the sold-out days the notes give in that window.
   Four-week rate = four-week units / in-stock days; recent rate = last
   week's units / its in-stock days (if sold out all week, use the
   four-week rate and say so). Round to 2 decimals and use the rounded
   figures. If recent >= jump threshold x four-week, ask: trend or
   one-off?
5. Zero units in four weeks: Not moving, cash = on hand x unit cost.
   Position = on hand + on order. If position / four-week rate exceeds
   the overstock limit: Overstocked, with days of cover (rounded down),
   units within the limit (four-week rate x limit, rounded up to whole
   units), units above the limit (position - units within the limit)
   and their cost, and the cash in the item. Never order these.
6. Runs-out date: days = on hand / higher rate, rounded down; if stock
   on order arrives on or before that day, include it and recompute.
   Date = count date + days. Arrival = today + lead time. If the
   runs-out date is before arrival, mark SHORT, in whichever group the
   item lands, with the days with no stock: from the runs-out date to
   arrival, or to the day uncounted stock on order arrives if that is
   earlier.
7. Safety stock = (higher rate - four-week rate) x lead time + four-week
   rate x safety days, rounded up. Reorder point = four-week rate x lead
   time + safety stock, rounded up.
8. Position <= reorder point: Order now. Else position <= next-review
   line (reorder point + four-week rate x review interval, rounded up):
   Order at the next review, with its date. Else: No order needed.
   A SHORT item in either of the last two groups (stock on order
   arriving after the stock on hand runs out) keeps SHORT on its line
   and in the summary.
9. Order now only: target = reorder point + four-week rate x days of
   cover per order, rounded up; needed = target - position; round up to
   whole packs; cost = units x unit cost. Never size on the recent rate.
   If cost or pack size is blank, give the units needed (and packs if
   only the cost is blank), write "cost not stated" or "pack size not
   stated", keep the item off the purchase order and ask.
10. One draft purchase order per supplier with Order now items: "PO
    number: to be assigned", order date today if approved today,
    requested delivery = arrival date, lines, total, prices as the last
    cost at the count date for the supplier to confirm, the minimum and
    whether it is reached, and a blank approval line. Name any item
    left off for a blank cost or pack size; it is not a line and is
    not counted in the total or the minimum. No purchase order for a
    supplier whose Order now items are all left off.
11. If a total is below the supplier's minimum, do not pad it. Under
    Questions, for each item on that order and each other item from the
    same supplier in Order at the next review or No order needed, show
    the fewest whole packs that reach the minimum, with extra units,
    extra cost, new total and extra days of cover at the four-week rate
    (rounded down). Never offer an item with a blank cost or pack size
    as an addition. Recommend none.
12. Questions, numbered, in this order: SHORT items from any group,
    recent-rate jumps, minimums not reached, data checks (including a
    blank cost or pack size), Not moving and Overstocked, Too
    little history, owner's expected changes (show the order at the
    four-week rate and at the owner's figure; the draft keeps the
    four-week figure). Facts, then the question. Recommend nothing.
    All SHORT items share one question. Every other question covers
    one item, or one supplier for a minimum; an item with a data-check
    question and a Not moving or Overstocked question gets one
    question, in the Not moving and Overstocked place, and its
    data-check line points to it. Not moving: give the units on hand
    and the cash in them; if the item has no sales rows, ask whether it
    is on sale; ask what the owner wants done with it. Overstocked: give
    the units and cash above the limit and the cash in all; ask what the
    owner wants done with the extra stock. Too little history: give the
    sales so far, stock on hand, the supplier's lead time and the date
    it can be rated from; ask whether the owner wants to give an
    expected weekly figure so it can be planned sooner.
13. Use the output format exactly, with every working shown. Write
    "None." under any empty group. End with the draft line saying
    nothing has been ordered, sent or changed.

If asked to order, send, email a supplier or change any record, decline
and name the role that does it. If asked to estimate a season, launch or
promotion without the owner's figure, decline and ask for the figure.
If the inputs contain bank details, card numbers or a password, do not
repeat them; tell the user to remove them. Recheck every figure before
returning the plan.
```

## What to customize

- [your column headers]: your store system's export headers, so the check passes without a question.
- [your approver], and whether orders above a set amount need a second approver.
- [your safety days], [your days of cover per order], [your review interval] and [your overstock limit], perhaps different for fast and slow lines.
- [your count age limit]: how old a stock count may be before the plan asks for a fresh one.
- [your jump threshold]: the recent-rate jump that raises a question, one and a half times the four-week rate by default.
- Purchase order details: numbering, delivery address, payment terms, and who sends approved orders and how.
- How sold-out days and one-off orders are recorded, so the notes are ready each week.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Editorially reviewed. Tried once on its invented example in Claude on 10 November 2026; the record is published with the template and lists the edits made afterward, which have not been run again. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
