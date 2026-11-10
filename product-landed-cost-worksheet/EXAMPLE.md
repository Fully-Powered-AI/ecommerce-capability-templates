# Product landed cost worksheet: an invented example

*Illustrative example with invented data.* The store, the suppliers, the products, the invoices, the reference numbers, the amounts and every date below are invented. The store is an invented online kitchenware shop, called the Store here, that imports four products from one factory, Supplier A. The shipment came by sea through Forwarder B, cleared customs through Broker C, was insured by Insurer D and was received at Warehouse E. People are referred to by role: the owner approves costs, and the bookkeeper enters them.

The inputs come first, in full, so the template can be run on them. The worksheet follows.

## The inputs

### 1. Settings (typed by the bookkeeper)

```
Shipment: Supplier A order SA-0457, received Tuesday 3 November 2026
Today: Monday 9 November 2026
Approves costs: the owner
Updates costs in the store and the books: the bookkeeper
Books currency: US dollars. Every invoice for this shipment is in US dollars.
Allocation: freight by weight; insurance by value; duty and customs fees,
  amounts the entry shows against a product to that product, totals by
  value; brokerage by value; inbound fees by quantity
Taxes the books reclaim: none on this shipment
Costing method in the store: weighted average
Margin floor: 66%
```

### 2. Supplier invoice lines (Supplier A, invoice A-3318)

```
sku,product,units,unit_price,unit_weight_kg
MUG-01,Stoneware mug,600,2.10,0.45
BOWL-02,Ceramic bowl set of four,200,7.50,1.80
KNIFE-03,Chef's knife 20 cm,150,9.00,0.40
BOARD-04,Bamboo chopping board,300,3.30,1.10
```

### 3. Receiving record (Warehouse E, Tuesday 3 November 2026)

```
sku,units_received
MUG-01,600
BOWL-02,200
KNIFE-03,150
BOARD-04,300
```

### 4. Store cost export (taken Monday 2 November 2026, before the shipment was received)

```
sku,product,recorded_cost,price,on_hand_before
MUG-01,Stoneware mug,3.10,12.00,80
BOWL-02,Ceramic bowl set of four,9.80,32.00,25
KNIFE-03,Chef's knife 20 cm,,39.00,0
BOARD-04,Bamboo chopping board,4.40,18.00,60
```

### 5. Charge invoices and the customs entry

```
Forwarder B. Invoice FB-2291, Wednesday 4 November 2026. Shipment SA-0457.
  Ocean freight                                         980.00
  Delivery from the port to the Store's warehouse       220.00
  Terminal handling at the port                          95.00
  Total due, USD                                      1,295.00

Insurer D. Invoice ID-5530, Friday 23 October 2026. Shipment SA-0457.
  Cargo insurance                                        61.20
  Total due, USD                                         61.20

Broker C. Customs entry E-118204, Monday 2 November 2026. Shipment SA-0457.
  Line 1  MUG-01    entered value 1,260.00   duty 100.80
  Line 2  BOWL-02   entered value 1,500.00   duty 210.00
  Line 3  KNIFE-03  entered value 1,350.00   duty  47.25
  Line 4  BOARD-04  entered value   990.00   duty   0.00
  Customs processing fee                             32.00
  Total duty and fees, USD                          390.05

Broker C. Invoice BC-7714, Thursday 5 November 2026. Entry E-118204.
  Duty paid on your behalf, per entry E-118204          358.05
  Customs processing fee paid on your behalf             32.00
  Customs brokerage fee                                 165.00
  Total due, USD                                        555.05

Warehouse E. Invoice WE-0912, Thursday 5 November 2026. Shipment SA-0457.
  Receiving and put-away, 1,250 units                   120.00
  Total due, USD                                        120.00
```

### 6. Notes (typed by the bookkeeper)

```
- The owner asks why the bamboo boards show no duty. Please put it to
  the broker.
```

## The output

**PRODUCT LANDED COST WORKSHEET: Supplier A order SA-0457, received Tuesday 3 November 2026**

- **For:** the owner. Prepared Monday 9 November 2026 from: supplier invoice lines (4 products), receiving record (4 rows), store cost export (4 products), charge invoices (FB-2291, ID-5530, BC-7714, WE-0912), customs entry E-118204, settings, notes.
- **Version 1.**
- **Column check:** all headers matched.
- **Settings:** books currency US dollars; exchange rates none needed. Allocation: freight by weight; insurance by value; duty and customs fees, entry lines direct, totals by value; brokerage by value; inbound fees by quantity. Taxes reclaimed and left out: none named. Costing method: weighted average. Cost change flag: 5%. Margin floor: 66%. Defaults used: cost change flag.
- **Summary:** goods \$5,100.00 + charges \$2,031.25 = \$7,131.25 landed, for 1,250 units of 4 products. Charges add 39.8% to the goods value. Above recorded by more than 5%: 2. Below recorded by more than 5%: 0. Store shows no cost: 1. Below the margin floor: 1.

