# Product landed cost worksheet: two runs on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Opus 5.5 (model ID `claude-opus-5-5`)
- **Date:** 2026-11-10

The template was run twice on 10 November 2026 on its invented example, and no client data was used in either run. The first run, by a model that did not write the template, came before two editorial reviews; small clarifications were made to the procedure and the pasted instructions after each review. The run recorded in full here is the second, made on the instructions as they now stand. A short account of the first run, and of what was changed after it, follows.

**A limit on this record.** The second run was not blind. It was made by the same model session that applied the second review's points, after reading the template, the example's output and the first run's record. It shows what the revised instructions give when followed step by step; it is not an independent second reading of them, and its agreement with the example shows less than the first run's agreement did.

## The second run

The inputs are the invented example in [`example.md`](example.md): the invented kitchenware store, Supplier A order SA-0457, and everything under "The inputs" there (settings, supplier invoice lines, receiving record, store cost export, the four charge invoices and the customs entry, and the note about the bamboo boards). The run followed the instruction block and the output format in `member/template.md`. The arithmetic was checked with a short script working from the inputs.

### What came out

The run reached a full worksheet. No stop condition was triggered. The output is given below in full, as the output format lays it out.

```text
PRODUCT LANDED COST WORKSHEET: Supplier A order SA-0457, received Tuesday 3 November 2026

For: the owner. Prepared Monday 9 November 2026 from: supplier invoice lines (4 products), receiving record (4 rows), store cost export (4 products), charge invoices (FB-2291, ID-5530, BC-7714, WE-0912), customs entry E-118204, settings, notes.
Version 1.
Column check: all headers matched.
Settings: books currency US dollars; exchange rates none needed. Allocation: freight by weight; insurance by value; duty and customs fees, entry lines direct, totals by value; brokerage by value; inbound fees by quantity. Taxes reclaimed and left out: none named. Costing method: weighted average. Cost change flag: 5%. Margin floor: 66%. Defaults used: cost change flag.
Summary: goods $5,100.00 + charges $2,031.25 = $7,131.25 landed, for 1,250 units of 4 products. Charges add 39.8% to the goods value. Above recorded by more than 5%: 2. Below recorded by more than 5%: 0. Store shows no cost: 1. Below the margin floor: 1.

Checks
Units received equal units invoiced for all 4 products; no sku appears twice in any export.
The lines of FB-2291, ID-5530, BC-7714, WE-0912 and entry E-118204 add up to their totals; the total lines are not registered.
The value entry E-118204 shows for each product matches Supplier A's invoice line.
BC-7714 passes on duty of $358.05 and a customs processing fee of $32.00. Both agree with entry E-118204 and are counted once, from the entry.
KNIFE-03 has no recorded cost in the store cost export; see question 1.

Charges register
FB-2291, Forwarder B, Wednesday 4 November 2026: Ocean freight $980.00 -> freight.
FB-2291, Forwarder B, Wednesday 4 November 2026: Delivery from the port to the Store's warehouse $220.00 -> freight.
FB-2291, Forwarder B, Wednesday 4 November 2026: Terminal handling at the port $95.00 -> inbound fees.
ID-5530, Insurer D, Friday 23 October 2026: Cargo insurance $61.20 -> insurance.
E-118204, Broker C, Monday 2 November 2026: Line 1 duty $100.80 -> duty and customs fees, against MUG-01 on the entry.
E-118204, Broker C, Monday 2 November 2026: Line 2 duty $210.00 -> duty and customs fees, against BOWL-02 on the entry.
E-118204, Broker C, Monday 2 November 2026: Line 3 duty $47.25 -> duty and customs fees, against KNIFE-03 on the entry.
E-118204, Broker C, Monday 2 November 2026: Line 4 duty $0.00 -> duty and customs fees, against BOARD-04 on the entry.
E-118204, Broker C, Monday 2 November 2026: Customs processing fee $32.00 -> duty and customs fees.
BC-7714, Broker C, Thursday 5 November 2026: Customs brokerage fee $165.00 -> brokerage.
WE-0912, Warehouse E, Thursday 5 November 2026: Receiving and put-away, 1,250 units $120.00 -> inbound fees.
Not counted: BC-7714, Duty paid on your behalf, per entry E-118204 $358.05, counted once, from entry E-118204.
Not counted: BC-7714, Customs processing fee paid on your behalf $32.00, counted once, from entry E-118204.
Totals: freight $1,200.00; insurance $61.20; duty and customs fees $390.05; brokerage $165.00; inbound fees $215.00. All charges $2,031.25.

Allocation
Freight $1,200.00 by weight (total basis 1,020 kg): MUG-01 270 kg = $317.65; BOWL-02 360 kg = $423.52; KNIFE-03 60 kg = $70.59; BOARD-04 330 kg = $388.24. Rounding: -$0.01 placed on BOWL-02, the largest basis.
Insurance $61.20 by value (total basis $5,100.00): MUG-01 $1,260.00 = $15.12; BOWL-02 $1,500.00 = $18.00; KNIFE-03 $1,350.00 = $16.20; BOARD-04 $990.00 = $11.88.
Duty and customs fees: from the entry, MUG-01 $100.80; BOWL-02 $210.00; KNIFE-03 $47.25; BOARD-04 $0.00. Total-only amounts $32.00 by value: MUG-01 $1,260.00 = $7.91; BOWL-02 $1,500.00 = $9.41; KNIFE-03 $1,350.00 = $8.47; BOARD-04 $990.00 = $6.21.
Brokerage $165.00 by value (total basis $5,100.00): MUG-01 $1,260.00 = $40.76; BOWL-02 $1,500.00 = $48.53; KNIFE-03 $1,350.00 = $43.68; BOARD-04 $990.00 = $32.03.
Inbound fees $215.00 by quantity (total basis 1,250 units): MUG-01 600 = $103.20; BOWL-02 200 = $34.40; KNIFE-03 150 = $25.80; BOARD-04 300 = $51.60.

Landed unit cost
MUG-01 Stoneware mug. Goods 600 x $2.10 = $1,260.00. Charges: freight $317.65, insurance $15.12, duty and customs fees $108.71, brokerage $40.76, inbound fees $103.20 = $585.44. Landed ($1,260.00 + $585.44) / 600 = $3.08 per unit, of which charges $0.98.
BOWL-02 Ceramic bowl set of four. Goods 200 x $7.50 = $1,500.00. Charges: freight $423.52, insurance $18.00, duty and customs fees $219.41, brokerage $48.53, inbound fees $34.40 = $743.86. Landed ($1,500.00 + $743.86) / 200 = $11.22 per unit, of which charges $3.72.
KNIFE-03 Chef's knife 20 cm. Goods 150 x $9.00 = $1,350.00. Charges: freight $70.59, insurance $16.20, duty and customs fees $55.72, brokerage $43.68, inbound fees $25.80 = $211.99. Landed ($1,350.00 + $211.99) / 150 = $10.41 per unit, of which charges $1.41.
BOARD-04 Bamboo chopping board. Goods 300 x $3.30 = $990.00. Charges: freight $388.24, insurance $11.88, duty and customs fees $6.21, brokerage $32.03, inbound fees $51.60 = $489.96. Landed ($990.00 + $489.96) / 300 = $4.93 per unit, of which charges $1.63.
Rounding check: landed unit costs x units received = $7,132.50, $1.25 above the shipment total of $7,131.25.

Against the recorded cost
KNIFE-03 Chef's knife 20 cm. Store shows no cost. Landed $10.41. Difference: none worked out, as the store shows no cost.
Cost to enter (weighted average): $10.41 (nothing on hand before, so the landed unit cost).
Margin at $39.00: no recorded cost; 73.3% at the cost to enter.
BOWL-02 Ceramic bowl set of four. Recorded $9.80. Landed $11.22. Difference $1.42 (14.5%): above recorded by more than 5%.
Cost to enter (weighted average): $11.06 ((25 x $9.80 + 200 x $11.22) / 225 = $2,489.00 / 225).
Margin at $32.00: 69.4% at the recorded cost; 65.4% at the cost to enter, below the 66% floor (question 2).
BOARD-04 Bamboo chopping board. Recorded $4.40. Landed $4.93. Difference $0.53 (12.0%): above recorded by more than 5%.
Cost to enter (weighted average): $4.84 ((60 x $4.40 + 300 x $4.93) / 360 = $1,743.00 / 360).
Margin at $18.00: 75.6% at the recorded cost; 73.1% at the cost to enter.
MUG-01 Stoneware mug. Recorded $3.10. Landed $3.08. Difference -$0.02 (-0.6%): within 5%.
Cost to enter (weighted average): $3.08 ((80 x $3.10 + 600 x $3.08) / 680 = $2,096.00 / 680).
Margin at $12.00: 74.2% at the recorded cost; 74.3% at the cost to enter.

Questions for the broker
1. The owner asks why the bamboo chopping boards show no duty. Entry E-118204, line 4, shows BOARD-04 Bamboo chopping board with an entered value of $990.00 and duty of $0.00, and the worksheet uses $0.00. Recorded as entered; not answered here.

Questions for the owner
1. KNIFE-03 Chef's knife 20 cm has no cost in the store, so until one is entered the store's margin reports treat it as costing nothing. Nothing was on hand before this shipment, so its cost to enter is its landed unit cost, $10.41. Do you approve $10.41 as its cost?
2. BOWL-02 Ceramic bowl set of four sells at $32.00. Its margin is 69.4% at the recorded cost of $9.80 and 65.4% at the cost to enter of $11.06, below your 66% floor. Its landed unit cost is $11.22, of which charges are $3.72. What do you want done?

Draft cost updates
DRAFT, NOT ENTERED. For the bookkeeper, once the owner approves.
KNIFE-03 Chef's knife 20 cm: recorded none -> $10.41 (weighted average).
BOWL-02 Ceramic bowl set of four: recorded $9.80 -> $11.06 (weighted average).
BOARD-04 Bamboo chopping board: recorded $4.40 -> $4.84 (weighted average).
MUG-01 Stoneware mug: recorded $3.10 -> $3.08 (weighted average).
For the books: shipment SA-0457, inventory value $7,131.25 = goods $5,100.00 + freight $1,200.00 + insurance $61.20 + duty and customs fees $390.05 + brokerage $165.00 + inbound fees $215.00.
Approved to enter: ______________ Date: ________

Draft for the owner's decision. No cost has been changed in the store or the books, no invoice has been paid, and no customs question has been answered.
```

