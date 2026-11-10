# Stock count reconciliation: an invented example

*Illustrative example with invented data.* The business, the suppliers, the items, the quantities, the values and every date below are invented. The business is an invented online homewares shop with one warehouse, called the Store here, buying from suppliers named Supplier A and Supplier B. Its warehouse lead counted every stock item after closing on the last Saturday of October, and its bookkeeper exported the books' figures for the same date. People are referred to by role.

The inputs come first, in full, so the template can be run on them. The reconciliation follows.

## The inputs

### 1. Settings (typed by the bookkeeper)

```
Business: the Store
Count date: Saturday 31 October 2026
When counted: after the warehouse closed; nothing moved after the count
Count basis: full count. Every stock item in the warehouse was looked for.
Locations counted: Warehouse
Book stock report covers: Warehouse (the only stock location)
Books' unit: each
Conversions: CND-02 counted in cartons; 1 carton = 12 each
Currency: US dollars
Bookkeeper: the bookkeeper
Warehouse or store lead: the warehouse lead
Approver: the owner
Today: Monday 2 November 2026
```

### 2. Count sheet

```
item_code,description,location,counted_qty,count_unit
MUG-01,Stoneware mug,Warehouse,118,each
MUG-02,Enamel mug,Warehouse,64,each
CND-01,Soy candle large,Warehouse,30,each
CND-02,Tealight box,Warehouse,9,carton
THR-01,Wool throw grey,Warehouse,14,each
THR-02,Wool throw blue,Warehouse,6,each
VAS-01,Glass vase,Warehouse,0,each
TRY-01,Oak serving tray,Warehouse,3,each
LMP-01,Table lamp,Warehouse,4,each
```

### 3. Book stock report as of 31 October 2026

```
item_code,description,book_qty,book_value
MUG-01,Stoneware mug,120,540.00
MUG-02,Enamel mug,64,352.00
CND-01,Soy candle large,42,378.00
CND-02,Tealight box,96,192.00
THR-01,Wool throw grey,10,320.00
THR-02,Wool throw blue,10,320.00
VAS-01,Glass vase,0,45.00
BSK-01,Seagrass basket,15,180.00
```

### 4. Stock item list

```
item_code,description,active
BSK-01,Seagrass basket,yes
CND-01,Soy candle large,yes
CND-02,Tealight box,yes
MUG-01,Stoneware mug,yes
MUG-02,Enamel mug,yes
THR-01,Wool throw grey,yes
THR-02,Wool throw blue,yes
TRY-01,Oak serving tray,yes
VAS-01,Glass vase,yes
```

### 5. Movement notes (typed by the warehouse lead)

```
Receiving log, 26 to 31 October:
- 28 Oct, Supplier A, MUG-01, 24 each. Entered in the books.
- 30 Oct, Supplier B, CND-02, 1 carton (12 each). Supplier B's
  bill has not arrived; not entered.
Returns log:
- 29 Oct, TRY-01, 3 each, customer returns, checked and back on the
  shelf. Refunds issued; the return to stock is not entered.
Damage log:
- 27 Oct, CND-01, 5 each, cracked jars, put in the disposal bin and not
  counted. Not written off.
```

## The output

**STOCK COUNT RECONCILIATION: the Store, counted Saturday 31 October 2026**

- **For:** the bookkeeper and the warehouse lead. Prepared Monday 2 November 2026 from: count sheet (9 rows, Warehouse), book stock report as of 31 October 2026 (8 items), stock item list (9 items), settings, movement notes.
- **Column check:** all headers matched.
- **Basis:** full count: an item not on the sheet counts as 0. Scope: Warehouse against books covering Warehouse. Timing: counted after the day's last movement. Units: converted: CND-02 carton = 12 each. Currency: US dollars.
- **Settings:** recount at \$100.00 or 10% of the book quantity; size check more than 10 times the book quantity and at least 50 units above it; approver the owner. Defaults used: recount value, recount share, size check.
- **Summary:** 9 items compared. Agrees 1. Short 4, −\$425.00. Over 3, +\$152.00. Query 1. Counted, not in the books 1. In the books, not counted 0. Inactive at zero, left out 0. Net difference −\$273.00, an estimate at average cost; left out of it: 1 Query, 1 other compared item with no cost basis. Recounts 5. Actions for the approver 4.

**Count and book checks**

- TRY-01 Oak serving tray is on the stock item list but not in the book stock report. Read as 0 units and \$0.00; see question 3.
- LMP-01 Table lamp is on the count sheet but not on the stock item list. Listed under Counted, not in the books; see question 2.

**Item by item**

