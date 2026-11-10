# Chargeback response pack: tried on its invented example

- **Product:** Claude, run in Claude Code
- **Model:** Claude Opus 5.5 (model ID claude-opus-5-5)
- **Date:** 2026-11-10

The template was run three times on 10 November 2026 on its invented example (Tidevale Teaware, dispute DP-20931), and no client data was used in any run. The template and the example were revised after the first run. This record gives a short account of the first run, the second run in full, and a third, blind run made after small wording edits to the pasted instructions.

## The first run

The first run used Claude Sonnet 5.5 on the template as first written. That model had not written the template, and it read the example's own output only after producing its own. Its figures, dates, weekdays, reason family, evidence count, history, flags and ratio were the same as the example's.

It found that the example's draft response did not hold to the template's own rule in three places. The response said the parcel "was shipped to the address entered at checkout", which no input backs, since the order export has only a Shipping Address column. Its sentence that no further message was on record, and its sentence giving the dispute's opening date, had no exhibit after them. It called the shipping policy "in force on the order date" without giving the policy's date. That run also put "Inputs missing: none" where the example named the delivery photo. It met seven points the template left open: whether a carrier match on town and postcode only is [found]; how to mark "delivery photo or signature" when neither is supplied but a photo exists on request; whether a dispute whose status is "Evidence submitted" still needs a response; whether a policy dated before the order is in force; whether a later dispute counts in the customer's look-back; whether the word limit covers the exhibit list; and how "Prepared from" differs from "Inputs used".

Changes made after the first run:

- The example's draft response now says "shipped to the shipping address on the order", cites the support thread for the sentence about no further message, leaves out the opening date, and gives the policy's date instead of calling it in force. Its evidence, history and exhibit lines are written as plain lines, matching the output format.
- The procedure and the pasted instructions settle each of the seven open points in one sentence, and the output format says that a missing evidence file is listed under "Inputs missing".
- The pasted instructions gained details the procedure had and they lacked: flagging an order already refunded in full, "to [today's date]" for a month not yet over, adding the dispute to the count if the log lacks it, the "Not calculated" wording, and asking whether customer contact exists when none is supplied.

## The second run

The inputs were the seven in `public/example.md` (settings, dispute notice, order export, carrier tracking record, support thread, shipping policy, disputes log). The model followed the revised instruction block and output format in `member/template.md`. This run was made by the same model session that made the revisions, after reading the first run's record and the example's output, so it was not blind. Its agreement with the example shows less than the first run's agreement did.

### What came out

A complete eight-part pack, in the fixed format. Its main points:

- Deadline: respond by Monday 16 November 2026 (13 days left); submit by Friday 13 November 2026; no URGENT line.
- Dispute: matched by payment reference PAY-88213 to order TV-4418; $100.00 disputed against a $100.00 order total with no refund, so "Matches". Family: not received. Stage: chargeback. Fee $15.00.
- Evidence: 5 of 6 found. The carrier record was marked [found], with the town and postcode agreeing and the street under "Not checked". The delivery photo or signature was marked [missing]: signature not required, photo available on request from Carrier N. The shipping policy was marked [found] as in force on the order date, being dated 1 September 2026 with no later version supplied.
- History: two earlier orders (TV-3102, TV-3655), neither disputed, same shipping address and IP address; no earlier disputes from this customer in 12 months. Kept out of the response, because the family is not "not authorised".
- Decision facts: $100.00 plus the $15.00 fee, no flags, nothing recommended.
- Draft response: 170 words, counting the response text only, within the 250-word limit. Every sentence is followed by its exhibit: E1 order record, E2 carrier record, E3 support thread, E4 shipping policy, numbered in order of first citation. The policy is given by its date. The draft did not mention the missing photo, which was listed to add before Friday 13 November 2026 as E5.
- Ratio for October 2026: 3 disputes (DP-20114, DP-20702, DP-20931) ÷ 412 card payments = 0.73%, at or above the 0.65% warning level and below the 1.00% limit. Other dispute needing a response: DP-21010. DP-20702, with status "Evidence submitted", was not counted as needing one.
- Coverage: "Inputs used" repeated the header's "Prepared from" list; "Inputs missing" named the delivery photo from Carrier N.
- Closing line: draft for the owner; nothing submitted, accepted, refunded or sent to anyone.

### What was observed

