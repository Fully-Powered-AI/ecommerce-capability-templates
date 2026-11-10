# Store facts file: an invented example

*Illustrative example with invented data.* The store, its products, its web address, its apps and its people below are all invented. Larkfield Loose Leaf is an invented small online tea shop: an owner who blends and packs the tea and also runs the store day to day, a part-time helper who answers email, and a bookkeeper. First come the inputs, in full, then the file and the report the capability returned.

## The inputs

### 1. Store basics (typed by the owner from the store's admin, 2 November 2026)

```
Store name: Larkfield Loose Leaf
Web address: https://www.larkfield-loose-leaf.example
Platform and plan: Shopify, Basic plan
Currency: USD
Sells to and ships to: United States only
```

### 2. Product list export (exported 2 November 2026)

```
Handle,Title,Type,Tags,Product Category,Status
morning-assam,Morning Assam,Black tea,"black tea, breakfast","Food, Beverages & Tobacco > Beverages > Tea & Infusions",active
smoky-lapsang,Smoky Lapsang,Black tea,"black tea, smoked","Food, Beverages & Tobacco > Beverages > Tea & Infusions",active
spring-sencha,Spring Sencha,Green tea,green tea,"Food, Beverages & Tobacco > Beverages > Tea & Infusions",active
chamomile-meadow,Chamomile Meadow,Herbal tea,"herbal, caffeine-free","Food, Beverages & Tobacco > Beverages > Tea & Infusions",active
cast-iron-teapot,Cast Iron Teapot 0.8 L,Teaware,teapot,,active
winter-spice-sampler,Winter Spice Sampler,Herbal tea,"herbal, gift",,draft
```

### 3. Text from three product pages (copied by the owner, 2 November 2026)

```
https://www.larkfield-loose-leaf.example/products/morning-assam
A brisk, malty breakfast tea from a single estate in Assam, India. The best
breakfast tea you will ever taste. Packed in a resealable, home-compostable
pouch. 100 g, about 40 cups.

https://www.larkfield-loose-leaf.example/products/chamomile-meadow
Whole chamomile flowers, naturally caffeine free. Helps you sleep better.
50 g, about 25 cups.

https://www.larkfield-loose-leaf.example/products/cast-iron-teapot
Cast iron with an enamel lining. Stainless steel infuser included. Holds 0.8 L.
```

### 4. Links from the storefront footer (copied by the owner, 2 November 2026)

```
Shipping: https://www.larkfield-loose-leaf.example/policies/shipping-policy
Returns and refunds: https://www.larkfield-loose-leaf.example/policies/refund-policy
Privacy: https://www.larkfield-loose-leaf.example/policies/privacy-policy
Contact: hello@larkfield-loose-leaf.example
```

### 5. What the owner said (the conversation, 9 November 2026, in the order it ran)

```
What we sell
- Business in one line: "We blend and pack loose-leaf tea in small batches,
  and sell the teapots to brew it in."
- Lines: keep two. "Tea" for all the black, green and herbal teas in
  pouches, for people who brew loose-leaf tea at home; the category in the
  export is right. "Teaware" for the cast iron teapots, same people; I don't
  know its category, I'll copy it from the teapot in the admin later.
- Search words: loose leaf tea; breakfast tea; caffeine free herbal tea;
  cast iron teapot.
- What a careful buyer checks: caffeine, the pages say "caffeine free" or
  "caffeine-free", I know it; pouch weight in grams, "g", from the label;
  cups per pouch, "cups", I work it out; brewing temperature and time, the
  pages say "steep", "boiling", "just-boiled", I set it; ingredients, from
  the label; origin, the pages say "estate" and "grown in", from the
  supplier sheet; teapot capacity in liters, "L", from the spec sheet.

Buyers
- Who buys: "People who brew tea at home, mostly in the US, and gift buyers
  in November and December."
- Their questions, as they ask them:
  how much caffeine is in the assam?
  how many cups do i get out of one bag
  Can I steep the leaves twice?
  is the teapot ok on the stove?
  Do I need a strainer?
  whats the difference between the assam and the lapsang
- Assistant prompts, two of them:
  "How much caffeine is in Assam black tea compared with a cup of coffee?"
  "Can a cast iron teapot with an enamel lining go on a stovetop?"
- Where they hear about us: Instagram; the Saturday farmers market stall;
  search.

Statements, one by one
- "A brisk, malty breakfast tea from a single estate in Assam, India." Clear.
- "The best breakfast tea you will ever taste." Drop. Never say "best ever".
- "Packed in a resealable, home-compostable pouch." Reword to "Packed in a
  resealable pouch." The supplier hasn't confirmed compostable in writing.
- "100 g, about 40 cups." Clear.
- "Whole chamomile flowers, naturally caffeine free." Clear.
- "Helps you sleep better." Drop. We never claim sleep or health benefits;
  we can't back them up.
- "50 g, about 25 cups." Clear.
- "Cast iron with an enamel lining." Clear.
- "Stainless steel infuser included." Clear.
- "Holds 0.8 L." Clear.
- Words we avoid: "best ever"; "detox".
- Competitor comparisons: no, keep the default. Who clears: me, the owner.

The store, apps, pages, access
- Basics and footer links: all correct. Also sold: two cafés in town buy
  wholesale, no website.
- Reviews app: Starling Reviews. No idea whether the stars reach the product
  data; I'll check its settings.
- Email: Postbox Mail, newsletter only. No SMS.
- No other apps that change the store or the products.
- Analytics: the platform's built-in reports.
- AI tool: I use ChatGPT. It is not connected to the store.
- Terms page: we don't have one. No FAQ page.
- The helper (support) reads the contact email; we reply within two
  business days.
- Popups: a newsletter sign-up popup on the first visit, on every page.
- Access: exports and the public pages. No connection. I can export
  products and orders, monthly.

Roles
- I approve product data changes. I also act as operator, so I publish
  files onto the site.

Numbers
- All defaults fine except low stock: 10 units per variant, not 5.

AI shopping channels
- Haven't looked at any of these in the admin yet. I'll do it as owner.
```

