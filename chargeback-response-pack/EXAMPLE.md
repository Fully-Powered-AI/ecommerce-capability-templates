# Chargeback response pack: an invented example

*Illustrative example with invented data.* Tidevale Teaware, its customers, its payment processor (called Processor P here), its carrier (called Carrier N), the addresses, the order and dispute numbers and every figure below are invented. Tidevale Teaware is an online shop selling teapots and loose-leaf tea, run by an owner with a part-time bookkeeper. The addresses and IP addresses use ranges set aside for examples. First come the inputs the bookkeeper supplied, in full, then the pack the workflow template returned.

## The inputs

### 1. Settings

```
Store: Tidevale Teaware
Today: Tuesday 3 November 2026
Prepared by: the bookkeeper
Decides and submits: the owner
Payment processor: Processor P
Submit-by buffer: 3 days before the due date
Response length limit: 250 words
Warning level: 0.65% (the owner's own)
Processor's limit: 1.00% (from Processor P's terms, as the owner reads them)
Look-back for earlier disputes: 12 months
Card payments in October 2026 (Processor P's monthly report): 412
```

### 2. The dispute notice (pasted from Processor P's dispute page)

```
Processor P · Disputes · DP-20931
Status: Needs response
Amount: $100.00 USD
Reason: Product not received
Opened: 28 Oct 2026
Respond by: 16 Nov 2026
Payment: PAY-88213, 13 Oct 2026
Customer: customer.r@example.com
Cardholder's statement (from the card issuer): "Package never arrived."
Dispute fee: $15.00
```

### 3. The order export (orders-customer-r.csv, filtered by the customer's email)

```
Order ID,Order Date,Customer Email,Billing Address,Shipping Address,Items,Order Total,Refunded Amount,Currency,Payment Reference,Fulfilled Date,Carrier,Tracking Number,Customer IP
TV-3102,2026-06-14,customer.r@example.com,"12 Sample Lane, Example City, EX 00000","12 Sample Lane, Example City, EX 00000","Breakfast blend tin x1 18.00; Tea strainer x1 22.00; Shipping 6.00",46.00,0.00,USD,PAY-71540,2026-06-15,Carrier N,N7731 0039 2207,203.0.113.24
TV-3655,2026-08-30,customer.r@example.com,"12 Sample Lane, Example City, EX 00000","12 Sample Lane, Example City, EX 00000","Green tea pouch x2 26.00; Shipping 6.00",32.00,0.00,USD,PAY-79022,2026-08-31,Carrier N,N7731 0040 8815,203.0.113.24
TV-4418,2026-10-13,customer.r@example.com,"12 Sample Lane, Example City, EX 00000","12 Sample Lane, Example City, EX 00000","Stoneware teapot 1 l x1 68.00; Loose-leaf sampler x1 24.00; Shipping 8.00",100.00,0.00,USD,PAY-88213,2026-10-14,Carrier N,N7731 0042 9918,203.0.113.24
```

### 4. Carrier N's tracking record (copied from its tracking page)

```
Tracking number N7731 0042 9918
14 Oct 2026 16:05  Collected            Riverside depot
15 Oct 2026 07:40  Out for delivery     Example City
15 Oct 2026 13:12  Delivered, left at front door   Example City EX 00000
Proof of delivery: photo taken at delivery, available on request
Signature: not required
```

### 5. Customer contact (the support inbox thread for TV-4418)

```
Mon 19 Oct 2026 09:14, from customer.r@example.com:
  Hi, my tracking says delivered but I can't find the box. Order TV-4418.

Mon 19 Oct 2026 11:02, from Tidevale Teaware support:
  Sorry to hear that. The carrier shows it was left at your front door on
  15 October at 13:12. Could you check with neighbours or anyone else at
  the address? If it hasn't turned up by Friday 23 October, reply and we
  will open a claim with the carrier.

No further messages in the thread.
```

### 6. The shipping policy

```
Shipping policy (dated 1 September 2026)
Orders ship within two business days. Every order is sent with tracking.
If your tracking says delivered and the parcel has not arrived, tell us
within 14 days of the delivery date and we will open a claim with the
carrier.
```

### 7. The disputes log (the bookkeeper's sheet)

```
Dispute ID,Opened,Order ID,Customer Email,Reason,Amount,Status,Outcome
DP-19807,2026-09-03,TV-2950,customer.k@example.com,Fraudulent,54.00,Closed,Won
DP-20114,2026-10-06,TV-3988,customer.m@example.com,Product unacceptable,72.00,Closed,Accepted
DP-20702,2026-10-21,TV-4290,customer.t@example.com,Fraudulent,118.00,Evidence submitted,
DP-20931,2026-10-28,TV-4418,customer.r@example.com,Product not received,100.00,Needs response,
DP-21010,2026-11-02,TV-4466,customer.w@example.com,Duplicate,36.00,Needs response,
```

## The output

**CHARGEBACK RESPONSE PACK: Tidevale Teaware, dispute DP-20931**

