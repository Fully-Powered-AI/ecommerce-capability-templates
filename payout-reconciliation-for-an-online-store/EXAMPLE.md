# Payout reconciliation for an online store: an invented example

*Illustrative example with invented data.* The store (called Store K here), its card payment processor (Processor P), the marketplace it also sells on (Marketplace M), its bank (Bank B), its supplier (Supplier A), the rates, the order and payout numbers and every figure below are invented. Store K is a small online candle shop run by an owner with a part-time bookkeeper. It takes card payments on its own site through Processor P and also sells through Marketplace M. First come the inputs the bookkeeper supplied, in full, then the pack the workflow template returned.

## The inputs

### 1. Settings

```
Store: Store K
Month: October 2026
Today: Tuesday 3 November 2026
Prepared by: the bookkeeper
Approved by: the owner
Posts the entries: the bookkeeper, after the owner approves
Decides on fee disputes, and raises them: the owner
Books kept in: USD
Bank account the payouts reach: Bank B operating account
Bank working days: Monday to Friday; no bank holidays in October or early November
Deposit window: 3 business days
Fee tolerance: $0.01 per line
Channels:
  Processor P, card payments on the store's own site
    Name on the bank statement: PROCESSOR P
    Waiting period: 7 days
  Marketplace M, paid once a month on the 15th
    Name on the bank statement: MARKETPLACE M
    Waiting period: 30 days
```

### 2. Fee schedule (typed by the bookkeeper)

```
Processor P: from its published pricing page, as the owner read it on 1 March 2026
  sale: 2.8% of the gross + $0.25
  refund: the sale's fee is not returned (fee $0.00)
  chargeback: no fee on the chargeback line itself; $20.00 charged as its
    own chargeback fee line

Marketplace M: from the rate card in its seller agreement, dated 1 January 2026
  sale: 12% of the gross (item price plus shipping paid by the buyer)
  refund: the sale's fee is returned, less a $2.00 refund handling fee
  fee: monthly account fee $25.00
  advertising: charged from the store's own campaign settings; not on the rate card
```

### 3. Payouts list (payouts-oct-2026.csv)

```
Channel,Payout ID,Payout Date,Payout Amount
Processor P,PO-P-1007,2026-10-09,159.23
Processor P,PO-P-1021,2026-10-23,197.55
Processor P,PO-P-1030,2026-10-30,135.58
Marketplace M,MP-M-0415,2026-10-15,77.38
```

### 4. Payout line exports

Processor P (lines-processor-p-oct-2026.csv):

```
Channel,Payout ID,Payout Date,Line Type,Order ID,Gross,Fee,Net,Currency
Processor P,PO-P-1007,2026-10-09,sale,K-2101,48.00,-1.59,46.41,USD
Processor P,PO-P-1007,2026-10-09,sale,K-2102,126.00,-3.78,122.22,USD
Processor P,PO-P-1007,2026-10-09,sale,K-2103,32.00,-1.40,30.60,USD
Processor P,PO-P-1007,2026-10-09,refund,K-2088,-40.00,0.00,-40.00,USD
Processor P,PO-P-1021,2026-10-23,sale,K-2110,74.00,-2.32,71.68,USD
Processor P,PO-P-1021,2026-10-23,sale,K-2114,210.00,-6.13,203.87,USD
Processor P,PO-P-1021,2026-10-23,chargeback,K-2071,-58.00,0.00,-58.00,USD
Processor P,PO-P-1021,2026-10-23,chargeback fee,K-2071,0.00,-20.00,-20.00,USD
Processor P,PO-P-1030,2026-10-30,sale,K-2121,96.00,-2.94,93.06,USD
Processor P,PO-P-1030,2026-10-30,sale,K-2125,44.00,-1.48,42.52,USD
```

Marketplace M (lines-marketplace-m-oct-2026.csv):

```
Channel,Payout ID,Payout Date,Line Type,Order ID,Gross,Fee,Net,Currency
Marketplace M,MP-M-0415,2026-10-15,sale,M-7768,28.00,-3.36,24.64,USD
Marketplace M,MP-M-0415,2026-10-15,sale,M-7781,60.00,-7.20,52.80,USD
Marketplace M,MP-M-0415,2026-10-15,sale,M-7790,36.00,-4.32,31.68,USD
Marketplace M,MP-M-0415,2026-10-15,sale,M-7794,84.00,-13.44,70.56,USD
Marketplace M,MP-M-0415,2026-10-15,refund,M-7781,-60.00,5.20,-54.80,USD
Marketplace M,MP-M-0415,2026-10-15,advertising,,-22.50,0.00,-22.50,USD
Marketplace M,MP-M-0415,2026-10-15,fee,,0.00,-25.00,-25.00,USD
```

### 5. Order export (orders-oct-2026.csv: every order dated in October paid through a channel, and the earlier orders the payout lines name)

