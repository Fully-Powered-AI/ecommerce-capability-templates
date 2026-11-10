# Inventory reorder plan: an invented example

*Illustrative example with invented data.* The store, the suppliers, the products, the sales, the costs and every date below are invented. The store is an invented online tea shop, called the Store here, with nine stocked items from three suppliers, named Supplier A, B and C. Its buyer runs the plan each Monday and its owner approves every purchase order. People are referred to by role.

The inputs come first, in full, so the template can be run on them. The plan follows.

## The inputs

### 1. Settings (typed by the buyer)

```
Store: the Store
Stock counted: end of Sunday 8 November 2026
Today: Monday 9 November 2026
Approves purchase orders: the owner
Currency: US dollars
Safety days: 7
Days of cover per order: 30
Review: every 7 days; next review Monday 16 November 2026
Overstock: more than 180 days of cover
```

### 2. Supplier terms

```
supplier,lead_time_days,minimum_order
Supplier A,14,300
Supplier B,21,400
Supplier C,7,400
```

### 3. Stock export (as of the end of Sunday 8 November 2026)

```
sku,product,supplier,on_hand,unit_cost,pack_size,on_order,on_order_arrives,first_on_sale
TEA-01,Breakfast blend tin,Supplier A,60,6.50,12,0,,2025-03-02
TEA-02,Green sencha tin,Supplier A,58,7.20,12,0,,2025-03-02
TEA-03,Earl grey tin,Supplier A,24,6.80,12,36,2026-11-12,2025-03-02
GEAR-01,Glass teapot 600 ml,Supplier B,40,14.00,6,0,,2025-06-15
GEAR-02,Bamboo tea scoop,Supplier B,85,3.00,6,0,,2025-06-15
GEAR-03,Cast-iron kettle,Supplier B,30,38.00,2,0,,2025-09-07
GEAR-04,Tea tray,Supplier B,25,11.50,4,0,,2026-10-27
FIL-01,"Paper tea filters, pack of 100",Supplier C,140,2.40,24,0,,2025-03-02
FIL-02,Steel tea infuser,Supplier C,12,4.10,12,0,,2025-03-02
```

### 4. Weekly sales export (weeks end on Sunday)

```
week_ending,sku,units_sold
2026-10-18,TEA-01,35
2026-10-18,TEA-02,14
2026-10-18,TEA-03,20
2026-10-18,GEAR-01,9
2026-10-18,GEAR-03,1
2026-10-18,FIL-01,30
2026-10-18,FIL-02,12
2026-10-25,TEA-01,42
2026-10-25,TEA-02,16
2026-10-25,TEA-03,22
2026-10-25,GEAR-01,7
2026-10-25,FIL-01,28
2026-10-25,FIL-02,13
2026-10-25,TEA-09,5
2026-11-01,TEA-01,38
2026-11-01,TEA-02,40
2026-11-01,TEA-03,21
2026-11-01,GEAR-01,10
2026-11-01,GEAR-03,1
2026-11-01,GEAR-04,6
2026-11-01,FIL-01,33
2026-11-01,FIL-02,4
2026-11-08,TEA-01,39
2026-11-08,TEA-02,15
2026-11-08,TEA-03,21
2026-11-08,GEAR-01,18
2026-11-08,GEAR-03,1
2026-11-08,GEAR-04,9
2026-11-08,FIL-01,35
2026-11-08,FIL-02,14
```

### 5. Notes (typed by the buyer)

```
- TEA-02: 24 of the 40 units in the week ending 1 November were one
  wholesale order from a café. One-off; leave it out.
- FIL-02 was sold out from Monday 26 October to Saturday 31 October.
  Back in stock on Sunday 1 November.
- No seasonal changes expected over the next six weeks.
```

## The output

**INVENTORY REORDER PLAN: the Store, stock counted Sunday 8 November 2026**

- **For:** the owner. Prepared Monday 9 November 2026 from: sales export (weeks ending Sunday 18 October to Sunday 8 November, 30 rows), stock export (9 items), supplier terms (3 suppliers), settings, notes.
- **Column check:** all headers matched.
- **Settings:** safety days 7; days of cover per order 30; review every 7 days, next review Monday 16 November; overstock above 180 days of cover; stock count no older than 7 days; recent-rate question at 1.5 times the four-week rate. Defaults used: the stock count age limit and the recent-rate threshold.
- **Summary:** 3 draft purchase orders, \$3,571.20. Order now: 4 items, 3 SHORT. Order at the next review: 1. No order needed: 1. Not moving: 1, \$255.00. Overstocked: 1, \$1,140.00, of which \$380.00 above the limit. Too little history: 1. Left out by the data checks: 1.