- **BSK-01** Seagrass basket. Counted 0 (not on the sheet); books 15, \$180.00. Difference −15 × \$12.00 = −\$180.00. Short.
- **CND-01** Soy candle large. Counted 30; books 42, \$378.00. Difference −12 × \$9.00 = −\$108.00. Short.
- **CND-02** Tealight box. Counted 108 (9 cartons × 12); books 96, \$192.00. Difference +12 × \$2.00 = +\$24.00. Over.
- **MUG-01** Stoneware mug. Counted 118; books 120, \$540.00. Difference −2 × \$4.50 = −\$9.00. Short.
- **MUG-02** Enamel mug. Counted 64; books 64, \$352.00. Difference 0 × \$5.50 = \$0.00. Agrees.
- **THR-01** Wool throw grey. Counted 14; books 10, \$320.00. Difference +4 × \$32.00 = +\$128.00. Over.
- **THR-02** Wool throw blue. Counted 6; books 10, \$320.00. Difference −4 × \$32.00 = −\$128.00. Short.
- **TRY-01** Oak serving tray. Counted 3; books 0, \$0.00. Difference +3; value: no cost basis. Over.
- **VAS-01** Glass vase. Counted 0; books 0, \$45.00. Difference 0; value: no cost basis. Query: \$45.00 in the books with no units behind it.

**What to check**

- **BSK-01**, Short 15, −\$180.00. Not on the sheet: check the shelf was looked at before reading this as a loss. Check: a sale shipped but not entered by 31 October; stock damaged, used or given away and not written off; a delivery entered in full that arrived short; counted under another code or in another unit; and only then unexplained loss.
- **CND-01**, Short 12, −\$108.00. Seen in the notes: damage log, 27 October, cracked jars in the disposal bin, not written off, 5 units; unexplained −7, −\$63.00. Check: a sale shipped but not entered by 31 October; stock damaged, used or given away and not written off; a delivery entered in full that arrived short; counted under another code or in another unit; and only then unexplained loss.
- **CND-02**, Over 12, +\$24.00. Seen in the notes: receiving log, 30 October, Supplier B, 1 carton of 12 not entered, 12 units; unexplained 0, \$0.00.
- **MUG-01**, Short 2, −\$9.00. Check: a sale shipped but not entered by 31 October; stock damaged, used or given away and not written off; a delivery entered in full that arrived short; counted under another code or in another unit; and only then unexplained loss.
- **THR-01**, Over 4, +\$128.00. Possible mix-up with THR-02: equal and opposite. Check: a delivery received but not entered; a customer return back on the shelf but not entered; a sale entered but still on the shelf; counted under another code or in another unit.
- **THR-02**, Short 4, −\$128.00. Possible mix-up with THR-01: equal and opposite. Check: a sale shipped but not entered by 31 October; stock damaged, used or given away and not written off; a delivery entered in full that arrived short; counted under another code or in another unit; and only then unexplained loss.
- **TRY-01**, Over 3, no cost basis. Seen in the notes: returns log, 29 October, customer returns back on the shelf, return to stock not entered, 3 units; unexplained 0, no value.

**Query**

- **VAS-01:** the books show \$45.00 for 0 units, and none were counted. See question 1.

**Counted, not in the books**

- **LMP-01** Table lamp, Warehouse: 4 counted. See question 2.

**In the books, not counted**

None.

**Recount before anything is adjusted**

1. **BSK-01** Seagrass basket, Warehouse: counted 0, books 15, unexplained −15, −\$180.00. Why: not on the sheet of a full count, and above the recount levels. How: a different counter; count in each.
2. **THR-01** Wool throw grey, Warehouse: counted 14, books 10, unexplained +4, +\$128.00. Why: possible mix-up with THR-02, and above the recount levels. How: a different counter; count in each; count both at the same time.
3. **THR-02** Wool throw blue, Warehouse: counted 6, books 10, unexplained −4, −\$128.00. Why: possible mix-up with THR-01, and above the recount levels. How: a different counter; count in each; count both at the same time.
4. **CND-01** Soy candle large, Warehouse: counted 30, books 42, unexplained −7, −\$63.00. Why: 7 of 42 is 16.7% of the book quantity, above 10%. How: a different counter; count in each; leave out the 5 set aside.
5. **LMP-01** Table lamp, Warehouse: counted 4, not in the books, unexplained +4, no value. Why: counted but not in the books. How: a different counter; count in each; check the code on the label against the item list.

**Actions for the approver**

- **CND-01:** write off −5 units, −\$45.00. Cause: damage log, 27 October, cracked jars. Approved: ______________ Date: ________
- **CND-02:** enter the receipt +12 units, +\$24.00. Cause: receiving log, 30 October, Supplier B, not entered. Bill not yet received; its value may differ. Approved: ______________ Date: ________
- **MUG-01:** adjust −2 units, −\$9.00. Cause: not found. Approved: ______________ Date: ________
- **TRY-01:** enter the return +3 units, value set by the books when entered. Cause: returns log, 29 October. Approved: ______________ Date: ________

**Questions for the bookkeeper**

1. VAS-01 Glass vase: the books show \$45.00 against 0 units, and none were counted. What does the \$45.00 represent?
2. LMP-01 Table lamp: 4 were counted in the Warehouse, and no stock item has this code. Is it a new item still to be set up in the books, or stock counted under the wrong code?
3. TRY-01 Oak serving tray: it is on the stock item list but not in the book stock report, so it was read as 0 units and \$0.00. Was the report exported in full?

Draft for the owner's decision. Nothing has been adjusted, posted or changed in the books or the stock system. Values are estimates at the books' average cost as of 31 October 2026; the books' own cost method may differ.
