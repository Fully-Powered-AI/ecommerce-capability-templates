# Slow-moving stock and markdown plan: an invented example

*Illustrative example with invented data.* The store, the products, the sales, the costs, the prices and every date below are invented. The store is an invented winter accessories and homeware shop that sells online and from one shop front, called the Store here. Its merchandiser runs the plan two months before the spring range goes out, and its owner decides every price change. People are referred to by role.

The inputs come first, in full, so the template can be run on them. The plan follows.

## The inputs

### 1. Settings (typed by the merchandiser)

```
Store: the Store
Stock counted: end of Sunday 3 January 2027
Today: Monday 4 January 2027
Reset: Monday 1 March 2027 (spring range goes out)
Sales period: Monday 5 October 2026 to Sunday 3 January 2027
Decides: the owner
Currency: US dollars
New-item window: 30 days
Markdown steps: 20%, 35%, 50% off the full price
Margin floor: 10%
Cover limit for kept lines: 26 weeks
```

### 2. Stock export (as of the end of Sunday 3 January 2027)

```
sku,product,on_hand,unit_cost,price,first_received,after_reset
HAT-01,Wool beanie,140,6.00,24.00,2026-10-05,clear
SCF-02,Cashmere-blend scarf,96,18.00,59.00,2026-10-05,clear
GLV-03,Touchscreen gloves,60,7.50,19.00,2026-10-05,clear
CND-04,Pine candle,75,9.00,16.00,2026-10-19,clear
MUG-05,Stoneware mug,220,4.00,14.00,2026-03-02,keep
THR-06,Knitted throw,30,32.00,89.00,2026-12-14,clear
ORN-07,Glass ornament set,0,5.50,18.00,2026-10-19,clear
TEA-08,Winter spice tea tin,40,5.00,12.00,2026-06-01,keep
```

### 3. Sales export (Monday 5 October 2026 to Sunday 3 January 2027)

```
sku,sold_in_period,sold_last_4_weeks
HAT-01,210,48
SCF-02,34,6
GLV-03,150,40
CND-04,45,0
MUG-05,120,20
THR-06,6,6
ORN-07,64,9
SOCK-09,18,4
```

### 4. Notes (typed by the merchandiser)

```
- Nothing is on markdown at the moment; every price above is full price.
- No promotions are booked before the reset.
```

## The output

**SLOW-MOVING STOCK AND MARKDOWN PLAN: the Store, stock counted Sunday 3 January 2027**

- **For:** the owner. Prepared Monday 4 January 2027 from: sales export (Monday 5 October 2026 to Sunday 3 January 2027, 8 rows), stock export (8 items), settings, notes.
- **Column check:** all headers matched.
- **Dates:** reset Monday 1 March 2027, 8.1 weeks after the count. First markdown Monday 11 January 2027, 7.0 weeks before the reset, so steps are 2 weeks apart. Stop date Monday 15 February 2027.
- **Settings:** new-item window 30 days; markdown steps 20%, 35%, 50% off the full price; deeper start below 40% projected sell-through; margin floor 10%; stop 14 days before the reset; cover limit for kept lines 26 weeks. Defaults used: first markdown date, deeper-start line, stop gap.
- **Summary:** cash tied up at cost: dead stock \$875.00 (2 items), slow stock \$2,568.00 (2 items), kept lines \$360.00 above the cover limit (1 item). Markdown plans: 3 items, 311 units, \$3,243.00 at cost. On track: 1. Too new to judge: 1. Left out by the data checks: 1. No stock, not listed: 1.

**Data checks**

- SOCK-09 is in the sales export (18 sold in the period, 4 in the last 4 weeks) and not in the stock export. Left out of the plan; see question 1.
- TEA-08 has no row in the sales export. Read as no sales; see question 2.
- ORN-07 has none on hand. Not listed.

**Dead stock**

- **CND-04** Pine candle (clear). First received Monday 19 October 2026 (10 weeks). Sold in the period 45; none in the last 4 weeks. On hand 75. Sell-through 37.5%. Cash at cost: 75 × \$9.00 = \$675.00. Markdown plan below.
- **TEA-08** Winter spice tea tin (keep). First received Monday 1 June 2026 (30 weeks). Sold in the period 0; none in the last 4 weeks; no row in the sales export. On hand 40. Sell-through 0.0%. Cash at cost: 40 × \$5.00 = \$200.00. Kept after the reset: no markdown planned (question 2).

**Slow stock**

- **SCF-02** Cashmere-blend scarf (clear). First received Monday 5 October 2026 (12 weeks). Sold in the period 34; last 4 weeks 6 = 1.50/week. On hand 96. Sell-through 26.2%. Weeks of cover 64.0, against 8.1 weeks to the reset. By the reset at this pace: 12 sold, 84 left, sell-through 35.4%. Cash at cost: 96 × \$18.00 = \$1,728.00. Markdown plan below.
- **HAT-01** Wool beanie (clear). First received Monday 5 October 2026 (12 weeks). Sold in the period 210; last 4 weeks 48 = 12.00/week. On hand 140. Sell-through 60.0%. Weeks of cover 11.7, against 8.1 weeks to the reset. By the reset at this pace: 97 sold, 43 left, sell-through 87.7%. Cash at cost: 140 × \$6.00 = \$840.00. Markdown plan below.

**Kept lines above the cover limit**