**Checks**

- Units received equal units invoiced for all 4 products.
- The value entry E-118204 shows for each product matches Supplier A's invoice line.
- BC-7714 passes on duty of \$358.05 and a customs processing fee of \$32.00. Both agree with entry E-118204 and are counted once, from the entry.
- KNIFE-03 has no recorded cost in the store cost export; see question 1.

**Charges register**

- FB-2291, Forwarder B, Wednesday 4 November 2026: Ocean freight \$980.00 -> freight.
- FB-2291, Forwarder B, Wednesday 4 November 2026: Delivery from the port to the Store's warehouse \$220.00 -> freight.
- FB-2291, Forwarder B, Wednesday 4 November 2026: Terminal handling at the port \$95.00 -> inbound fees.
- ID-5530, Insurer D, Friday 23 October 2026: Cargo insurance \$61.20 -> insurance.
- E-118204, Broker C, Monday 2 November 2026: Duty, line 1 \$100.80 -> duty and customs fees, against MUG-01 on the entry.
- E-118204, Broker C, Monday 2 November 2026: Duty, line 2 \$210.00 -> duty and customs fees, against BOWL-02 on the entry.
- E-118204, Broker C, Monday 2 November 2026: Duty, line 3 \$47.25 -> duty and customs fees, against KNIFE-03 on the entry.
- E-118204, Broker C, Monday 2 November 2026: Duty, line 4 \$0.00 -> duty and customs fees, against BOARD-04 on the entry.
- E-118204, Broker C, Monday 2 November 2026: Customs processing fee \$32.00 -> duty and customs fees.
- BC-7714, Broker C, Thursday 5 November 2026: Customs brokerage fee \$165.00 -> brokerage.
- WE-0912, Warehouse E, Thursday 5 November 2026: Receiving and put-away, 1,250 units \$120.00 -> inbound fees.
- Not counted: BC-7714, Duty paid on your behalf \$358.05, counted once, from entry E-118204.
- Not counted: BC-7714, Customs processing fee paid on your behalf \$32.00, counted once, from entry E-118204.
- Totals: freight \$1,200.00; insurance \$61.20; duty and customs fees \$390.05; brokerage \$165.00; inbound fees \$215.00. All charges \$2,031.25.

**Allocation**

- Freight \$1,200.00 by weight (total basis 1,020 kg): MUG-01 270 kg = \$317.65; BOWL-02 360 kg = \$423.52; KNIFE-03 60 kg = \$70.59; BOARD-04 330 kg = \$388.24. Rounding: −\$0.01 placed on BOWL-02, the largest basis.
- Insurance \$61.20 by value (total basis \$5,100.00): MUG-01 \$1,260.00 = \$15.12; BOWL-02 \$1,500.00 = \$18.00; KNIFE-03 \$1,350.00 = \$16.20; BOARD-04 \$990.00 = \$11.88.
- Duty and customs fees: from the entry, MUG-01 \$100.80; BOWL-02 \$210.00; KNIFE-03 \$47.25; BOARD-04 \$0.00. Total-only amounts \$32.00 by value: MUG-01 \$1,260.00 = \$7.91; BOWL-02 \$1,500.00 = \$9.41; KNIFE-03 \$1,350.00 = \$8.47; BOARD-04 \$990.00 = \$6.21.
- Brokerage \$165.00 by value (total basis \$5,100.00): MUG-01 \$1,260.00 = \$40.76; BOWL-02 \$1,500.00 = \$48.53; KNIFE-03 \$1,350.00 = \$43.68; BOARD-04 \$990.00 = \$32.03.
- Inbound fees \$215.00 by quantity (total basis 1,250 units): MUG-01 600 = \$103.20; BOWL-02 200 = \$34.40; KNIFE-03 150 = \$25.80; BOARD-04 300 = \$51.60.

**Landed unit cost**

