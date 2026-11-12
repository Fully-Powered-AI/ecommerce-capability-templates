# Store guide for AI shopping assistants: an invented example

*Illustrative example with invented data.* The store, its web address, its products, its pages and its roles below are all invented. Tarnmoor Wool Co. is an invented online store on Shopify selling wool socks and blankets in the United States, run by an owner and an operator. First come the inputs the operator supplied, in full, then the report the workflow template returned on 5 November 2026.

## The inputs

### 1. The operator's note

```
Please draft our guide for AI shopping assistants. I don't have a copy
of what /agents.md shows today; the facts file says it is still
Shopify's default. The address list is attached.
```

### 2. The store facts file, approved by the owner

```
STORE FACTS FILE: Tarnmoor Wool Co.

Last changed 2026-11-03. Every store workflow template reads this file first.
Marks: [owner] the person said it; [read] read from a supplied file and confirmed;
[default] a default the person accepted; [open] decide later, listed in the report.
A blank value means not yet asked. Headings and field wording never change.

## 1. The store
- Store name: Tarnmoor Wool Co. [owner]
- Web address: https://www.tarnmoor-wool.example [read]
- Platform and plan, as the admin shows them, with the date: Shopify, Basic, 2026-11-03 [read]
- Store currency: USD [read]
- Countries sold to and shipped to: the United States [owner]
- Other places the products are sold, one per indented line: none [owner]

## 2. What it sells
- The business in one line, in the person's own words: Premium wool socks and blankets, knitted and woven to last [owner]
- Product lines, one per indented line:
  - Socks: merino socks for hiking and everyday wear, for walkers and anyone with cold feet; category Apparel & Accessories > Clothing > Underwear & Socks > Socks [owner]
  - Blankets: woven wool throws and bed blankets, for the home and for gifts; category Home & Garden > Linens & Bedding > Bedding > Blankets [owner]
- Search words, one per indented line:
  - merino hiking socks [owner]
  - warm wool socks [owner]
  - wool throw blanket [owner]
- Fact slots, one per indented line:
  - fiber content (merino, wool, nylon), from the label [owner]
  - size (S, M, L, XL), from the size chart [owner]
  - dimensions in inches, from the specification sheet [owner]
  - care instructions (machine wash cold, hand wash), from the label [owner]

## 3. Statements and words
- Cleared statements, verbatim, with the product or line; anything else is asked:
  - Socks: "Knitted in Vermont." [owner]
  - Blankets: "Woven from 100% wool." [owner]
- Statements the store never makes, with the reason:
  - that the socks are waterproof; they have not been tested for it [owner]
  - that the blankets are machine washable; the label says hand wash [owner]
- Words and topics the brand avoids:
  - itch-free [owner]
  - lifetime [owner]
- Comparisons with named competitors allowed [default no]: no [default]
- Who clears a new statement (role) [default owner]: owner [default]

## 4. Buyers and their questions
- Who buys, in plain words: hikers, people who feel the cold, and people buying a gift [owner]
- Questions buyers ask before buying, five to ten, in the buyer's words:
  - are these ok for long hikes [owner]
  - what size sock if im a mens 10 [owner]
  - can the blanket go in the washer [owner]
  - how big is the throw [owner]
  - do you ship to canada [owner]
- Assistant prompts (optional), each question as typed to an assistant, no brand:
- Where buyers hear about the store today:
  - search [owner]
  - word of mouth [owner]

## 5. Apps and tools
- Reviews app, and whether it puts ratings into the product data: none [owner]
- Email and SMS apps: Shopify Email [owner]
- Other apps that change the storefront or product data: none [owner]
- Analytics in use: Shopify's own reports [owner]
- The AI tool the person uses, and whether it is connected to the store: Claude, not connected [owner]

## 6. Pages, policies and contact
- Policy pages with addresses (shipping, returns and refunds, privacy, terms):
  - shipping: https://www.tarnmoor-wool.example/policies/shipping-policy [read]
  - returns and refunds: https://www.tarnmoor-wool.example/policies/refund-policy [read]
  - privacy: https://www.tarnmoor-wool.example/policies/privacy-policy [read]
  - terms: https://www.tarnmoor-wool.example/policies/terms-of-service [read]
- FAQ or buying-guide pages:
  - https://www.tarnmoor-wool.example/pages/sizing-and-care [read]
- Public contact address, the role that reads it, and the reply-time target: the contact form at https://www.tarnmoor-wool.example/pages/contact, read by support, two business days [owner]
- Popups, age checks or password pages, with where they show: none [read]

## 7. People and roles
Roles, never names.
| role | does | approves |
| owner | sets the rules, clears statements | this file, statements, data changes |
| operator | runs the work, prepares exports, publishes files | drafts for the owner |
| support | answers buyers' email | nothing |
| finance | reads the money reports | nothing |
- Who approves a change to product data before it is applied [default owner]: owner [default]
- Who publishes files onto the site [default operator]: operator [default]

## 8. Access
- How later workflow templates reach the store's data (connection, exports, public): exports, public [owner]
- Connection access level approved, and the staff role it acts through: none, no connection [owner]
- Exports the person can produce, and how often: products, monthly [owner]

## 9. Numbers and rhythms
- Visibility review [default quarterly]: quarterly [default]
- Answer check [default monthly]: monthly [default]
- Product pages sampled per review [default 5]: 5 [default]
- Every product image has alt text [default yes]: yes [default]
- Low-stock units per variant [default 5]: 5 [default]
- Late-order days [default 3]: 3 [default]

## 10. AI shopping channels
- Product feed status for AI shopping, as the admin shows it, with the date: not checked [open]
- AI shopping channels switched on, as the admin shows them, with dates: not checked [open]
- Guide file for AI assistants (platform default or custom), date of last change: platform default, 2026-11-03 [read]
- AI crawler access (platform default or restricted), with the date: platform default, 2026-11-03 [read]

## 11. Decisions log
Dated lines, newest last: date, role, what was decided, section.
- 2026-11-03, owner, store facts file set up; 2 open items (section 10), all sections
```

