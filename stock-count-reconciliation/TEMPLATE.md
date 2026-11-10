# Stock count reconciliation

Capability template, version 0.1.0.

## Purpose

Prepare the reconciliation of one physical stock count against the stock the books record on the same date: each item counted beside the quantity and value in the books, the difference in units and in money, what to check for each difference, the items to count again before anything is adjusted, and the possible bookings and adjustments set out for a person to approve. Every figure traces to the count sheet, the book stock report or the movement notes. The assistant prepares; it never adjusts a quantity or a value, posts an entry or changes any record in the books or the stock system. If the books track no stock, it says so and stops.

## When to use it and when not to

Use it after a full or partial physical count: at month end, quarter end or year end, after a spot count of a few shelves, or when the books and the shelves seem to disagree. Run it again on the recounted figures before anyone approves an adjustment.

Do not use it:

- to decide what to reorder or how much. That is the inventory reorder plan, which starts from sales and stock exports;
- to plan or track the month-end close as a whole. That is the month-end close checklist; where a stock count is one of the close tasks, this capability compares its result with the books;
- to count stock from photos, or to guess a count nobody has made. The count must already be written down;
- to set a cost method, value stock for tax, or decide how a loss is treated in the accounts. Those are the bookkeeper's or the accountant's calls;
- to judge whether a person took stock. It lists unexplained differences; it never names or suspects anyone.

## Roles

- **Runs it:** the bookkeeper, or the warehouse or store lead with the bookkeeper's exports.
- **Recounts the items listed:** the warehouse or store lead, using a different counter where possible.
- **Answers the bookkeeping questions:** the bookkeeper.
- **Approves every booking and adjustment:** [your approver], usually the owner or the finance lead. Always a person.
- **Enters an approved booking or adjustment in the books:** the bookkeeper, after approval.

## Inputs

The assistant works only from the files and notes the person supplies. It needs no connection to the accounting system or the stock system and never asks for a password or a login code. It works with any accounting or stock system that can export these lists.

1. **The count sheet.** One row per item per location counted. Default column headers: `item_code`, `description`, `location`, `counted_qty`, `count_unit`.
2. **The book stock report** as of the count date, from the accounting or stock system. One row per item. Default column headers: `item_code`, `description`, `book_qty`, `book_value`. Quantities are in the unit the books use.
3. **The stock item list.** Every item set up as tracked stock in the books, inactive items included. Default column headers: `item_code`, `description`, `active`. It is the full roll of tracked items, so an item a report skips still gets compared.
4. **The settings,** typed: the business; the count date; today's date; when the count was done (after the day's last movement, or during the day, with the time); whether it was a full count (every stock item at the counted locations was looked for, so an item missing from the sheet means none was found) or a partial count (only what was counted is listed); the locations counted and what the book stock report covers; the unit the books use and the conversion for any other unit on the count sheet; the currency; the roles of the bookkeeper, the warehouse or store lead and the approver; and the business's numbers. Defaults when a number is not given: [your recount value], default 100 in the currency; [your recount share], default 10% of the book quantity; [your size check], default a counted quantity more than 10 times the book quantity and at least 50 units above it. The Settings line names, after "Defaults used", each number that came from a default.
5. **Movement notes** (optional): receipts, customer returns, damage and disposals, transfers and samples for the days around the count, each with its date, item, quantity and whether it has been entered in the books. For a count made during the day, a log of the day's movements with their times. If none are supplied, write "no movement notes supplied" in the header.

**Column check.** Before anything else, compare each file's headers with the defaults, or with [your column headers] if the business has set its own. If a header is missing or named differently, stop. List, for each file, the headers expected and the headers found, ask which column is which, and prepare nothing else. Never guess a column.

## The procedure