### What was observed

- **Every part of the output format was produced,** in order, and every figure traces to an input by the arithmetic written out beside it. The questions and the sorting followed the instructions.
- **Against the published example, every figure matches:** every allocation, landed unit cost, difference, cost to enter and margin, the \$1.25 rounding check and the line for the books. The first run's figures were the same.
- **Differences from the example were in wording only.** The run added a line under Checks saying that each invoice's and the entry's lines add up to their totals, which the instructions ask it to check and the example does not record; it noted under Checks that no sku appears twice; and it names the entry's duty lines by line number.
- **No fact appeared in the output that is not in the inputs.**
- **Nothing triggered a stop,** so none of the stop conditions was exercised by this run either.
- **The clarifications made after the first run were used as written.** Delivery from the port was typed as freight, from the freight definition that the pasted instructions now carry ("with any fuel or delivery charge"); terminal handling was typed as an inbound fee from the inbound fees definition; the processing fee was spread by the duty method as a total-only amount; total lines were used only to check the sums and were not registered; the differences were worked from the rounded landed unit costs.
- **Where the instructions still left room, and the run had to choose:**
  - The order of products under "Landed unit cost" and "Draft cost updates" is not stated. The run used the supplier invoice's order for the first and the order of "Against the recorded cost" for the second, as the example does.
  - The date format of a register line is not stated; the run wrote the weekday and date, as in the header.
  - Whether Checks records a check that passed is not stated. The run recorded the ones the instructions name.
  - The settings supply a "Today" of 9 November, while the run was made on 10 November. The run used the typed date, as the template names "today's date" as a setting.