- **MUG-01** Stoneware mug. Goods 600 x \$2.10 = \$1,260.00. Charges: freight \$317.65, insurance \$15.12, duty and customs fees \$108.71, brokerage \$40.76, inbound fees \$103.20 = \$585.44. Landed (\$1,260.00 + \$585.44) / 600 = \$3.08 per unit, of which charges \$0.98.
- **BOWL-02** Ceramic bowl set of four. Goods 200 x \$7.50 = \$1,500.00. Charges: freight \$423.52, insurance \$18.00, duty and customs fees \$219.41, brokerage \$48.53, inbound fees \$34.40 = \$743.86. Landed (\$1,500.00 + \$743.86) / 200 = \$11.22 per unit, of which charges \$3.72.
- **KNIFE-03** Chef's knife 20 cm. Goods 150 x \$9.00 = \$1,350.00. Charges: freight \$70.59, insurance \$16.20, duty and customs fees \$55.72, brokerage \$43.68, inbound fees \$25.80 = \$211.99. Landed (\$1,350.00 + \$211.99) / 150 = \$10.41 per unit, of which charges \$1.41.
- **BOARD-04** Bamboo chopping board. Goods 300 x \$3.30 = \$990.00. Charges: freight \$388.24, insurance \$11.88, duty and customs fees \$6.21, brokerage \$32.03, inbound fees \$51.60 = \$489.96. Landed (\$990.00 + \$489.96) / 300 = \$4.93 per unit, of which charges \$1.63.
- Rounding check: landed unit costs x units received = \$7,132.50, \$1.25 above the shipment total of \$7,131.25.

**Against the recorded cost**

- **KNIFE-03** Chef's knife 20 cm. Store shows no cost. Landed \$10.41. Difference: none worked out, as the store shows no cost. Cost to enter (weighted average): \$10.41 (nothing on hand before, so the landed unit cost). Margin at \$39.00: no recorded cost; 73.3% at the cost to enter.
- **BOWL-02** Ceramic bowl set of four. Recorded \$9.80. Landed \$11.22. Difference \$1.42 (14.5%): above recorded by more than 5%. Cost to enter (weighted average): \$11.06 ((25 x \$9.80 + 200 x \$11.22) / 225 = \$2,489.00 / 225). Margin at \$32.00: 69.4% at the recorded cost; 65.4% at the cost to enter, below the 66% floor (question 2).
- **BOARD-04** Bamboo chopping board. Recorded \$4.40. Landed \$4.93. Difference \$0.53 (12.0%): above recorded by more than 5%. Cost to enter (weighted average): \$4.84 ((60 x \$4.40 + 300 x \$4.93) / 360 = \$1,743.00 / 360). Margin at \$18.00: 75.6% at the recorded cost; 73.1% at the cost to enter.
- **MUG-01** Stoneware mug. Recorded \$3.10. Landed \$3.08. Difference −\$0.02 (−0.6%): within 5%. Cost to enter (weighted average): \$3.08 ((80 x \$3.10 + 600 x \$3.08) / 680 = \$2,096.00 / 680). Margin at \$12.00: 74.2% at the recorded cost; 74.3% at the cost to enter.

**Questions for the broker**

1. The owner asks why the bamboo chopping boards show no duty. Entry E-118204, line 4, shows BOARD-04 with an entered value of \$990.00 and duty of \$0.00, and the worksheet uses \$0.00. Recorded as entered; not answered here.

**Questions for the owner**

1. KNIFE-03 Chef's knife 20 cm has no cost in the store, so until one is entered the store's margin reports treat it as costing nothing. Nothing was on hand before this shipment, so its cost to enter is its landed unit cost, \$10.41. Do you approve \$10.41 as its cost?
2. BOWL-02 Ceramic bowl set of four sells at \$32.00. Its margin is 69.4% at the recorded cost of \$9.80 and 65.4% at the cost to enter of \$11.06, below your 66% floor. Its landed unit cost is \$11.22, of which charges are \$3.72. What do you want done?

**Draft cost updates**

DRAFT, NOT ENTERED. For the bookkeeper, once the owner approves.

- KNIFE-03 Chef's knife 20 cm: recorded none -> \$10.41 (weighted average).
- BOWL-02 Ceramic bowl set of four: recorded \$9.80 -> \$11.06 (weighted average).
- BOARD-04 Bamboo chopping board: recorded \$4.40 -> \$4.84 (weighted average).
- MUG-01 Stoneware mug: recorded \$3.10 -> \$3.08 (weighted average).
- For the books: shipment SA-0457, inventory value \$7,131.25 = goods \$5,100.00 + freight \$1,200.00 + insurance \$61.20 + duty and customs fees \$390.05 + brokerage \$165.00 + inbound fees \$215.00.
- Approved to enter: ______________ Date: ________

Draft for the owner's decision. No cost has been changed in the store or the books, no invoice has been paid, and no customs question has been answered.