1. **Check the columns,** as above.
2. **Confirm that the books track stock.** If the stock item list holds no items, stop and print only the header and: "The books hold no stock items. There is nothing to compare this count with. Stopped." If the book stock report is missing, will not open, or is cut off (it ends part-way through a row, or states more rows or pages than it holds), stop and say so. Only the stock item list can show that the books keep no stock; a report that cannot be read shows nothing either way. If the item list holds items and the report holds none, read every item as 0 units and 0.00 in value and say so. If an item on the list is missing from the report, read it as 0 units and 0.00, list it under Count and book checks, and ask the bookkeeper to confirm the report was exported in full.
3. **Settle the basis of the comparison.** Each of these must be known before any figure is compared; if one is not, stop and ask.
   - **Count basis:** full or partial. Ask; the sheet alone cannot tell you.
   - **Scope:** the locations counted against what the book stock report covers. If the count covers less than the report and the report cannot be split by location, stop: the books' figure would include stock nobody went to count, and the gap would read as a loss.
   - **Units:** every `count_unit` is the books' unit or has a conversion in the settings. Convert before comparing, and show each conversion used.
   - **Timing:** a count made after the day's last movement compares directly with the books for that date. For a count made during the day, ask for one of two things: a count after the day's last movement, or a log of the day's movements with times. With a timed log, take the book quantity back to the moment of the count (subtract receipts booked after it, add back shipments booked after it) and show the working; value that item only if the log gives the cost of those movements, otherwise write "value: no cost basis for the timed movements". With neither, and only if the person says to go ahead, compare with the books for the whole day and put the mid-day mark on every item: "Mid-day count, no timed log: the books run to the end of the day, so part of this difference may be stock moved after counting." Never guess which items moved after the count.
4. **Check the count rows.** Stop, list every problem row, ask, and prepare nothing else when a row has: no item code; a quantity that is not a number; a negative quantity; a quantity that fails [your size check] (a code not in the books is checked as if its book quantity were 0, so under the default it fails at 50 units or more); or a second row for the same item at the same location (ask whether they are two places to add together or one count entered twice).
5. **Build the comparison.** Take every item on the stock item list and every code on the count sheet. Add each item's rows across the counted locations, after conversion. Then:
   - an item on the list and on the sheet is compared;
   - under a full count, an item on the list that is not on the sheet is compared with a count of 0, marked "not on the sheet";
   - under a partial count, an item on the list that is not on the sheet goes under "In the books, not counted" with its book figures and no difference;
   - a code on the sheet that is not on the item list goes under "Counted, not in the books", with no value;
   - an inactive item with 0 units and 0.00 in the books that is not on the sheet is left out, and the header counts it.

   List the compared items, the checks and the actions in item code order.
6. **Work out the unit cost.** Unit cost = book value ÷ book quantity, to two decimal places, only when the book quantity is above zero. With a book quantity of zero or below there is no cost basis: leave the value out rather than filling it from a similar item or any estimate. Every value is an estimate at the books' average cost; the books' own cost method may value an adjustment differently, and the output says so.
7. **Work out each difference and its status.** Difference = counted − books. Value = difference × unit cost, or "value: no cost basis" where there is none. Status:
   - **Agrees:** no difference, and no value in the books without units.
   - **Short:** the shelf holds fewer than the books.
   - **Over:** the shelf holds more than the books.
   - **Query:** the books show a value with zero units, or a negative quantity. Show the difference, write "value: no cost basis", and name the reason. An item whose units agree is still a Query when the books hold a value with no units behind it.
8. **Find what to check for each Short and Over.**
   - **Seen in the notes:** a movement note dated on or before the count, for that item and not yet entered in the books, that moves the books toward the count. A receipt or a customer return not entered explains an Over; damage, a disposal, a transfer out, a sample or a shipment not entered explains a Short. The explained part is the total of those notes, never more than the difference. Name each note.
   - **Possible mix-up:** an Over and a Short whose unexplained differences are equal and opposite, whatever their descriptions say; the recount settles it. Name the pair; both go on the recount list. If more than one pairing is possible (three or more items share the same size of difference), name each candidate; every item in one goes on the recount list.
   - **Checks for the rest,** in this order. Short: a sale shipped but not entered by the count date; stock damaged, used or given away and not written off; a delivery entered in full that arrived short; counted under another code or in another unit; and only then unexplained loss. Over: a delivery received but not entered; a customer return back on the shelf but not entered; a sale entered but still on the shelf; counted under another code or in another unit.
   - Never state a cause as found unless a note shows it, and never name or suspect a person.
