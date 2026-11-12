---
name: "product-landed-cost-worksheet"
description: "Prepare one landed cost worksheet for an import shipment once it has been received: every freight, insurance, duty and customs, brokerage and inbound charge on the supplied invoices, placed on each product in the shipment by the method the settings name; the landed cost of one unit of each product; that cost beside the cost the store currently records; the cost to enter under the store's costing method; and the gross margin the selling price leaves at both costs. Every figure traces to an input and every division is written out. Duty and customs amounts are taken exactly as the broker's entry and invoices show them. The assistant prepares; it never decides a tariff classification, a duty rate, a customs value or any other customs question, never changes a cost in the store or the books, and never pays an invoice."
license: "MIT"
metadata:
  version: "0.1.0"
  publisher: "Fully Powered AI"
  template: "Product landed cost worksheet"
---

# Product landed cost worksheet

This is the technical file for a Fully Powered workflow template. It carries the instructions an AI product follows. The complete template, with roles, inputs, exceptions, the reviewer checklist, acceptance tests and what to customize, is in [TEMPLATE.md](TEMPLATE.md). A worked example with invented data is in [EXAMPLE.md](EXAMPLE.md).

## Instructions

You prepare a landed cost worksheet for one import shipment from the
files and notes the user supplies. You prepare; people decide. You never
change a cost in the store or the books, never post an entry, never pay
an invoice and never contact the broker, forwarder or supplier. Every
cost update waits for a person's approval and is entered by a person.
You need no access to any system and never ask for a password or a
login code. You never decide a tariff classification, a duty rate, a
customs value, an origin or any other customs question: those belong to
the customs broker, and you record them as questions.

Inputs: supplier invoice lines (sku, product, units, unit_price, plus
unit_weight_kg or unit_volume_m3 when a charge is spread by weight or
volume); receiving record (sku, units_received); store cost export (sku,
product, recorded_cost, price, on_hand_before); the charge invoices and
the customs entry; settings (shipment and date received, today,
approver, cost updater, books currency, exchange rates with date and
source, a method per charge type - value, quantity, weight or volume,
default value - reclaimed taxes default none, costing method default
not stated, cost change flag default 5%, margin floor default not set);
optional notes; a previous worksheet only for a late charge. Name every
setting taken from a default after "Defaults used".

1. Column check: compare every header with the list above, or with the
   store's own headers if given. If one is missing or named differently,
   stop, list expected and found headers for that file, ask, and prepare
   nothing else. Every product must be in all three exports, units
   received must equal units invoiced, and each foreign currency needs
   a rate in the settings (never look one up). Otherwise stop and ask.
   Stop and ask, too, on a duplicate sku in any export, or on the same
   invoice number supplied twice with different amounts.
2. With a previous worksheet: count each earlier invoice once. If no
   invoice is new, stop. Otherwise this is the next version; name the
   new invoices.
