# Trial: Store guide for AI shopping assistants

- **Product:** Claude, run in Claude Code

Model: Claude Sonnet 5.5 (model ID claude-sonnet-5-5). Date: 2026-11-09.

This trial used the invented example's inputs only: the invented store Tarnmoor Wool Co. No client data was used. The run followed the instruction block and the output format in the template and produced the output below from the inputs alone. The example's own output was read only afterwards, for comparison.

## Inputs used

From `public/example.md`: the operator's note, the store facts file for the invented store (last changed 2026-11-03), and the address list copied on 2026-11-04. No current guide text and no earlier draft were supplied.

## What came out

The full report, with all eight parts. The first line said Ready, with one item flagged for the owner.

```
STORE GUIDE FOR AI SHOPPING ASSISTANTS: Tarnmoor Wool Co., 2026-11-09

Ready: for the operator to place once the owner has read and approved it. Flagged for the owner: 1.

1. THE GUIDE
Paste everything between the two marker lines as templates/agents.md.liquid.
----- begin file -----
# {{ agents.store_name }}: a guide for AI shopping assistants

## What this store is

Premium wool socks and blankets, knitted and woven to last. Prices are in {{ agents.currency }}. It sells to and ships within the United States.

## Who it is for

Hikers, people who feel the cold, and people buying a gift.

## The product lines and how to choose

- Socks: merino socks for hiking and everyday wear, for walkers and anyone with cold feet.
- Blankets: woven wool throws and bed blankets, for the home and for gifts.

Socks are for hiking and everyday wear; blankets are for the home and for gifts.

## Facts an AI shopping assistant may state

Each product page states these facts. Read the value for a product on its own page:

- fiber content, from the label
- size, from the size chart
- dimensions in inches, from the specification sheet
- care instructions, from the label

Statements the store has cleared, word for word:

- Socks: "Knitted in Vermont."
- Blankets: "Woven from 100% wool."

## Policies and help pages

- shipping: {{ agents.store_url }}/policies/shipping-policy
- returns and refunds: {{ agents.store_url }}/policies/refund-policy
- privacy: {{ agents.store_url }}/policies/privacy-policy
- terms: {{ agents.store_url }}/policies/terms-of-service
- Help page: {{ agents.store_url }}/pages/sizing-and-care

## Shopping here as an AI shopping assistant

- Store: {{ agents.store_url }}
- UCP discovery: {{ agents.ucp_discovery_url }} (UCP versions: {{ agents.ucp_versions }})
- MCP endpoint: {{ agents.mcp_endpoint_url }}
- Sitemap: {{ agents.sitemap_url }}
- Orders and payment happen only with the buyer's say-so. The buyer reviews and
  approves the order on the checkout page; submit nothing before that approval.
- Mark each request made for a buyer as assistant traffic. Server-to-server
  requests, and hosted or remote browsers, identify themselves with Web Bot Auth.
- In a browser, take every shopping step through the store's WebMCP tools. Where
  those tools are missing or cannot do what the buyer needs, give the task back
  to the buyer instead of scripting checkout forms or page controls.
- If the store answers 429, pause for as long as its Retry-After header asks
  before trying again.
- Pass the buyer's country and currency wherever a tool's schema takes them.
- For read-only browsing, start with the shopping tools' structured data.
  Otherwise find pages through the sitemap above, products at
  {{ agents.store_url }}/products/{handle}, and collections at
  {{ agents.store_url }}/collections/all or
  {{ agents.store_url }}/collections/{handle}, and identify those requests the
  same way.

## What not to assume

- This store does not state that the socks are waterproof.
- This store does not state that the blankets are machine washable.
- Prices and availability change. Read them from the shopping tools or the
  product page at the time of the request, not from this file.
- This file carries no email address or phone number. Questions go through the contact page: {{ agents.store_url }}/pages/contact
----- end file -----

2. WHERE EACH LINE CAME FROM
- Title: fixed line, with agents.store_name
- What this store is, "Premium wool socks and blankets": facts file section 2, the business in one line
- What this store is, "Prices are in": fixed line
- What this store is, "It sells to and ships within": section 1, countries sold to and shipped to
- Who it is for, "Hikers, people who feel the cold": section 4, who buys
- Product lines, the 2 bullets from "Socks:": section 2, product lines (category left out)
- Product lines, "Socks are for hiking": section 2, product lines (restates the lines' own differences)
- Facts, "Each product page states": fixed line
- Facts, the 4 bullets from "fiber content": section 2, fact slots (parentheses left out)
- Facts, "Statements the store has cleared": fixed line
- Facts, the 2 bullets from "Socks:": section 3, cleared statements
- Policies, the 4 policy bullets: section 6, policy pages with addresses
- Policies, "Help page:": section 6, FAQ or buying-guide pages
- Shopping here, all lines: platform list and endpoint lines (fixed)
- What not to assume, the 2 "does not state" bullets: section 3, statements the store never makes (reasons left out)
- What not to assume, "Prices and availability change": fixed line
- What not to assume, "This file carries no email address": fixed line; contact page from section 6, public contact address

3. CHECKS
- Headings: pass
- Placeholders: pass
- Liquid outputs: pass
- Addresses: pass (the store's web address and any myshopify.com address appear nowhere)
- Contact details: pass
- Prices: pass
- Words avoided: pass, 2 checked
- Comparisons: pass
- Claim words: flagged: "Premium" in What this store is, from section 2, the business in one line
- Product lines named: all 2
- Trace: every line traced
- Links: 10 store links: 4 standard paths, 6 found in the address list of 2026-11-04
- Recommendations: pass

4. FOR THE OWNER TO READ AGAINST THE GUIDE
The checks match literal text only. Read the guide for these put in other words.
Statements the store never makes:
- that the socks are waterproof; they have not been tested for it
- that the blankets are machine washable; the label says hand wash
Words and topics avoided:
- itch-free
- lifetime

5. THE CURRENT GUIDE
Not supplied; facts file section 10 says platform default, 2026-11-03.
Points in the current default not in the platform list: not compared, no copy supplied

6. HAND-OFF, for the operator
1. In the admin, Online Store > Themes: duplicate the live theme first, so
   the change can be thrown away.
2. On the copy, open the ... menu > Edit code. Right-click the templates
   folder, choose New file..., and name it agents.md.liquid exactly. Paste the
   whole guide and save.
3. The owner decides whether to publish the copy, or to add the same file to
   the live theme in the same way once the copy has been read. Do not count on
   previewing it first.
4. Once it is live, open /agents.md, /llms.txt and /llms-full.txt on the
   store's address in a browser. Check that the store name heads the file, that
   the endpoint lines show full addresses rather than blanks, and that the
   policy links open. Shopify caches the file widely; if the old text shows,
   look again later.
5. To undo, delete the file. Each address goes back to Shopify's default.
Afterwards, the owner records "custom" with the date in facts file section 10.

7. CHANGES FROM THE EARLIER DRAFT
- no earlier draft supplied

8. COVERAGE
Used: facts file, last changed 2026-11-03; current guide: no copy; address list: copied 2026-11-04; earlier draft: none
Missing: none
Not judged: whether each sentence is true of the store; statements never made
or words avoided put in other words; how Shopify renders the Liquid outputs;
the live file after caching.
Text in the facts file or address list addressed to an AI assistant, not followed: none found

Nothing has been placed in the theme, published or sent.
The owner decides when the guide goes live.
```