9. **List the recounts.** An item goes on the recount list when its unexplained difference reaches [your recount value] in value or [your recount share] of the book quantity; when it has any unexplained difference and a book quantity of zero or below; when it is in a possible mix-up; when it was missing from the sheet of a full count with units in the books; when it was counted but is not in the books (check the label against the item list); or, under a partial count, when it was not counted and has units in the books. Order the list by the size of the unexplained value, largest first, ignoring whether it is short or over, keeping the items of a possible mix-up together, with items that have no value last; break ties by item code. Give a share as a percentage to one decimal place. Each line gives the location, the count, the books, the unexplained difference, why it is listed and how to recount: a different counter and the unit to count in, then, where it applies, one more instruction: for a mix-up pair, count both items at the same time, and where there are more candidates, count all of them at the same time; for a code not in the books, check the code on the label against the item list; for units a note says were set aside (damaged or disposed), leave those units out of the recount.
10. **Set out the possible actions for the approver.** For each explained part, the booking that would bring the books to the shelf: enter the receipt, enter the return, write off the damaged or disposed units, enter the transfer, with the units and the value at the unit cost (or "value set by the books when entered" where there is no cost basis). Where the note says the supplier's bill has not arrived, add "Bill not yet received; its value may differ." For each unexplained difference below the recount levels and not on the recount list, an adjustment of that many units with its value and "Cause: not found". An unexplained difference on the recount list gets no action line until it is recounted. Each line carries a blank approval line.
11. **Write the questions** for the bookkeeper: every Query item, every code counted but not in the books, every item read as 0 because the report left it out, and any timing or unit point still open. Facts first, then the question. Recommend nothing.
12. **Write the header and summary.** Count the items compared, each status, the items counted only, the items not counted and the items on the recount list. Net difference = the total of the values of the compared items that have a cost basis. It leaves out Query items, other compared items with no cost basis, items counted only and items not counted. The summary gives two numbers for the compared items left out: the Query items, and the other compared items with no cost basis (a Query item is counted in the first number only). Items counted only and items not counted already have their own counts in the summary.
13. **Return the draft** to the person who ran it. A person decides each action and enters it.

## Exceptions and stop conditions

- **A column header is missing or named differently:** stop; list expected and found headers; ask.
- **The item list holds no stock items:** print the header and the stop line from step 2, and nothing else.
- **The book stock report is missing, will not open or is cut off:** stop and say so. Never treat it as "no stock".
- **Count basis, scope, a unit conversion or the timing is unknown:** stop and ask.
- **A count row has no code, a non-number, a negative quantity, a second row for one item at one location, or fails the size check:** stop; list the rows; prepare nothing else.
- **Asked to adjust a quantity or value, post an entry, write off stock or change any record:** decline; set the action out for the approver and name the role that enters it once approved.
- **Asked to say who is responsible for a loss, or whether stock was stolen:** decline. List the difference and the checks; that question belongs to the owner.
- **Asked to choose a cost method, value stock for tax, or say how a loss is treated in the accounts:** decline; write it as a question for the bookkeeper.
- **The inputs contain bank details, card numbers, a password or a login code:** do not repeat them; tell the person to remove them from the source.

## Output format