```
Order ID,Order Date,Channel,Order Total,Refunded Amount,Payment Status
M-7768,2026-09-22,Marketplace M,28.00,0.00,paid
K-2071,2026-09-28,Processor P,58.00,0.00,paid
K-2088,2026-09-30,Processor P,40.00,40.00,refunded
M-7781,2026-10-02,Marketplace M,60.00,60.00,refunded
K-2101,2026-10-05,Processor P,48.00,0.00,paid
K-2102,2026-10-06,Processor P,126.00,0.00,paid
M-7790,2026-10-06,Marketplace M,36.00,0.00,paid
K-2103,2026-10-07,Processor P,32.00,0.00,paid
M-7794,2026-10-09,Marketplace M,84.00,0.00,paid
K-2107,2026-10-12,Processor P,64.00,0.00,paid
K-2110,2026-10-19,Processor P,74.00,0.00,paid
K-2114,2026-10-20,Processor P,210.00,0.00,paid
M-7802,2026-10-20,Marketplace M,45.00,0.00,paid
K-2121,2026-10-27,Processor P,96.00,0.00,paid
K-2125,2026-10-28,Processor P,44.00,0.00,paid
K-2129,2026-10-30,Processor P,52.00,0.00,paid
```

### 6. Bank statement export (Bank B operating account, statement 1 to 31 October 2026, ending Saturday 31 October)

```
Date,Description,Amount
2026-10-02,PROCESSOR P PAYOUT,210.40
2026-10-05,OWNER TRANSFER,500.00
2026-10-07,CARD PAYMENT SUPPLIER A,-312.60
2026-10-12,PROCESSOR P PAYOUT,159.23
2026-10-13,PROCESSOR P PAYOUT,61.96
2026-10-16,MARKETPLACE M DISBURSEMENT,77.38
2026-10-26,PROCESSOR P PAYOUT,197.55
2026-10-28,RENT,-1450.00
```

### 7. Last month's open items (from the September 2026 pack)

```
Still open at 30 September 2026:
1. In transit: Processor P payout PO-P-0930, dated 2026-09-30, $210.40.
   Not on the September statement.
2. Awaiting payout: Marketplace M order M-7768, dated 2026-09-22, $28.00.
```

## The output

**PAYOUT RECONCILIATION: Store K, October 2026**

For: the owner. Prepared by: the bookkeeper. Prepared on Tuesday 3 November 2026.
Prepared from: settings; fee schedule; payouts list payouts-oct-2026.csv (4 payouts); Processor P line export (10 lines); Marketplace M line export (7 lines); order export orders-oct-2026.csv (16 orders); Bank B statement export, 1 to 31 October 2026 (8 rows); last month's open items (2).
Fee rates from: Processor P: published pricing page, as read on 1 March 2026; Marketplace M: rate card in the seller agreement, dated 1 January 2026.

**1. RESULT**

Payouts: 4, $569.74, from 2 channels. In the bank: 3, $434.16. In transit: 1, $135.58. Not placed (no deposit found, or more than one candidate): 0, $0.00.
Fee lines checked: 16. Above the rate: 2, $3.61. Below the rate: 0, $0.00. Not checked: 0.
Differences listed: 4.

**2. CHANNEL SUMMARY**

Processor P (USD)
Gross sales $630.00. Refunds −$40.00. Chargebacks −$58.00. Transaction fees −$39.64. Advertising −$0.00. Adjustments $0.00. Reserve $0.00. Paid out $492.36.
Fee rate: 6.29% of gross sales, counting fixed charges and fees returned on refunds.
Tie-out: $630.00 − $40.00 − $58.00 − $39.64 − $0.00 ± $0.00 ± $0.00 = $492.36. Stated payouts total $492.36. Ties.

Marketplace M (USD)
Gross sales $208.00. Refunds −$60.00. Chargebacks −$0.00. Transaction fees −$48.12. Advertising −$22.50. Adjustments $0.00. Reserve $0.00. Paid out $77.38.
Fee rate: 23.13% of gross sales, counting fixed charges and fees returned on refunds.
Tie-out: $208.00 − $60.00 − $0.00 − $48.12 − $22.50 ± $0.00 ± $0.00 = $77.38. Stated payouts total $77.38. Ties.

**3. PAYOUTS AND THE BANK**

PO-P-1007, Processor P, Friday 9 October 2026, $159.23. Lines: 4, total $159.23, foots. Bank: Monday 12 October 2026, $159.23, 1 business day.
PO-P-1021, Processor P, Friday 23 October 2026, $197.55. Lines: 4, total $197.55, foots. Bank: Monday 26 October 2026, $197.55, 1 business day.
PO-P-1030, Processor P, Friday 30 October 2026, $135.58. Lines: 2, total $135.58, foots. In transit: not on the statement, which ends Saturday 31 October 2026; window runs to Wednesday 4 November 2026.
MP-M-0415, Marketplace M, Thursday 15 October 2026, $77.38. Lines: 7, total $77.38, foots. Bank: Friday 16 October 2026, $77.38, 1 business day.
Deposits from a channel with no payout: Tuesday 13 October 2026, PROCESSOR P PAYOUT, $61.96.
Other credits on the statement, left to the bank reconciliation: 1.