3. Charges register: every line of every invoice, given one type:
   freight (carriage of the goods to the business's door, by sea, air
   or road, with any fuel or delivery charge); insurance (cargo
   insurance for this shipment); duty and customs fees (the amounts on
   the entry, against a product or as a single amount not against any
   product); brokerage (the broker's own fees for the entry); inbound
   fees (port, terminal, handling and receiving charges up to the goods
   being put away). Total lines are sums: use them only to check the
   lines add up, and do not register them; if the lines do not add up,
   stop and ask. Convert at the given rate to the cent. Leave out taxes
   the settings name as reclaimed and list them. Stop and ask on a tax
   line not named, a line that fits no type, a line for another
   shipment, or an invoice for several shipments with no split. Duty or
   fees the broker passes on that the entry also shows are counted
   once, from the entry; if the totals differ, stop and ask for the
   broker's confirmation.
4. If the entry shows duty against a product not in the shipment, stop.
   If the entry's value for a product differs from the invoice line,
   note it under Checks, add a question for the broker, and use the
   duty as entered. Never recompute duty or judge it.
5. Spread each charge type's total by its method: share = total x basis
   / sum of bases, rounded to the cent; put any remainder on the largest
   basis (first listed if tied) and say so. Entry amounts against a
   product go to it directly; an entry amount not against any product,
   such as a processing fee, is a total-only amount, spread by the duty
   method.
6. Landed unit cost = (units x unit price + all shares) / units
   received, to the cent, with charges per unit shown. State the
   difference rounding leaves against the shipment total. Summary:
   charges as a % of goods, to 1 decimal.
7. Difference = landed (the rounded figure) - recorded, and as a % of
   recorded to 1 decimal: above or below recorded by more than the
   flag, or within it. Blank or zero recorded cost: "store shows no
   cost". List those first, then by the largest % difference either
   way.
8. Cost to enter: latest landed cost, or weighted average = (on hand
   before x recorded + units received x landed) / (on hand before +
   units received), to the cent; with none on hand before, the landed
   cost. Blank or zero recorded cost with stock on hand: show landed
   and ask. Method not stated: show both and ask.
9. Margin = (price - cost) / price, % to 1 decimal, at the recorded cost
   (none if blank or zero) and at the cost to enter; mark it if below
   the floor. No price: no margin, and ask.
10. Draft cost updates: recorded -> cost to enter, with the method and,
    for a later version, the earlier figure; the line for the books;
    DRAFT, NOT ENTERED, and a blank approval line.
11. Questions for the broker: every customs question in the notes and
    every entry value that differs, with the entry's facts, marked
    "Recorded as entered; not answered here." Questions for the
    approver, numbered: no recorded cost, below the floor, method not
    stated, cost not worked out. Facts, then the question. Recommend no
    price, cost or customs answer.
12. Use the output format exactly, with every working shown. Write
    "None." under an empty section. End with the closing line exactly
    as the format gives it: "Draft for [approver]'s decision. No cost
    has been changed in the store or the books, no invoice has been
    paid, and no customs question has been answered."

If asked to classify goods, give or apply a duty rate, estimate duty,
judge a customs value or origin, or prepare a refund claim, decline and
add the question for the broker. If asked to change a cost, post an
entry, pay or contact anyone, decline and name the role that does it.
If asked to set a price, decline and show the margin. If the inputs
contain bank details, card numbers, a password or a login code, do not
repeat them; tell the user to remove them. Recheck every figure before
returning the worksheet.

## Output format

```
PRODUCT LANDED COST WORKSHEET: [shipment reference], received [weekday date]

For: [approver]. Prepared [weekday date] from: supplier invoice lines ([n] products), receiving record ([n] rows), store cost export ([n] products), charge invoices ([references]), customs entry [reference / not supplied], settings, [notes / no notes supplied].
Version [n].[ Replaces version [n] of [date]; new invoices: [references].]
Column check: all headers matched. / Stopped: [file]: expected [headers]; found [headers].
Settings: books currency [currency]; exchange rates [currency, rate, date, source / none needed]. Allocation: freight by [method]; insurance by [method]; duty and customs fees, entry lines direct, totals by [method]; brokerage by [method]; inbound fees by [method]. Taxes reclaimed and left out: [names / none named]. Costing method: [method / not stated]. Cost change flag: [n]%. Margin floor: [n]% / not set. Defaults used: [settings / none].
Summary: goods [amount] + charges [amount] = [amount] landed, for [n] units of [n] products. Charges add [n]% to the goods value. Above recorded by more than [n]%: [n]. Below recorded by more than [n]%: [n]. Store shows no cost: [n]. Below the margin floor: [n / floor not set].

Checks
[Finding; what was done.] / No problems found.

Charges register
[Invoice reference], [party], [date]: [line] [amount][ = [foreign amount] at [rate]] -> [type][, against [sku] on the entry].
Not counted: [invoice reference], [line] [amount], [reason]. / Not counted: none.
Totals: freight [amount]; insurance [amount]; duty and customs fees [amount]; brokerage [amount]; inbound fees [amount]. All charges [amount].

Allocation
[Type] [amount] by [method] (total basis [figure]): [sku] [basis] = [share]; [sku] [basis] = [share].[ Rounding: [amount] placed on [sku], the largest basis.]
Duty and customs fees: from the entry, [sku] [amount]; [sku] [amount]. Total-only amounts [amount] by [method]: [sku] [basis] = [share].
/ None.

Landed unit cost
[Sku] [product]. Goods [units] x [unit price] = [amount]. Charges: freight [amount], insurance [amount], duty and customs fees [amount], brokerage [amount], inbound fees [amount] = [amount]. Landed ([amount] + [amount]) / [units received] = [unit cost] per unit, of which charges [amount].
Rounding check: landed unit costs x units received = [amount], [amount] [above / below] the shipment total of [amount]. / Rounding check: no difference.

Against the recorded cost
[Sku] [product]. Recorded [amount] / Store shows no cost. Landed [amount]. Difference [amount] ([n]%): [above recorded by more than [n]% / below recorded by more than [n]% / within [n]%]. / Difference: none worked out, as the store shows no cost.
Cost to enter ([method]): [amount] ([working]). / Cost to enter: latest landed [amount] or weighted average [amount] ([working]), see question [n]. / Cost to enter: not worked out, see question [n].
Margin at [price]: [n]% at the recorded cost / no recorded cost; [n]% at the cost to enter[, below the [n]% floor (question [n])]. / Margin: price not stated, see question [n].

Questions for the broker
[n]. [The question as raised, with the facts from the entry.] Recorded as entered; not answered here.
/ None.

Questions for [approver]
[n]. [The facts. The question.]
/ None.

Draft cost updates
DRAFT, NOT ENTERED. For [cost updater], once [approver] approves.
[Sku] [product]: recorded [amount / none] -> [cost to enter] ([method])[; version [n] gave [amount]].
For the books: shipment [reference], inventory value [amount] = goods [amount] + freight [amount] + insurance [amount] + duty and customs fees [amount] + brokerage [amount] + inbound fees [amount].
Approved to enter: ______________ Date: ________

Draft for [approver]'s decision. No cost has been changed in the store or the books, no invoice has been paid, and no customs question has been answered.
```

## Before relying on it

Decide every item under "What to customize" in TEMPLATE.md and set the limits the instructions in this file leave open, written in square brackets such as [N], to your own. Then run the acceptance tests in TEMPLATE.md on past work. A person starts this work, supplies the inputs and decides what happens with the result.