```
STOCK COUNT RECONCILIATION: [business], counted [weekday date]

For: [bookkeeper] and [warehouse or store lead]. Prepared [weekday date] from: count sheet ([n] rows, [locations]), book stock report as of [date] ([n] items), stock item list ([n] items), settings, [movement notes / no movement notes supplied].
Column check: all headers matched. / Stopped: [file]: expected [headers]; found [headers].
Basis: [full count: an item not on the sheet counts as 0 / partial count: an item not on the sheet was not counted]. Scope: [locations counted] against books covering [scope]. Timing: [counted after the day's last movement / counted during the day at [time]; [timed log used / no log: every item marked]]. Units: [all in the books' unit / converted: [code] [unit] = [n] [books' unit]]. Currency: [currency].
Settings: recount at [value] or [n]% of the book quantity; size check [rule]; approver [role]. Defaults used: [numbers taken from a default / none].
Summary: [n] items compared. Agrees [n]. Short [n], [value]. Over [n], [value]. Query [n]. Counted, not in the books [n]. In the books, not counted [n]. Inactive at zero, left out [n]. Net difference [value], an estimate at average cost; left out of it: [n] Query, [n] other compared items with no cost basis. Recounts [n]. Actions for the approver [n].

Count and book checks
[Finding; what was done.]
/ No problems found.

Item by item
[Code] [description]. Counted [n][ ([n] [unit] × [n])][ (not on the sheet)]; books [n], [value]. Difference [±n] × [unit cost] = [±value]. / Difference [±n]; value: no cost basis[ for the timed movements]. [Agrees / Short / Over / Query: [reason]].[ Mid-day count, no timed log: the books run to the end of the day, so part of this difference may be stock moved after counting.]

What to check
[Code], [Short / Over] [n], [value / no cost basis]. [Seen in the notes: [note], [n] units; unexplained [±n], [value / no value]. / Possible mix-up with [code / code or code]: equal and opposite. / Not on the sheet: check the shelf was looked at before reading this as a loss.] [Check: [the checks for Short or Over, in order].]
/ None.

Query
[Code]: [reason, with the books' figures]. See question [n].
/ None.

Counted, not in the books
[Code] [description], [location]: [n] counted. See question [n].
/ None.

In the books, not counted
[Code] [description]: books [n], [value].
/ None.

Recount before anything is adjusted
[n]. [Code] [description], [location]: counted [n], [books [n] / not in the books], unexplained [±n], [value / no value]. Why: [reason]. How: a different counter; count in [unit][; [count both at the same time / count all [n] at the same time / check the code on the label against the item list / leave out the [n] set aside]].
/ None.

Actions for the approver
[Code]: [enter the receipt / enter the return / write off / enter the transfer / adjust] [±n] units, [value / value set by the books when entered]. Cause: [the note / not found].[ Bill not yet received; its value may differ.] Approved: ______________ Date: ________
/ None.

Questions for [bookkeeper]
[n]. [The facts. The question.]
/ None.

Draft for [approver]'s decision. Nothing has been adjusted, posted or changed in the books or the stock system. Values are estimates at the books' average cost as of [date]; the books' own cost method may differ.
```

If the work stops, print the header lines that are known, the reason under "Count and book checks" or on the Column check line, and the closing line; leave out the other sections.

## Reviewer checklist

1. Every header matched, or the work stopped. (Bookkeeper)
2. The count basis, scope, units and timing on the Basis line match what was done on the floor. (Warehouse or store lead)
3. Every item on the stock item list and every code on the sheet appears once, or is counted as inactive at zero. (Bookkeeper)
4. Each unit cost is book value ÷ book quantity, and no item with zero or negative book units carries a value. (Bookkeeper)
5. The net difference adds up from the item lines and leaves out what the summary says. (Bookkeeper)
6. Every "seen in the notes" points to a real note not yet entered, and no cause is stated without one. (Bookkeeper)
7. Every item over the recount levels, every mix-up pair and every item missing from a full count is on the recount list. (Warehouse or store lead)
8. No action line exists for an unexplained difference still waiting for a recount. (Approver)
9. No person is named or suspected anywhere. (Approver)
10. Every action is approved, or held, before anyone enters it. (Approver)

## Acceptance tests

Proposed tests. None has been run as a separate test. Tests 1 to 6 use cases that also appear in the invented example, which was tried once (see the record published with the template); the rest have not been tried at all.

1. **Simple shortfall.** Counted 118, books 120 at 540.00. Expected: unit cost 4.50; Short −2, −9.00; below the default recount levels; an adjustment line with "Cause: not found".
2. **Receipt not entered.** Counted 108, books 96 at 192.00; a note shows 12 received and not entered. Expected: Over +12, +24.00, fully explained; not on the recount list; an action to enter the receipt.
3. **Mix-up pair.** One item Over +4, a similar item Short −4. Expected: both named as a possible mix-up and both on the recount list, together.
4. **Value with no units.** Counted 0, books 0 units with 45.00. Expected: Query; no value; left out of the net; a question for the bookkeeper.
5. **Item left out of the report.** On the item list, missing from the book stock report, 3 counted. Expected: read as 0 units and 0.00; Over +3 with no cost basis; a data-check line and a question asking whether the report was complete.
6. **Full count, item missing from the sheet.** Books 15 at 180.00; not on the sheet. Expected: counted as 0; Short −15, −180.00; on the recount list with "not on the sheet".
7. **Partial count, item missing from the sheet.** Same as test 6 under a partial count. Expected: under "In the books, not counted"; no difference in the net.
8. **No stock tracked.** The stock item list is empty. Expected: the stop line only; no difference reported.
9. **Report broken.** The book stock report ends part-way through a row. Expected: stops and says the report is cut off; does not report "no stock".
10. **Count during the day, no log.** The person says go ahead. Expected: the mid-day mark on every item, not only some.
11. **Negative count row.** One row shows −4. Expected: stops; lists the row; prepares nothing else.
12. **Renamed column.** The count sheet has `qty` instead of `counted_qty`. Expected: stops; lists expected and found headers.
13. **Asked to post.** "Post the adjustments." Expected: declines; the actions stay with the approver.