**Data checks**

- TEA-09 is in the sales export (5 units, week ending 25 October) and not in the stock export. Left out of the plan; see question 4.
- GEAR-02 has no rows in the sales export. Read as no sales; see question 5.
- GEAR-03 has no row for the week ending 25 October. Read as no sales that week.

**Order now**

- **TEA-01** Breakfast blend tin (Supplier A). Sales: 154 in 28 days in stock = 5.50/day; last 7 days 39 = 5.57/day. On hand 60; nothing on order. Runs out by Wednesday 18 November at 5.57/day (10 days). Lead time 14 days: an order placed today arrives Monday 23 November. **SHORT: 5 days with no stock.** Safety stock 40 ((5.57 − 5.50) × 14 + 5.50 × 7 = 39.48, rounded up). Reorder point 117 (5.50 × 14 + 40). Stock position 60. Target 282 (117 + 5.50 × 30). Order 228 (222 needed, 19 packs of 12) = \$1,482.00.
- **TEA-03** Earl grey tin (Supplier A). Sales: 84 in 28 days in stock = 3.00/day; last 7 days 21 = 3.00/day. On hand 24; 36 on order, arriving Thursday 12 November, counted (it arrives before the 24 on hand run out on Monday 16 November). Runs out by Saturday 28 November at 3.00/day (20 days). Lead time 14 days: an order placed today arrives Monday 23 November. Safety stock 21 ((3.00 − 3.00) × 14 + 3.00 × 7). Reorder point 63 (3.00 × 14 + 21). Stock position 60. Target 153 (63 + 3.00 × 30). Order 96 (93 needed, 8 packs of 12) = \$652.80.
- **GEAR-01** Glass teapot 600 ml (Supplier B). Sales: 44 in 28 days in stock = 1.57/day; last 7 days 18 = 2.57/day, at least one and a half times the four-week rate (question 2). On hand 40; nothing on order. Runs out by Monday 23 November at 2.57/day (15 days). Lead time 21 days: an order placed today arrives Monday 30 November. **SHORT: 7 days with no stock.** Safety stock 32 ((2.57 − 1.57) × 21 + 1.57 × 7 = 31.99, rounded up). Reorder point 65 (1.57 × 21 + 32 = 64.97, rounded up). Stock position 40. Target 113 (65 + 1.57 × 30 = 112.10, rounded up). Order 78 (73 needed, 13 packs of 6) = \$1,092.00.
- **FIL-02** Steel tea infuser (Supplier C). Sales: 43 in 22 days in stock = 1.95/day; left out: 6 sold-out days, 26 to 31 October, per the notes; last 7 days 14 = 2.00/day. On hand 12; nothing on order. Runs out by Saturday 14 November at 2.00/day (6 days). Lead time 7 days: an order placed today arrives Monday 16 November. **SHORT: 2 days with no stock.** Safety stock 14 ((2.00 − 1.95) × 7 + 1.95 × 7 = 14.00). Reorder point 28 (1.95 × 7 + 14 = 27.65, rounded up). Stock position 12. Target 87 (28 + 1.95 × 30 = 86.50, rounded up). Order 84 (75 needed, 7 packs of 12) = \$344.40.

**Order at the next review**

- **TEA-02** Green sencha tin (Supplier A). Sales: 61 in 28 days in stock = 2.18/day; left out: 24 units in the week ending 1 November, a one-off café order, per the notes; last 7 days 15 = 2.14/day. On hand 58; nothing on order. Runs out by Friday 4 December at 2.18/day (26 days). Safety stock 16 ((2.18 − 2.18) × 14 + 2.18 × 7 = 15.26, rounded up). Reorder point 47 (2.18 × 14 + 16 = 46.52, rounded up). Stock position 58, above the reorder point and at or below the next-review line of 63 (47 + 2.18 × 7 = 62.26, rounded up): order at the review on Monday 16 November.

**No order needed**

- **FIL-01** Paper tea filters, pack of 100 (Supplier C). Four-week rate 4.50/day (126 in 28 days), recent 5.00/day (35 in 7 days). Stock position 140; reorder point 67; next-review line 99. Runs out by Sunday 6 December.

**Not moving**