**4. ORDERS**

Lines matched to an order: 14 of 14 sale, refund and chargeback lines. Amounts agree: 14.
Orders dated in October paid through a channel: 13. Paid out: 10. Awaiting payout: K-2129, Processor P, Friday 30 October 2026, $52.00; M-7802, Marketplace M, Tuesday 20 October 2026, $45.00. Not in any payout: K-2107.

**5. FEE CHECK**

Processor P: 10 lines checked, 9 at the rate. Not checked: none. Not fees, not checked against a rate: none.
Above the rate: K-2103, PO-P-1007: charged $1.40, rate gives $1.15, difference $0.25.
Below the rate: none.

Marketplace M: 6 lines checked, 5 at the rate. Not checked: none. Not fees, not checked against a rate: advertising.
Above the rate: M-7794, MP-M-0415: charged $13.44, rate gives $10.08, difference $3.36; 16.00% of $84.00.
Below the rate: none.

**6. DIFFERENCES, WITH THEIR EVIDENCE**

1. Deposit with no payout. Bank B shows a credit of $61.96 on Tuesday 13 October 2026, described PROCESSOR P PAYOUT. No payout in the payouts list, and no payout in transit from last month, has that amount, so the list or the export may be missing a Processor P payout. Evidence: bank statement row dated 2026-10-13; payouts list. Possible link: difference 2, to confirm. Looks into it: the bookkeeper.
2. Paid order not in any payout. Order K-2107, Monday 12 October 2026, Processor P, $64.00, status paid, is named by no line in any October payout. It is dated before Saturday 24 October 2026, when Processor P's 7-day waiting period begins. At Processor P's rate it would pay $61.96 ($64.00 less a $2.04 fee). Evidence: order export row K-2107; Processor P line export. Possible link: difference 1, to confirm. Looks into it: the bookkeeper.
3. Fee above the rate. Order K-2103 in payout PO-P-1007: charged $1.40; 2.8% of $32.00 plus $0.25 gives $1.15; difference $0.25. Evidence: Processor P line export, PO-P-1007, sale K-2103; fee schedule, Processor P. Looks into it: the bookkeeper; the owner decides whether to raise it.
4. Fee above the rate. Order M-7794 in payout MP-M-0415: charged $13.44, which is 16.00% of $84.00; 12% gives $10.08; difference $3.36. Evidence: Marketplace M line export, MP-M-0415, sale M-7794; fee schedule, Marketplace M. Looks into it: the bookkeeper; the owner decides whether to raise it.

**7. LAST MONTH'S OPEN ITEMS**

In transit: Processor P payout PO-P-0930, Wednesday 30 September 2026, $210.40: cleared Friday 2 October 2026, by a Bank B deposit of $210.40, 2 business days after the payout date.
Awaiting payout: Marketplace M order M-7768, Tuesday 22 September 2026, $28.00: cleared Thursday 15 October 2026, by a sale line in payout MP-M-0415.

**8. FIGURES FOR THE ENTRIES, to be posted by the bookkeeper after the owner approves**

Processor P: gross sales $630.00; refunds −$40.00; chargebacks −$58.00; transaction fees −$39.64; advertising $0.00; adjustments $0.00; reserve $0.00; paid out $492.36, of which in the bank $356.78 and in transit $135.58.
Marketplace M: gross sales $208.00; refunds −$60.00; chargebacks $0.00; transaction fees −$48.12; advertising −$22.50; adjustments $0.00; reserve $0.00; paid out $77.38, of which in the bank $77.38 and in transit $0.00.
Not to be posted until confirmed: difference 1, the $61.96 deposit; difference 2, order K-2107, until it is known which payout carried it.

**9. FEE DIFFERENCES, for the owner to decide whether to raise**

Processor P: K-2103, PO-P-1007: charged $1.40, rate gives $1.15, difference $0.25. Rate from the published pricing page, as read on 1 March 2026. Total $0.25.
Marketplace M: M-7794, MP-M-0415: charged $13.44, rate gives $10.08, difference $3.36. Rate from the rate card in the seller agreement, dated 1 January 2026. Total $3.36.

**10. COVERAGE**

Inputs used: settings; fee schedule; payouts list payouts-oct-2026.csv (4 payouts); Processor P line export (10 lines); Marketplace M line export (7 lines); order export orders-oct-2026.csv (16 orders); Bank B statement export, 1 to 31 October 2026 (8 rows); last month's open items (2).
Inputs missing: none.
Not checked: the Marketplace M advertising charge of $22.50, which no rate covers (its campaign settings were not supplied); the lines of last month's payout PO-P-0930, which were not supplied, so it was not footed and its fees were not checked; the 1 other credit on the statement, left to the bank reconciliation.

Prepared for the owner. Nothing has been posted, paid, raised with a channel or sent.