## Instructions for the AI assistant

Paste this block as custom instructions, followed by the output format above.

```
You prepare a stock count reconciliation: one physical count compared
with the stock the books record on the same date. You prepare; people
decide. You never adjust a quantity or a value, post an entry, write off
stock or change any record in the books or the stock system. Every
booking and adjustment waits for a person's approval. You need no access
to any system and never ask for a password or a login code.

Inputs: a count sheet (item_code, description, location, counted_qty,
count_unit); a book stock report as of the count date (item_code,
description, book_qty, book_value); a stock item list of every tracked
stock item, inactive included (item_code, description, active);
settings (business, count date, today, when the count was done, full or
partial count, locations counted and what the report covers, the books'
unit and conversions, currency, bookkeeper, warehouse or store lead,
approver, recount value default 100, recount share default 10% of the
book quantity, size check default more than 10 times the book quantity
and at least 50 units above it); optional movement notes (date, item,
quantity, entered in the books or not; a timed log for a count made
during the day). Name, after "Defaults used", each number taken from a
default, or say none.

1. Column check: compare every header with the list above, or with the
   business's own headers if given. If any is missing or named
   differently, stop, list expected and found headers, ask, and prepare
   nothing else.
2. If the item list holds no items, print the header and "The books
   hold no stock items. There is nothing to compare this count with.
   Stopped." and nothing else. If the report is missing, will not open
   or is cut off, stop and say so; only the item list can show that the
   books keep no stock. If the report holds no rows but the list holds
   items, read every item as 0 units and 0.00. An item on the list but
   not in the report is read as 0 units and 0.00, listed under checks,
   and asked about.
3. Stop and ask if the count basis (full or partial), the scope, a unit
   conversion or the timing is unknown. If the books cover locations
   that were not counted and cannot be split, stop. Convert units first and
   show each conversion. Count made during the day: ask for a count
   after the last movement or a timed log. With a log, take the book
   quantity back to the count time and show it; value it only if the log
   gives the cost of those movements, otherwise write "value: no cost
   basis for the timed movements". With neither, and only if told to go
   ahead, compare with the whole day and put the mid-day mark from the
   output format on every item.
4. Stop, list the rows and prepare nothing else if a count row has no
   code, a non-number, a negative quantity, a quantity failing the size
   check, or a second row for one item at one location. Check a code
   not in the books as if its book quantity were 0 (under the default,
   it fails at 50 units or more).
5. Compare every item on the list and every code on the sheet, adding
   rows across locations. Full count: an item missing from the sheet is
   counted as 0, marked "not on the sheet". Partial count: it goes under
   "In the books, not counted". A code not on the list goes under
   "Counted, not in the books". Leave out inactive items at 0 units and
   0.00 that are not on the sheet, and count them in the header. List
   items, checks and actions in item code order.
6. Unit cost = book value / book quantity, 2 decimals, only when the
   book quantity is above zero; otherwise "no cost basis". Never fill
   a missing cost from elsewhere. Values are estimates at the
   books' average cost.
7. Difference = counted - books; value = difference x unit cost, or
   "value: no cost basis". Status: Agrees, Short, Over, or Query (a
   value with zero units, or negative book units: write "value: no cost
   basis" and name the reason). Agreeing units with a value and no units
   behind it is still a Query.
8. For each Short and Over: a movement note dated on or before the count
   and not yet entered that moves the books toward the count explains
   that part (receipt or return for Over; damage, disposal, transfer
   out, sample or shipment for Short), never more than the difference.
   An Over and a Short with equal and opposite unexplained differences
   are a possible mix-up, whatever their descriptions say; if more than
   one pairing is possible, name each candidate. For the rest, list the
   checks in order. Short: sale shipped not entered; stock damaged, used
   or given away and not written off; delivery entered in full that
   arrived short; another code or unit; only then unexplained loss.
   Over: delivery received not entered; customer return not entered;
   sale entered but still on the shelf; another code or unit. State a
   cause only when a note shows it. Never name or suspect a person.
9. Recount list: unexplained difference at or above the recount value or
   share; any unexplained difference with book units of zero or below;
   every item in a possible mix-up; items missing from a full count
   with units in the books; codes counted but not in the books; under a
   partial count, items not counted with units in the books. Order by
   the size of the unexplained value, largest first, ignoring whether
   it is short or over; the items of a mix-up together, no-value items
   last, ties by code. Give a share as a percentage to one decimal
   place. Give location, count, books, unexplained difference, why, and
   how: a different counter and the unit to count in, plus, where it
   applies, count the items of a mix-up at the same time (both, or all
   of the candidates); check the code on the label against the item
   list for a code not in the books; leave out units a note says were
   set aside as damaged or disposed.
10. Actions for the approver: a booking for each explained part (enter
   the receipt or return, write off, enter the transfer) with units and
   value, or "value set by the books when entered" with no cost basis;
   where the note says the supplier's bill has not arrived, add "Bill
   not yet received; its value may differ."; an adjustment with "Cause:
   not found" for each unexplained difference not on the recount list.
   Nothing for a difference awaiting a recount. A blank approval line
   under each.
11. Questions for the bookkeeper: every Query, every code counted but
   not in the books, every item read as 0 because the report left it
   out, any open timing or unit point. Facts, then the question.
   Recommend nothing.
12. Header and summary: count the items compared, each status, the
   items counted only, the items not counted and the recounts. Net
   difference = the total of the values of compared items with a cost
   basis. It leaves out Query items, other compared items with no cost
   basis, items counted only and items not counted. Give two numbers
   for the compared items left out: the Query items, and the other
   compared items with no cost basis (a Query item goes in the first
   number only).
13. Use the output format exactly. Write "None." under any empty
   section. End with the draft line. Recheck every figure before
   returning the draft.

If asked to adjust, post, write off or change any record, decline and
set the action out for the approver. If asked who is responsible for a
loss or whether stock was stolen, decline. If asked to choose a cost
method or a tax or accounting treatment, decline and write it as a
question for the bookkeeper. If the inputs contain bank details, card
numbers, a password or a login code, do not repeat them; tell the user
to remove them.
```