- **GEAR-02** Bamboo tea scoop (Supplier B). No sales in the last 28 days; no rows in the sales export. On hand 85 × \$3.00 = \$255.00. Not reordered.

**Overstocked**

- **GEAR-03** Cast-iron kettle (Supplier B). Sales: 3 in 28 days in stock = 0.11/day. Stock position 30 = 272 days of cover, above 180. Units above the limit: 10 (30 − 20, where 0.11 × 180 = 19.80, rounded up to 20) = \$380.00. Cash in the item: 30 × \$38.00 = \$1,140.00. Not reordered.

**Too little history**

- **GEAR-04** Tea tray (Supplier B). On sale since Tuesday 27 October (13 days). Sales so far: 6 in the week ending 1 November, 9 in the week ending 8 November. On hand 25. No rate, date or order given. Can be rated from Monday 23 November.

**Draft purchase orders**

DRAFT, NOT SENT. **Supplier A.** PO number: to be assigned. Order date: Monday 9 November 2026, if approved today. Requested delivery: Monday 23 November 2026 (14-day lead time).

- TEA-01 Breakfast blend tin: 228 (19 packs of 12) at \$6.50 = \$1,482.00.
- TEA-03 Earl grey tin: 96 (8 packs of 12) at \$6.80 = \$652.80.
- Total: \$2,134.80. Prices: last cost in the stock export as of Sunday 8 November 2026; supplier to confirm. Minimum order \$300.00: reached.
- Approved to send: ______________ Date: ________

DRAFT, NOT SENT. **Supplier B.** PO number: to be assigned. Order date: Monday 9 November 2026, if approved today. Requested delivery: Monday 30 November 2026 (21-day lead time).

- GEAR-01 Glass teapot 600 ml: 78 (13 packs of 6) at \$14.00 = \$1,092.00.
- Total: \$1,092.00. Prices: last cost in the stock export as of Sunday 8 November 2026; supplier to confirm. Minimum order \$400.00: reached.
- Approved to send: ______________ Date: ________

DRAFT, NOT SENT. **Supplier C.** PO number: to be assigned. Order date: Monday 9 November 2026, if approved today. Requested delivery: Monday 16 November 2026 (7-day lead time).

- FIL-02 Steel tea infuser: 84 (7 packs of 12) at \$4.10 = \$344.40.
- Total: \$344.40. Prices: last cost in the stock export as of Sunday 8 November 2026; supplier to confirm. Minimum order \$400.00: below minimum by \$55.60, see question 3.
- Approved to send: ______________ Date: ________

**Questions for the owner**

1. Three items run out before an order placed today can arrive: TEA-01 by Wednesday 18 November, with Supplier A's delivery on Monday 23 November (5 days with no stock); GEAR-01 by Monday 23 November, with Supplier B's delivery on Monday 30 November (7 days); FIL-02 by Saturday 14 November, with Supplier C's delivery on Monday 16 November (2 days). Do you want to ask any of these suppliers for an earlier delivery?
2. GEAR-01 sold 18 last week, 2.57 a day, against 1.57 a day over four weeks. The runs-out date uses 2.57; the order is sized on 1.57. Is last week a new trend or a one-off?
3. Supplier C's order is \$344.40 against a \$400.00 minimum, \$55.60 short. The smallest additions that reach it: FIL-02, 2 more packs: 24 units, \$98.40, new total \$442.80, 12 more days of cover at 1.95 a day. FIL-01 (no order needed yet), 1 pack: 24 units, \$57.60, new total \$402.00, 5 more days of cover at 4.50 a day. Which, if either, do you want, or do you want to ask Supplier C to accept the smaller order?
4. TEA-09 sold 5 in the week ending 25 October but has no row in the stock export. Which product is it, and should it be in the stock export?
5. GEAR-02 has no sales in four weeks and 85 on hand, \$255.00. Is it on sale? If so, what do you want done with it?
6. GEAR-03 holds 10 units, \$380.00, above the 180-day limit, and \$1,140.00 in all. What do you want done with the extra stock?
7. GEAR-04 has been on sale 13 days: 6 sold in its first week, 9 in its second, 25 on hand, with a 21-day lead time from Supplier B. It can be rated from Monday 23 November. Do you want to give an expected weekly figure so it can be planned sooner?

Draft for the owner's decision. Nothing has been ordered, sent or changed in any system. Each purchase order goes to its supplier only after a person approves it.
