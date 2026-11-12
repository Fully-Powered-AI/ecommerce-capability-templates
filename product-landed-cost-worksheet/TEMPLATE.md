# Product landed cost worksheet

Workflow template, version 0.1.0.

## Purpose

Prepare one landed cost worksheet for an import shipment once it has been received: every freight, insurance, duty and customs, brokerage and inbound charge on the supplied invoices, placed on each product in the shipment by the method the settings name; the landed cost of one unit of each product; that cost beside the cost the store currently records; the cost to enter under the store's costing method; and the gross margin the selling price leaves at both costs. Every figure traces to an input and every division is written out. Duty and customs amounts are taken exactly as the broker's entry and invoices show them. The assistant prepares; it never decides a tariff classification, a duty rate, a customs value or any other customs question, never changes a cost in the store or the books, and never pays an invoice.

## When to use it and when not to

Use it when an import shipment has been received into stock and its charge invoices are in: the forwarder's freight invoice, the cargo insurance, the customs broker's entry and invoice, and any port or receiving fees. Run it again, as a new version, when a charge invoice for the same shipment arrives after the worksheet was prepared.

Do not use it:

- to decide what to reorder or when. That is the inventory reorder plan;
- to see total spend by supplier or category across a period. That is supplier spend analysis;
- to check a supplier's bill or prepare a payment run;
- to classify goods, work out what duty should be, check a customs value or country of origin, or claim a duty refund. Those questions go to the licensed customs broker, and the worksheet only records them;
- to set selling prices. The worksheet shows the margin; the owner decides any price;
- to post the cost of goods sold for orders already shipped, or to revalue stock in the books. The bookkeeper or accountant does that from the approved worksheet.

## Roles

- **Runs it:** the owner, the operations lead, the buyer or the bookkeeper of the store.
- **Answers the questions and approves the costs to enter:** [your approver], usually the owner.
- **Enters approved costs in the store and records the shipment in the books:** [your cost updater], usually the bookkeeper. Always a person, after approval.
- **Answers every customs question:** the customs broker who filed the entry.

## Inputs

The assistant works only from the files and notes the person supplies. It needs no connection to the store, the accounts, the broker or the forwarder, and never asks for a password or a login code.

1. **The supplier's invoice lines for the shipment,** as an export. One row per product. Default column headers: `sku`, `product`, `units`, `unit_price`. Add `unit_weight_kg` when any charge is spread by weight and `unit_volume_m3` when any charge is spread by volume. `unit_price` is the price per unit on the supplier's invoice, before any of the charges below.
2. **The receiving record.** One row per product received from this shipment. Default column headers: `sku`, `units_received`.
3. **The store cost export.** One row per product in the shipment. Default column headers: `sku`, `product`, `recorded_cost`, `price`, `on_hand_before`. `recorded_cost` is the cost per unit the store holds now, blank or 0 if none; `price` is the current selling price before sales tax; `on_hand_before` is the units on hand before this shipment was received.
4. **The charge invoices,** as documents or text: the forwarder's invoice, the cargo insurance invoice or certificate, the customs broker's invoice, the customs entry the broker filed (or its summary showing the duty against each product), and any port, terminal or receiving invoices. Each must name this shipment.
5. **The settings,** typed: the shipment reference and the date it was received; today's date; who approves; who updates costs; the books currency, and an exchange rate for each other currency on any invoice, with the date and source the person used; the allocation method for each charge type; [your reclaimed taxes]; [your costing method]; [your cost change flag]; [your margin floor].
   - Allocation methods are value (units × unit price), quantity (units received), weight (units × unit weight) or volume (units × unit volume). Default when not given: value for every charge type. Duty and customs amounts the entry shows against a product always go to that product; only amounts the entry shows as a single figure for the whole shipment and not against any product, such as a customs processing fee, are spread, by the method set for duty and customs fees. The worksheet calls these total-only amounts.
   - [your reclaimed taxes]: taxes on the invoices that the books reclaim, such as import VAT or GST, which are left out of cost. Default: none named.
   - [your costing method]: latest landed cost, or weighted average. Default: not stated.
   - [your cost change flag]: the difference from the recorded cost worth flagging, as a percentage of it. Default 5%.
   - [your margin floor]: the lowest gross margin the owner accepts. Default: none set, and the worksheet says so.
   The Settings line of the worksheet names, after "Defaults used", each setting that came from a default.
6. **Notes** (optional): anything the owner wants asked of the broker, and anything else the person knows about the shipment. If none, write "no notes supplied" in the header.
7. **The previous worksheet** for this shipment, only when a late charge invoice has arrived. Supply the original inputs again with it, plus the new invoice.

**Column check.** Before any arithmetic, compare each export's headers with the defaults, or with [your column headers] if the store has set its own. If a required header is missing or named differently, or a weight or volume column is missing when a setting needs it, stop. List the headers expected and found for that file, ask which column is which, and prepare nothing else. Never guess a column.

## The procedure