## The output

```
STORE FACTS FILE: Larkfield Loose Leaf

Last changed 9 November 2026. Every store capability reads this file first.
Marks: [owner] the person said it; [read] read from a supplied file and confirmed;
[default] a default the person accepted; [open] decide later, listed in the report.
A blank value means not yet asked. Headings and field wording never change.

## 1. The store
- Store name: Larkfield Loose Leaf [read]
- Web address: https://www.larkfield-loose-leaf.example [read]
- Platform and plan, as the admin shows them, with the date: Shopify, Basic plan, 2 November 2026 [read]
- Store currency: USD [read]
- Countries sold to and shipped to: United States only [read]
- Other places the products are sold, one per indented line:
  - two cafés in town, wholesale, no address [owner]

## 2. What it sells
- The business in one line, in the person's own words: We blend and pack loose-leaf tea in small batches, and sell the teapots to brew it in. [owner]
- Product lines, one per indented line:
  - Tea: black, green and herbal teas in pouches, for people who brew loose-leaf tea at home; category Food, Beverages & Tobacco > Beverages > Tea & Infusions [owner]
  - Teaware: cast iron teapots, for the same people; category not set [open]
- Search words, one per indented line:
  - loose leaf tea [owner]
  - breakfast tea [owner]
  - caffeine free herbal tea [owner]
  - cast iron teapot [owner]
- Fact slots, one per indented line:
  - caffeine (caffeine free, caffeine-free), from the person [owner]
  - pouch weight in grams (g), from the label [owner]
  - cups per pouch (cups), from the person [owner]
  - brewing temperature and time (steep, boiling, just-boiled), from the person [owner]
  - ingredients, from the label [owner]
  - origin (estate, grown in), from the supplier sheet [owner]
  - teapot capacity in liters (L), from the specification sheet [owner]

## 3. Statements and words
- Cleared statements, verbatim, with the product or line; anything else is asked:
  - Morning Assam: "A brisk, malty breakfast tea from a single estate in Assam, India." [owner]
  - Morning Assam: "Packed in a resealable pouch." [owner]
  - Morning Assam: "100 g, about 40 cups." [owner]
  - Chamomile Meadow: "Whole chamomile flowers, naturally caffeine free." [owner]
  - Chamomile Meadow: "50 g, about 25 cups." [owner]
  - Cast Iron Teapot 0.8 L: "Cast iron with an enamel lining." [owner]
  - Cast Iron Teapot 0.8 L: "Stainless steel infuser included." [owner]
  - Cast Iron Teapot 0.8 L: "Holds 0.8 L." [owner]
- Statements the store never makes, with the reason:
  - any sleep or health benefit; the store cannot back such claims up [owner]
- Words and topics the brand avoids:
  - "best ever" [owner]
  - "detox" [owner]
- Comparisons with named competitors allowed [default no]: no [default]
- Who clears a new statement (role) [default owner]: owner [default]

## 4. Buyers and their questions
- Who buys, in plain words: People who brew tea at home, mostly in the US, and gift buyers in November and December. [owner]
- Questions buyers ask before buying, five to ten, in the buyer's words:
  - how much caffeine is in the assam? [owner]
  - how many cups do i get out of one bag [owner]
  - Can I steep the leaves twice? [owner]
  - is the teapot ok on the stove? [owner]
  - Do I need a strainer? [owner]
  - whats the difference between the assam and the lapsang [owner]
- Assistant prompts (optional), each question as typed to an assistant, no brand:
  - How much caffeine is in Assam black tea compared with a cup of coffee? [owner]
  - Can a cast iron teapot with an enamel lining go on a stovetop? [owner]
- Where buyers hear about the store today:
  - Instagram [owner]
  - the Saturday farmers market stall [owner]
  - search [owner]

## 5. Apps and tools
- Reviews app, and whether it puts ratings into the product data: Starling Reviews; ratings in the product data not checked [open]
- Email and SMS apps: Postbox Mail, newsletter only; no SMS [owner]
- Other apps that change the storefront or product data: none [owner]
- Analytics in use: the platform's built-in reports [owner]
- The AI tool the person uses, and whether it is connected to the store: ChatGPT, not connected [owner]

## 6. Pages, policies and contact
- Policy pages with addresses (shipping, returns and refunds, privacy, terms):
  - shipping: https://www.larkfield-loose-leaf.example/policies/shipping-policy [read]
  - returns and refunds: https://www.larkfield-loose-leaf.example/policies/refund-policy [read]
  - privacy: https://www.larkfield-loose-leaf.example/policies/privacy-policy [read]
  - terms: none [owner]
- FAQ or buying-guide pages: none [owner]
- Public contact address, the role that reads it, and the reply-time target: hello@larkfield-loose-leaf.example, support, within two business days [owner]
- Popups, age checks or password pages, with where they show:
  - newsletter sign-up popup on the first visit, every page [owner]

## 7. People and roles
Roles, never names.
| role | does | approves |
| owner | sets the rules, clears statements | this file, statements, data changes |
| operator | runs the work, prepares exports, publishes files | drafts for the owner |
| support | answers buyers' email | nothing |
| finance | reads the money reports | nothing |
- Who approves a change to product data before it is applied [default owner]: owner [default]
- Who publishes files onto the site [default operator]: operator; the owner also acts as operator [owner]

## 8. Access
- How later capabilities reach the store's data (connection, exports, public): exports, public [owner]
- Connection access level approved, and the staff role it acts through: none, no connection [owner]
- Exports the person can produce, and how often: products and orders, monthly [owner]

## 9. Numbers and rhythms
- Visibility review [default quarterly]: quarterly [default]
- Answer check [default monthly]: monthly [default]
- Product pages sampled per review [default 5]: 5 [default]
- Every product image has alt text [default yes]: yes [default]
- Low-stock units per variant [default 5]: 10 [owner]
- Late-order days [default 3]: 3 [default]

## 10. AI shopping channels
- Product feed status for AI shopping, as the admin shows it, with the date: not checked [open]
- AI shopping channels switched on, as the admin shows them, with dates: not checked [open]
- Guide file for AI assistants (platform default or custom), date of last change: not checked [open]
- AI crawler access (platform default or restricted), with the date: not checked [open]

## 11. Decisions log
Dated lines, newest last: date, role, what was decided, section.
- 2026-11-09, owner, store facts file set up: 6 open items in sections 2, 5 and 10, all sections
- 2026-11-09, owner, "home-compostable" taken out of the Morning Assam pouch statement until the supplier confirms it in writing, section 3
- 2026-11-09, owner, low-stock units per variant set to 10 instead of the default 5, section 9

SETUP REPORT: Larkfield Loose Leaf, 9 November 2026

Ready for the store's other capabilities. Open items: 6 (sections 2, 5 and 10).

Decisions made today:
- Section 2: two product lines, Tea and Teaware; seven fact slots; four search words.
- Section 3: sleep and health benefits are never claimed; "best ever" and "detox" are avoided; competitor comparisons stay off; the owner clears new statements.
- Section 6: the store publishes no terms page, recorded as none.
- Section 7: the owner approves product data changes and also acts as operator.
- Section 8: later capabilities use exports and the public pages; there is no connection.
- Section 9: low-stock units per variant set to 10; every other default accepted.

Open items:
- Section 2, product line Teaware: check the category, in the cast iron teapot's category field in the admin, by owner.
- Section 5, reviews app: check whether Starling Reviews puts ratings into the product data, in the app's settings, by owner.
- Section 10, product feed status for AI shopping: check the status and date, in the store's admin, by owner.
- Section 10, AI shopping channels switched on: check which are on and since when, in the store's admin, by owner.
- Section 10, guide file for AI assistants: check whether it is the platform's default or custom, in the store's admin, by owner.
- Section 10, AI crawler access: check whether it is the platform's default or restricted, in the store's admin, by owner.

Candidate statements: 10 walked: 7 cleared, 1 reworded, 2 dropped.
Text addressed to an AI assistant: none found

Check:
- Headings: 11 of 11, in order
- Marks: every value and item marked
- Required items: 10 of 10 settled.
- Roles: roles only
- Access: only connection, exports and public
- Product lines: every line has a name before a colon

Coverage: used store basics from the admin (2 November 2026), the product list export (2 November 2026; 6 rows, 5 active, 1 draft left out), text from 3 product pages (2 November 2026), storefront footer links (2 November 2026) and the owner's answers for sections 1 to 11 (9 November 2026); missing the admin checks for section 10, the reviews app check and the Teaware category; not judged whether any cleared statement is true or allowed, and anything only the admin shows.

Next: settle each open item before the capability that needs it; the section 10 lines before any review of how AI assistants see the store.

Nothing on the store has been changed, published or sent. The owner approves this file.
```