- **One limit of this trial:** it is a second run on the same input set, with no problems in it, by a model that had seen the example. It shows the revised template can be followed to the published example. It does not show how the stops, the refusals or the late-invoice path behave. Of the template's fifteen acceptance tests, the first (the example) has been run twice and the other fourteen have not been run.

## The first run, and what was changed after it

The first run was made the same day by Claude Sonnet 5.5 (model ID `claude-sonnet-5-5`), also in Claude Code, on the template before the reviews' points were applied. That model did not write the template. It followed the instruction block and the output format, worked the arithmetic before looking at the example's output, and only then compared the two; the arithmetic was checked with a short script. Its record gave a condensed rendering of the worksheet, with some register lines grouped and the questions shortened, rather than the full output format.

It reached a full worksheet, triggered no stop, and matched every figure in the example. Its differences were in wording and layout: it grouped some register lines, and it listed the entry's and invoices' "Total" lines as not counted, which the example does not mention. It recorded these places where it had to choose:

- Terminal handling at the port was typed as an inbound fee, not freight, from the definition of the types; the example agrees. A reader could reasonably call it freight.
- The template did not say what to do with the "Total" lines on the entry and invoices. It left them out of the register as sums. A literal reader might count them.
- The customs processing fee appears on the entry as a single amount. It treated it as a total-only amount spread by the duty method (value). The wording supported this but did not name this case.
- "From the largest percentage difference, either way, to the smallest" does not say whether the sign matters. It sorted by size regardless of sign.
- The percentage of charges over goods had no stated precision; it used one decimal.
- The differences were worked from the rounded landed unit cost, which the template implied but did not say.
- It used the typed "Today" of 9 November rather than the real run date.