1. **Check the inputs.** Run the column check. Every product in the supplier's invoice lines must appear in the receiving record and the store cost export, and the reverse. Units received must equal units invoiced for every product. Each invoice in a currency other than the books currency needs a rate in the settings; the assistant never looks one up. A duplicate `sku` in any export, or the same invoice number supplied twice with different amounts: stop and ask.
2. **Guard against a second allocation.** If a previous worksheet is supplied, compare its charges register with the invoices now supplied. An invoice already in it is counted once. If no invoice is new, stop: there is nothing new to place. Otherwise this worksheet is the next version, and the header names the new invoices.
3. **Build the charges register.** Read every line of every charge invoice and give it one type:
   - freight: carriage of the goods to the business's door, by sea, air or road, with any fuel or delivery charge;
   - insurance: cargo insurance for this shipment;
   - duty and customs fees: the amounts on the customs entry, against a product or as a single amount not against any product, such as a processing fee;
   - brokerage: the broker's own fees for the entry;
   - inbound fees: port, terminal, handling and receiving charges up to the goods being put away.
   The total lines of the invoices and the entry are sums, not charges: they are used only to check that the lines add up, and are not registered. If the lines do not add up to the total, stop and ask. Convert any other currency at the rate given, to the cent. A tax the settings name as reclaimed is left out, and listed. A tax line the settings do not name, a line that fits no type, a line for another shipment, or an invoice that covers several shipments without splitting them: stop and ask. When the broker's invoice passes on duty or customs fees that the entry also shows, count them once, from the entry, and check that the two totals agree; if they differ, stop and ask the person to get the figure confirmed by the broker.
4. **Check the entry against the invoice.** If the entry shows duty against a product not in the shipment, stop and ask. If the value the entry shows for a product differs from the supplier's invoice line, list it under Checks, add a question for the broker with both figures, and use the duty exactly as entered. Never recompute duty, and never judge whether a classification, rate or value is right.
5. **Place each charge.** For each charge type, take its total and spread it over the products by its method: share = total × the product's basis ÷ the sum of the bases. Round each share to the cent. If the shares do not add back to the total, put the difference on the product with the largest basis (the first listed, if two are equal) and say so. Duty and customs amounts the entry shows against a product go to that product directly; a duty or customs amount the entry shows not against any product, such as a processing fee, is a total-only amount and is spread by the method set for duty and customs fees.
6. **Work out each landed unit cost.** Goods = units × unit price. Charges = the product's shares of all five types. Landed unit cost = (goods + charges) ÷ units received, rounded to the cent, with the charges per unit shown separately. Then multiply each landed unit cost by its units, add them, and state the difference from the shipment total that rounding leaves. For the Summary, charges as a percentage of the goods value, to one decimal place.
7. **Compare with the recorded cost.** Difference = landed unit cost, the rounded figure, − recorded cost, and as a percentage of the recorded cost to one decimal place. Mark it "above recorded by more than [your cost change flag]", "below recorded by more than [your cost change flag]" or "within [your cost change flag]". A blank or zero recorded cost is marked "store shows no cost": until it is set, the store's margin reports treat that product as costing nothing. List the products with no recorded cost first, then the rest from the largest percentage difference, either way, to the smallest.
8. **Work out the cost to enter.** Latest landed cost: the landed unit cost. Weighted average: (on hand before × recorded cost + units received × landed unit cost) ÷ (on hand before + units received), rounded to the cent; with nothing on hand before, it is the landed unit cost. If the recorded cost is blank or zero with stock on hand before, the weighted average cannot be worked out: show the landed unit cost and ask. Costing method not stated: show both figures and ask which the store uses.
9. **Work out the margin.** Gross margin = (price − cost) ÷ price, as a percentage to one decimal place, at the recorded cost (unless it is blank or zero) and at the cost to enter. If the margin at the cost to enter is below [your margin floor], mark it. A blank price: no margin, and a question.
10. **Draft the cost updates.** One line per product: recorded cost, cost to enter and the method, and, for a later version, the figure the previous version gave. Then the line for the books: the shipment's inventory value as goods plus each charge type. Mark it DRAFT, NOT ENTERED, with a blank approval line.
11. **Write the questions.** Questions for the broker: every customs question the notes raise and every entry value that differs from the invoice, each with the facts from the entry, marked as recorded and not answered. Questions for the approver, numbered, in this order: products with no recorded cost; margins below the floor; the costing method, if not stated; any cost that could not be worked out. Each gives the facts and asks; none recommends a price, a cost or a customs answer.
12. **Return the worksheet** to the person who ran it, for [your approver]. A person enters the approved costs and records the shipment in the books.

## Exceptions and stop conditions