- Every required part was produced. No stop condition applied. Each point the revisions settled was applied without a further choice.
- The numbers, dates, weekdays, family, evidence count, history, flags and ratio were the same as the example's and the first run's.
- Differences from the example's output:
  - The run named "records the reason needs" as not supplied, in "Prepared from" and in "Inputs missing", adding that none is needed for this family. The example does not name it. The template asked for those records only for return, cancellation, duplicate-charge and subscription disputes, and did not say whether an input the family does not need is named as not supplied. After this run the template was edited to say it is not named, which matches the example. That edit has not been run again. (The third run, below, was made after it.)
  - The run's response was shorter (170 words against the example's 182) and kept to one fact per sentence. Its exhibit descriptions and evidence lines were worded more briefly. No fact differed.
- Shortcomings of this trial: two runs on one invented example, the recorded one by the model session that revised the template. It does not show how the template behaves with a messy real export, a header that does not match, or inputs that try to instruct the assistant; the acceptance tests for those cases have not been run. No other AI product was tried. (The third run, below, was blind.)

## The third run

After an independent review, the pasted instructions were edited in three small places, with no change to the output format or the example: step 1 now limits URGENT to "after the submit-by date and on or before the due date", as the procedure does; step 2 now flags a partial or exceeding amount as "amount differs" and a full refund as "refunded already"; and step 6 names the four flags. The procedure's step 4 gained the same flags, and its step 8 now writes "refunded already" as the output format does.

The third run was then made in a fresh session of the same model with no other context: its only instructions were the instruction block and the output format from `member/template.md` as they now stand, and its only input was the seven inputs from `public/example.md`. It had not seen the example's output, the template's procedure or this record, so it was blind.

### What came out

A complete eight-part pack, in the fixed format, preceded by one line outside the format: the run noted that it had used today's date from the settings (Tuesday 3 November 2026) although the computer's clock read 10 November 2026, and said what the deadline would be if the clock's date were the real one. Its main points:

- Deadline, match, amount, family, stage and fee: the same as the example's (13 days left, submit by Friday 13 November 2026, no URGENT line; matched by payment reference; "Matches"; not received; chargeback; $15.00).
- Evidence: 5 of 6 found, the same items marked the same way as in the example, the delivery photo marked [missing] with Carrier N as its source.
- History: the same two earlier orders, neither disputed; it listed the same billing address and the same carrier as matching details as well as the shipping address and IP address. No earlier disputes. Kept out of the response.
- Decision facts: $100.00 plus the $15.00 fee, "Flags: none", nothing recommended.
- Draft response: 239 words, counting the response text only, within the 250-word limit, citing E1 to E4 in order of first citation, giving the policy by its date, and listing the delivery photo to add as E5. It added the carrier's collection and out-for-delivery scans, wrote in the store's voice ("we", "our") and called the customer "the cardholder".
- Ratio: 3 disputes ÷ 412 card payments = 0.73%, at or above the 0.65% warning level and below the 1.00% limit; DP-21010 as the other dispute needing a response, DP-20702 not counted.
- Coverage: "Inputs used" repeated "Prepared from"; "Inputs missing" named only the delivery photo. "Records the reason needs" was not named anywhere, which is what the edit after the second run asked for.
- Closing line: draft for the owner; nothing submitted, accepted, refunded or sent to anyone.

### What was observed

- The numbers, dates, weekdays, family, evidence count, history, flags and ratio were the same as the example's and the two earlier runs'.
- Differences from the example's output:
  - The line before the pack about the computer's clock is outside the output format, which says to use the format exactly. It came from the run's own environment, not from the inputs; the pack itself used the settings' date throughout.
  - The draft response was longer (239 words against 182) and more detailed, but stayed within the limit and every sentence had an exhibit. One sentence cites two exhibits, (E1, E2).
  - "Not checked" listed seven points against the example's two, adding what the photo shows, whether a carrier claim was opened, the card network, orders under other emails, the processor's limit as the owner's reading, and the clock's date. Each was a fair point the inputs leave open.
  - Small wording differences: "Product not received (no code shown)" and "0 (none)".
- Shortcomings of this trial: three runs on one invented example, all by Claude models in Claude. It still does not show how the template behaves with a messy real export, a header that does not match, or inputs that try to instruct the assistant; the acceptance tests for those cases have not been run. No other AI product was tried.