### 3. The store's page addresses, copied from the sitemap and footer on 4 November 2026

```
https://www.tarnmoor-wool.example/
https://www.tarnmoor-wool.example/collections/all
https://www.tarnmoor-wool.example/collections/socks
https://www.tarnmoor-wool.example/collections/blankets
https://www.tarnmoor-wool.example/products/trail-merino-crew-sock
https://www.tarnmoor-wool.example/products/everyday-merino-sock
https://www.tarnmoor-wool.example/products/fell-wool-throw
https://www.tarnmoor-wool.example/pages/about
https://www.tarnmoor-wool.example/pages/sizing-and-care
https://www.tarnmoor-wool.example/pages/contact
https://www.tarnmoor-wool.example/policies/shipping-policy
https://www.tarnmoor-wool.example/policies/refund-policy
https://www.tarnmoor-wool.example/policies/privacy-policy
https://www.tarnmoor-wool.example/policies/terms-of-service
```

No current guide text and no earlier draft were supplied.

## The report the workflow template returned

```
STORE GUIDE FOR AI SHOPPING ASSISTANTS: Tarnmoor Wool Co., 2026-11-05

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

Socks suit hiking and everyday wear, for walkers and anyone with cold feet; Blankets suit the home and gifts.

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

- Shipping: {{ agents.store_url }}/policies/shipping-policy
- Returns and refunds: {{ agents.store_url }}/policies/refund-policy
- Privacy: {{ agents.store_url }}/policies/privacy-policy
- Terms: {{ agents.store_url }}/policies/terms-of-service
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
- Title, "# {{ agents.store_name }}": fixed line
- What this store is, "Premium wool socks": facts file section 2, the business in one line
- What this store is, "Prices are in": fixed line
- What this store is, "It sells to and ships within": facts file section 1, countries sold to and shipped to
- Who it is for, "Hikers, people who feel the cold": facts file section 4, who buys
- The product lines and how to choose, the 2 bullets from "Socks: merino socks": facts file section 2, product lines
- The product lines and how to choose, "Socks suit hiking": facts file section 2, product lines
- Facts an AI shopping assistant may state, "Each product page states": fixed line
- Facts an AI shopping assistant may state, the 4 bullets from "fiber content": facts file section 2, fact slots
- Facts an AI shopping assistant may state, "Statements the store has cleared": fixed line
- Facts an AI shopping assistant may state, the 2 bullets from "Socks:": facts file section 3, cleared statements
- Policies and help pages, the 4 bullets from "Shipping:": facts file section 6, policy pages
- Policies and help pages, "Help page:": facts file section 6, FAQ or buying-guide pages
- Shopping here as an AI shopping assistant, the 10 bullets from "Store:": platform list
- What not to assume, the 2 bullets from "This store does not state": facts file section 3, statements the store never makes
- What not to assume, "Prices and availability change": fixed line
- What not to assume, "This file carries no email address": fixed line
- What not to assume, "Questions go through the contact page": facts file section 6, public contact address

3. CHECKS
- Headings: pass
- Placeholders: pass
- Liquid outputs: pass
- Addresses: pass
- Contact details: pass
- Prices: pass
- Words avoided: pass, 2 checked
- Comparisons: pass
- Claim words: flagged: "premium" in What this store is, from facts file section 2, the business in one line
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
1. In the admin, Online Store > Themes: duplicate the live theme first, so the
   change can be thrown away.
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
no earlier draft supplied

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

The one flag is the owner's call: "Premium" is the owner's own word in the facts file, so the guide keeps it until the owner rewords or clears it there. The two open items in section 10 of the facts file do not hold the guide back, because the guide reads only the guide file line of that section, which is settled.