- **A column header is missing or named differently, or a weight or volume column is missing when a setting needs it:** stop; list expected and found headers; ask.
- **A product is missing from one of the three exports, or units received differ from units invoiced:** stop and ask which quantity stands. A short or damaged delivery is the person's to settle with the supplier first.
- **An invoice in another currency with no rate in the settings:** stop and ask for the rate and its source. Never look one up.
- **An invoice's or the entry's lines do not add up to its total, a charge line that fits no type, a tax line the settings do not name, a line for another shipment, or an invoice covering several shipments without a split:** stop and ask.
- **The broker's invoice and the entry disagree on duty or customs fees, or the entry shows duty against a product not in the shipment:** stop; ask the person to get the figure confirmed by the broker.
- **A previous worksheet is supplied and no invoice is new:** stop; nothing is placed twice.
- **Asked to classify goods, name or apply a duty rate, estimate duty, judge a customs value or origin, say whether duty was charged correctly, or prepare a refund claim:** decline; add the question to Questions for the broker with the facts from the entry.
- **Asked to change a cost in the store, post an entry in the books, pay an invoice or contact the broker, forwarder or supplier:** decline; name the role that does it.
- **Asked to set or recommend a selling price:** decline; show the margin and leave the price to the approver.
- **The inputs contain bank details, card numbers, a password or a login code:** do not repeat them; tell the person to remove them from the source.

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

## Reviewer checklist

1. Every export header matched, or the worksheet stopped. (Bookkeeper)
2. Units received equal units invoiced for every product. (Buyer)
3. Every line of every charge invoice, other than its total line, appears in the charges register, counted or not counted with a reason, and duty passed on by the broker is counted once. (Bookkeeper)
4. Each charge type's shares add back exactly to its total, and each method matches the settings. (Bookkeeper)
5. Duty against each product matches the entry exactly; nothing was recomputed from a rate. (Approver)
6. Landed unit costs, differences, costs to enter and margins recompute correctly with the rounding stated. (Bookkeeper)
7. Every customs question sits under Questions for the broker and none is answered. (Approver)
8. No price, cost or customs answer is recommended. (Approver)
9. The cost updates are approved before anyone enters them in the store or the books. (Approver)

## Acceptance tests

Proposed tests. The first uses the inputs of the two recorded runs on the invented example (see the trial record); the others have not been run.

1. **Normal shipment.** The invented example's inputs. Expected: the worksheet in the example, figure for figure: the $358.05 of duty and the $32.00 processing fee that the broker's invoice passes on are counted once, from the entry, and listed under Not counted, so duty and customs fees total $390.05; the rounding check is $1.25 above the shipment total.
2. **Renamed column.** The store cost export has `cost_per_item` instead of `recorded_cost`. Expected: stops; lists expected and found headers; prepares nothing.
3. **Short delivery.** 190 bowls received against 200 invoiced. Expected: stops and asks which quantity stands.
4. **Reclaimed tax.** The broker's invoice also carries $1,020.00 of import VAT, and the settings name import VAT as reclaimed. Expected: the VAT line under Not counted as a reclaimed tax and named in the Settings line; all charges stay $2,031.25 and every figure stays as in the example.
5. **Broker totals disagree.** The broker's invoice passes on $368.05; the entry totals $358.05. Expected: stops; asks for the figure to be confirmed by the broker.
6. **Foreign currency.** An insurance invoice in euros with no rate in the settings. Expected: stops and asks for the rate and its source; looks nothing up.
7. **Weight without weights.** Freight set to weight and no `unit_weight_kg` column. Expected: stops at the column check.
8. **Rounding remainder.** $1,200.00 of freight over weights of 270, 360, 60 and 330 kg. Expected: shares 317.65, 423.52, 70.59 and 388.24, with $0.01 taken off the largest basis and said so.
9. **No recorded cost.** A product with a blank recorded cost and nothing on hand. Expected: listed first, marked "store shows no cost", cost to enter equal to the landed unit cost, and a question.
10. **Late charge.** The previous worksheet plus a new $60.00 receiving invoice. Expected: version 2 naming the new invoice, every earlier invoice counted once, and each cost update showing what version 1 gave.
11. **Nothing new.** The previous worksheet and the same invoices again. Expected: stops; nothing placed twice.
12. **Customs question.** "Should the boards have paid duty? Work out what the rate should be." Expected: declines to answer or estimate; records the question for the broker with the entry's figures.
13. **Asked to update the store.** "Change the costs in the store now." Expected: declines; names the cost updater and the approval.
14. **Unknown tax line.** A forwarder's invoice carries a tax on its fees that the settings do not name. Expected: stops and asks whether the books reclaim it.
15. **Total does not add up.** FB-2291 shows a total due of $1,305.00 against lines that add to $1,295.00. Expected: stops and asks; registers nothing from the total line.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
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
```

## What to customize

- [your column headers]: your store's and supplier's export headers, so the check passes without a question.
- [your approver] and [your cost updater], and whether a cost change above a set amount needs a second approver.
- The allocation method for each charge type: many importers spread freight by weight or volume and insurance by value.
- [your reclaimed taxes]: the import taxes your books reclaim, agreed with your accountant.
- [your costing method]: latest landed cost or weighted average, as your accountant keeps the books.
- [your cost change flag] and [your margin floor].
- Your usual charge invoices and which of the five types each line belongs to, so new lines are rare.
- Which files the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Editorially reviewed. Tried on its invented example on 10 November 2026 in two runs in Claude: the first on the template as first written, the second, not blind, on the instructions as they now stand, after small clarifications to the procedure and the pasted instructions that the trial record lists. Both runs followed a clean path, so the record notes that none of the stop conditions was exercised. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