For: the owner. Prepared by: the bookkeeper. Prepared on Tuesday 3 November 2026.
Deadline: respond by Monday 16 November 2026 (13 days left). Submit by Friday 13 November 2026, 3 days before the due date.
Prepared from: dispute notice DP-20931; order export orders-customer-r.csv (3 orders); Carrier N tracking record N7731 0042 9918; support thread for TV-4418; shipping policy dated 1 September 2026; disputes log (5 disputes); settings, with October card payments.

**1. THE DISPUTE**

Processor: Processor P. Card network: not shown on the notice. Stage: chargeback.
Reason as stated: Product not received. Reason family: not received.
Cardholder's statement: "Package never arrived."
Amount disputed: $100.00, USD. Order total less refunds: $100.00. Matches.
Opened: Wednesday 28 October 2026. Dispute fee: $15.00.

**2. THE ORDER**

Matched by: payment reference (PAY-88213).
TV-4418, placed Tuesday 13 October 2026. Items: stoneware teapot 1 l, $68.00; loose-leaf sampler, $24.00; shipping, $8.00. Total: $100.00. Refunded: none.
Ship to: 12 Sample Lane, Example City, EX 00000. Bill to: same as ship to.
Fulfilled: Wednesday 14 October 2026 by Carrier N, tracking N7731 0042 9918. Delivery: delivered, left at front door, Thursday 15 October 2026 at 13:12, Example City EX 00000.

**3. EVIDENCE THE REASON CALLS FOR: not received**

[found] Order record: TV-4418, 13 October 2026, stoneware teapot and loose-leaf sampler, $100.00, payment PAY-88213 (source: order export).
[found] Shipping address on the order: 12 Sample Lane, Example City, EX 00000 (source: order export).
[found] Carrier record of delivery, with date and place: delivered, left at front door, Example City EX 00000, Thursday 15 October 2026 at 13:12. The town and postcode agree with the shipping address (source: Carrier N tracking record).
[missing] Delivery photo or signature: no signature was required; the tracking record says a delivery photo is available on request. Ask Carrier N for the photo.
[found] Contact with the customer about the delivery: the customer's email of Monday 19 October 2026 saying the box could not be found, and the store's reply the same day giving the delivery details and offering a carrier claim if the parcel had not turned up by 23 October (source: support thread).
[found] Shipping policy in force on the order date: shipping policy dated 1 September 2026, before the order date, and no later version supplied (source: policy text).

Found: 5 of 6.

**4. THIS CUSTOMER'S HISTORY**

Earlier orders from customer.r@example.com:
TV-3102, Sunday 14 June 2026, $46.00, not disputed, same shipping address and IP address.
TV-3655, Sunday 30 August 2026, $32.00, not disputed, same shipping address and IP address.

Earlier disputes from this customer in the last 12 months: 0.

**5. FOR THE DECISION**

At stake: $100.00, plus a dispute fee of $15.00.
Evidence: 5 of 6 found. Missing: delivery photo, from Carrier N on request.
Flags: none.
This dispute is in October 2026's dispute count whatever is decided.
The owner decides whether to contest or accept. Nothing is recommended.

**6. DRAFT RESPONSE, for the owner to edit**

Tidevale Teaware: response to dispute DP-20931, payment PAY-88213, $100.00.

Order TV-4418 was placed on 13 October 2026 for a stoneware teapot and a loose-leaf sampler, $100.00 including $8.00 shipping, and was paid with payment PAY-88213 (E1). It was shipped to the shipping address on the order, 12 Sample Lane, Example City, EX 00000 (E1).

Carrier N collected the parcel on 14 October 2026 under tracking number N7731 0042 9918. It recorded the parcel as delivered and left at the front door in Example City, EX 00000, at 13:12 on 15 October 2026 (E2).

On 19 October 2026 the customer wrote that the tracking showed the parcel as delivered but the box could not be found. The store replied the same day with the delivery details and offered to open a claim with the carrier if the parcel had not turned up by 23 October (E3). No further message from the customer is on record (E3).

The store's shipping policy, dated 1 September 2026, asks customers to report a parcel marked delivered that has not arrived within 14 days of delivery, so that a claim can be opened with the carrier (E4).

Exhibits to attach:
E1 Order record for TV-4418: items, total, payment reference and shipping address (order export).
E2 Carrier N tracking record for N7731 0042 9918 (tracking record).
E3 Email thread of 19 October 2026 between the customer and the store (support thread).
E4 Shipping policy dated 1 September 2026 (policy text).

To add if obtained before Friday 13 November 2026: delivery photo from Carrier N, as E5.

**7. DISPUTE RATIO: October 2026**

3 disputes opened (DP-20114, DP-20702, DP-20931) ÷ 412 card payments = 0.73%.
Warning level 0.65%; processor's limit 1.00% (from the settings). At or above the warning level, below the limit.
Other disputes in the log needing a response: DP-21010.

**8. COVERAGE**

Inputs used: dispute notice DP-20931; order export orders-customer-r.csv (3 orders); Carrier N tracking record N7731 0042 9918; support thread for TV-4418; shipping policy dated 1 September 2026; disputes log (5 disputes); settings, with October card payments.
Inputs missing: delivery photo from Carrier N.
Not checked: the street address of the delivery, because the carrier record gives only the town and postcode; whether anyone at the address received the parcel.

Draft for the owner. Nothing has been submitted, accepted, refunded or sent to anyone.