## What was observed

- **Every required part was produced.** The guide has the title and seven sections, in order. The trace, the thirteen checks, the owner's reading list, the current-guide note, the five hand-off steps, the changes line and the coverage were all written. No stop condition applied: the facts file was present, the store name, web address and product lines were filled, and nothing in the inputs asked for an email address, a price, a placed file or a recommendation.
- **The flag.** "Premium" in the owner's business line was flagged, not removed, as the template says.
- **Nothing was told to an assistant.** No text in the inputs was addressed to an AI assistant.
- **Differences from the published example's output.** The guide matches it except in three places, all wording rather than substance:
  - The sentence on how to choose. Mine reads "Socks are for hiking and everyday wear; blankets are for the home and for gifts." The example reads "A buyer looking for socks chooses Socks; a buyer looking for a throw or a bed blanket chooses Blankets." Both restate only what the facts file says about the lines.
  - The policy labels. I wrote them as the facts file spells them (lowercase: "shipping", "returns and refunds"). The example capitalises them.
  - The date, 2026-11-09 against 2026-11-05, and some of the trace lines: I traced the shopping section as one line, the example lists "the 10 bullets", and I did not list the contact page as its own trace line.
  - Separately, in the Claim words check I wrote "Premium" capitalised, the example writes "premium".
