---
name: "inventory-reorder-plan"
description: "Prepare one reorder plan for a store from its weekly sales export, its stock export and its supplier terms: each item's sales rate, the earliest day it could run out, its safety stock and reorder point, the quantity to order in whole supplier packs with its cost, the items not moving or overstocked with the cash in them, one draft purchase order per supplier, and the questions only the owner can answer. Every figure traces to an input, and the arithmetic is written out beside each item. The assistant prepares; it never places an order, sends a purchase order, contacts a supplier or changes a stock record."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "Fully Powered AI"
  template: "Inventory reorder plan"
---

# Inventory reorder plan

This is the technical file for a Fully Powered workflow template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example with invented data is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

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

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