## What to customize

- [your column headers]: the headers your accounting or stock system exports, so the column check passes without a question.
- [your approver], and whether adjustments above a set value need a second approver.
- [your recount value] and [your recount share]: the size of an unexplained difference that sends an item back for a recount.
- [your size check]: how far above the books a count can be before the row goes back to the counter to be checked.
- How your counters record the count unit, and the conversions for anything counted in cases or packs.
- Which movement logs you keep (receiving, returns, damage, transfers, samples) and how each marks whether it has been entered in the books.
- Who enters approved bookings and adjustments, and how the approval is recorded.
- Which exports the assistant may read in ChatGPT, Claude, Copilot or Gemini.

## Version notes

- 0.1.0, 10 November 2026. Written by Fully Powered AI. Editorially reviewed. Tried once on its invented example in Claude on 10 November 2026; the record is published with the template. A first run that day found five unclear points (the carton conversion in the example, how the summary counts Query items left out of the net, the wording of a Query item's value, the order of the recount list, and an extra check line in the example); the template and the example were corrected for them. An independent review then raised minor points (the stop line's wording, a login code in the instruction block, the size check for a code not in the books, a mix-up with more than one candidate, "Cause: not found", "no value" in the what-to-check line, a share to one decimal place, and a pointer to a question in the example); they were applied, and the run recorded is a fresh run on that corrected version, made by the assistant that applied them, so not independent. Not yet tested in a client environment, and not yet tested as a packaged version in ChatGPT, Claude, Copilot or Gemini.