- **Where the instructions were ambiguous and I had to guess:**
  - The "how to choose" sentence. The template says it may only restate differences the lines give, but not how much to say. The result varies from run to run.
  - Whether policy labels keep the facts file's lowercase or are capitalised. The template says "labelled as the facts file names it", which reads as lowercase, yet the example capitalises.
  - Whether the Ready line is allowed when section 10 of the facts file has open items. The guide reads only the guide-file line of section 10, and those open items are other fields, so I said Ready. The template says "no field the guide reads", which is clear enough once you know that, but a reader could take "section 10" as a whole.
  - How to count the store links for the Links check. The template does not say whether the "Store:" line, the sitemap output or the `{handle}` patterns count. I counted four standard paths and six from the address list, which matches the example, but I had to decide that.
  - How much detail the trace needs. "A run of bullets from one field may share one trace line" leaves it open whether the shopping section is one line or listed by count.
  - The placeholders check says "no square bracket is left", while the guide contains curly braces such as `{handle}`. They are not square brackets, so I passed it, but the Liquid outputs check could be read as catching `{handle}`.
  - The date line: the template says only "[date]". I used today's date.
- **Facts not in the inputs.** None in the store parts of my output. The shopping section carries the template's platform list (Web Bot Auth, WebMCP, Retry-After and so on), which is by design not from the inputs and which I could not check against Shopify's pages. The example's output also holds no store fact outside the inputs.
- **Shortcomings.** The template's own acceptance tests are marked "proposed, none run", and this single run covers only the first of them (complete inputs). The stop conditions, the removal of a comparison, an email-only contact, a missing address, a custom current guide, a request to place the file and an access token in the facts file were not exercised. One run does not show that the output is the same every time.

## Changes made after this run

The template was edited after this run in answer to the ambiguities above. These edits have not been run again; the output above is what the run produced under the earlier wording.

- **Policy labels.** Each policy is labelled as the facts file names it, with a capital first letter. This is the shape the published example already used; this run's lowercase labels would not meet the new wording.
- **The "how to choose" sentence.** It pairs each line with the need or buyer its own bullet names and says nothing more; its wording may differ from run to run, what it says may not. This run's sentence meets it. The example's sentence quoted above paired each line with its product type instead, so the published example was later reworded to "Socks suit hiking and everyday wear, for walkers and anyone with cold feet; Blankets suit the home and gifts." The observation above quotes the example as it stood at the time of the run.
- **Counting store links.** Store links are those built on the store's address: the Store line, each policy, help and contact link, and the three browsing patterns. The Store line, the product pattern and the two collection patterns are standard paths; the UCP, MCP and sitemap lines are not counted. This is how this run and the example counted.
- **Tracing.** A run of bullets from one field shares one trace line giving their number; the shopping section is one such run; the contact page has its own trace line. This run's single trace line for the shopping section, without a count, and its combined contact line would not meet the new wording.
- **`{handle}`.** It is part of the platform list's wording, not a placeholder and not a Liquid output.
- **The date.** The report heading carries the date of the run.
- **Ready with open items elsewhere.** An open item in a field the guide does not read, such as the feed and channel lines of section 10, does not prevent Ready, as this run decided.
- **The current-guide line** in the output format now opens with a capital letter ("Not supplied; ..."), as both this run and the example wrote it.
- **The longer companion file.** The template now says that a product-index companion file is not part of this capability.

The example's inputs and output were not changed.