It also noted that the template's version notes still said the template had not been tried, and that only one input set with no problems in it had been run.

After the first run, an independent review failed the template on that stale line, which was corrected, and raised minor points. These edits were then made, by Opus 5.5:

1. The procedure and the pasted instructions say that the total lines of the invoices and the entry are sums: they are used only to check that the lines add up and are not registered, and the work stops and asks if the lines do not add up. A fifteenth acceptance test covers that stop, and the reviewer checklist's register item excepts total lines.
2. They name the case of a duty or customs amount the entry shows as a single figure, not against any product, such as the processing fee: it is a total-only amount, spread by the method set for duty and customs fees.
3. The weighted-average exception and the margin at the recorded cost say "blank or zero", matching how a recorded cost of 0 is already treated.
4. The charges-to-goods percentage in the Summary is stated to one decimal place, and the difference from the recorded cost is stated to be worked from the rounded landed unit cost.
5. The pasted instructions quote the output format's closing line word for word, and name a login code beside a password among the details never repeated.
6. The public page says that every charge ties back to the invoices to the cent, since the unit costs times units sit \$1.25 above the shipment total by rounding.

A second review passed the template and raised minor points, which were applied before the second run:

7. The pasted instructions now stop on a duplicate sku in any export, or on the same invoice number supplied twice with different amounts, as the procedure does.
8. The pasted instructions now carry the one-line definitions of all five charge types, including freight to the business's door with any delivery charge, so a product given only the pasted block need not guess where port delivery and terminal handling go.
9. The acceptance tests were adjusted: the first now names the duty counted once from the entry, and the fourth, which repeated it, now covers a reclaimed import tax left out of cost.

The output format and the example's inputs did not change at any point.