- **MUG-05** Stoneware mug (keep). Sold in the period 120; last 4 weeks 20 = 5.00/week. On hand 220. Sell-through 35.3%. Weeks of cover 44.0, above 26. Units within the limit: 130 (5.00 × 26 = 130.00, rounded up); above it: 90 × \$4.00 = \$360.00. Cash at cost in the item: \$880.00. No markdown planned (question 3).

**On track**

- **GLV-03** Touchscreen gloves (clear). Last 4 weeks 40 = 10.00/week. On hand 60. Sell-through 71.4%. Weeks of cover 6.0, against 8.1 weeks to the reset; by the reset at this pace: 60 sold, 0 left.

**Too new to judge**

- **THR-06** Knitted throw (clear). First received Monday 14 December 2026 (20 days before the count). Sold so far 6; on hand 30. Not judged. Can be judged from Wednesday 13 January 2027.

**Markdown plans**

Largest cash at cost first. Prices are the full price less the step's percentage, to the cent. A step after the first is taken only if fewer units than its check figure have sold since the first markdown; otherwise the current price holds, the step and those after it move to the next check, 2 weeks later, with the check figure worked out again for the new date, and none is taken after the stop date. No forecast of extra sales is made.

**SCF-02** Cashmere-blend scarf. Full price \$59.00, unit cost \$18.00: margin \$41.00 a unit (69.5%). Floor price \$20.00 (10% margin). Starts at the second markdown percentage, 35%: projected sell-through 35.4% is below 40%. Pace to clear by the reset: 96 ÷ 7.0 weeks = 13.71 a week, against 1.50 a week now.

- Step 1, Monday 11 January 2027: 35% off, \$38.35. Margin \$20.35 a unit (53.1%); if all 96 sold at this price, \$1,953.60.
- Step 2, Monday 25 January 2027: 50% off, \$29.50. Take it if fewer than 28 have sold since Monday 11 January 2027. Margin \$11.50 a unit (39.0%); if all 96 sold at this price, \$1,104.00.
- No further step: the markdown steps are used up.
- Stop date Monday 15 February 2027: no markdown after it. Prices hold until the reset on Monday 1 March 2027; what is left then is your choice (question 5).
- Owner's decision (approve / change / hold): ______________ Date: ________

**HAT-01** Wool beanie. Full price \$24.00, unit cost \$6.00: margin \$18.00 a unit (75.0%). Floor price \$6.67 (10% margin). Pace to clear by the reset: 140 ÷ 7.0 weeks = 20.00 a week, against 12.00 a week now.

- Step 1, Monday 11 January 2027: 20% off, \$19.20. Margin \$13.20 a unit (68.8%); if all 140 sold at this price, \$1,848.00.
- Step 2, Monday 25 January 2027: 35% off, \$15.60. Take it if fewer than 40 have sold since Monday 11 January 2027. Margin \$9.60 a unit (61.5%); if all 140 sold at this price, \$1,344.00.
- Step 3, Monday 8 February 2027: 50% off, \$12.00. Take it if fewer than 80 have sold since Monday 11 January 2027. Margin \$6.00 a unit (50.0%); if all 140 sold at this price, \$840.00.
- No further step: the markdown steps are used up.
- Stop date Monday 15 February 2027: no markdown after it. Prices hold until the reset on Monday 1 March 2027; what is left then is your choice (question 5).
- Owner's decision (approve / change / hold): ______________ Date: ________

**CND-04** Pine candle. Full price \$16.00, unit cost \$9.00: margin \$7.00 a unit (43.8%). Floor price \$10.00 (10% margin). Starts at the second markdown percentage, 35%: dead stock. Pace to clear by the reset: 75 ÷ 7.0 weeks = 10.71 a week, against 0.00 a week now.

- Step 1, Monday 11 January 2027: 35% off, \$10.40. Margin \$1.40 a unit (13.5%); if all 75 sold at this price, \$105.00.
- Step 2, Monday 25 January 2027: 37.5% off, \$10.00, at the floor. Take it if fewer than 22 have sold since Monday 11 January 2027. Margin \$1.00 a unit (10.0%); if all 75 sold at this price, \$75.00.
- No step after the floor.
- Stop date Monday 15 February 2027: no markdown after it. Prices hold until the reset on Monday 1 March 2027; what is left then is your choice (question 5).
- Owner's decision (approve / change / hold): ______________ Date: ________

**Questions for the owner**

1. SOCK-09 sold 18 in the period and 4 in the last 4 weeks, but has no row in the stock export. Which product is it, how many are on hand, and should it be in the stock export?
2. TEA-08, Winter spice tea tin, stays in the range after the reset. It has no sales in the period and no row in the sales export, with 40 on hand, \$200.00 at cost. Is it on sale? What do you want done with it?
3. MUG-05, Stoneware mug, stays in the range after the reset. It holds 44.0 weeks of cover against a 26-week limit: 90 units, \$360.00 at cost, above the limit, and \$880.00 in the whole item. What do you want done with the extra stock?
4. THR-06, Knitted throw, is to clear by the reset but arrived 20 days before the count: 6 sold so far, 30 on hand. It can be judged from Wednesday 13 January 2027. Do you want it judged then?
5. At the current pace, SCF-02 would have 84 units left at the reset, HAT-01 43 and CND-04 75. After the stop date, Monday 15 February 2027, prices hold until the reset on Monday 1 March 2027. Any units still left then need a decision: hold for next season, return to the supplier where the terms allow it, bundle with a line that sells, sell to a clearance buyer, or donate. Which do you want for each?

Draft for the owner's decision. No price has been changed and nothing has been published or sent. Each price change is made by a person, on its date, after the owner approves it.
