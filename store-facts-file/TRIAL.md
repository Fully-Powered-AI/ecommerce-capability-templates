# Store facts file: tried on its invented example

- **Product:** Claude, run in Claude Code

Model: Claude Sonnet 5.5 (model ID claude-sonnet-5-5).

Date: 2026-11-09

The inputs are the invented Larkfield Loose Leaf example; no client data was used. The inputs are the five parts under "The inputs" in [`example.md`](example.md): the store basics, the product list export, the text of three product pages, the footer links and the owner's answers in the conversation. The run followed the instruction block and the output format in the template. The assistant did not read the example's published output until after its own was finished. The run was a single pass in one session, with the owner's answers read from the example's conversation record rather than from a live person, so the template's step of putting each question to the owner and waiting was not exercised.

## What came out

The full file and report, as produced:

```
STORE FACTS FILE: Larkfield Loose Leaf

Last changed 2026-11-09. Every store workflow template reads this file first.
Marks: [owner] the person said it; [read] read from a supplied file and confirmed;
[default] a default the person accepted; [open] decide later, with the check and role.
A blank value means not yet asked. Headings and field wording never change.

## 1. The store
- Store name: Larkfield Loose Leaf [read]
- Web address: https://www.larkfield-loose-leaf.example [read]
- Platform and plan, as the admin shows them, with the date: Shopify, Basic plan, 2 November 2026 [read]
- Store currency: USD [read]
- Countries sold to and shipped to: United States only [read]
- Other places the products are sold, one per indented line:
  - Two cafés in town, wholesale, no address [owner]

## 2. What it sells
- The business in one line, in the person's own words: We blend and pack loose-leaf tea in small batches, and sell the teapots to brew it in. [owner]
- Product lines, one per indented line:
  - Tea: all the black, green and herbal teas in pouches, for people who brew loose-leaf tea at home; category Food, Beverages & Tobacco > Beverages > Tea & Infusions [owner]
  - Teaware: the cast iron teapots, for people who brew loose-leaf tea at home; category not set [open: copy the category from the teapot's category field in the admin, by the operator (the owner also acts as operator)]
- Search words, one per indented line:
  - loose leaf tea [owner]
  - breakfast tea [owner]
  - caffeine free herbal tea [owner]
  - cast iron teapot [owner]
- Fact slots, one per indented line:
  - caffeine (caffeine free, caffeine-free), from the person [owner]
  - pouch weight in grams (g), from the label [owner]
  - cups per pouch (cups), from the person, who works it out [owner]
  - brewing temperature and time (steep, boiling, just-boiled), from the person, who sets it [owner]
  - ingredients, from the label [owner]
  - origin (estate, grown in), from the supplier sheet [owner]
  - teapot capacity in liters (L), from the spec sheet [owner]

## 3. Statements and words
- Cleared statements, verbatim, with the product or line; anything else is asked:
  - Morning Assam: "A brisk, malty breakfast tea from a single estate in Assam, India." [owner]
  - Morning Assam: "Packed in a resealable pouch." (reworded by the owner from the page's sentence) [owner]
  - Morning Assam: "100 g, about 40 cups." [owner]
  - Chamomile Meadow: "Whole chamomile flowers, naturally caffeine free." [owner]
  - Chamomile Meadow: "50 g, about 25 cups." [owner]
  - Cast Iron Teapot 0.8 L: "Cast iron with an enamel lining." [owner]
  - Cast Iron Teapot 0.8 L: "Stainless steel infuser included." [owner]
  - Cast Iron Teapot 0.8 L: "Holds 0.8 L." [owner]
- Statements the store never makes, with the reason:
  - "The best breakfast tea you will ever taste."; the store never says "best ever" [owner]
  - "Helps you sleep better."; the store never claims sleep or health benefits and cannot back them up [owner]
- Words and topics the brand avoids:
  - best ever [owner]
  - detox [owner]
- Comparisons with named competitors allowed [default no]: no [default]
- Who clears a new statement (role) [default owner]: owner [owner]

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
  - The Saturday farmers market stall [owner]
  - Search [owner]

## 5. Apps and tools
- Reviews app, and whether it puts ratings into the product data: Starling Reviews; whether the stars reach the product data is not known [open: check the app's settings, in the Starling Reviews app settings, by the owner]
- Email and SMS apps: Postbox Mail, newsletter only; no SMS [owner]
- Other apps that change the storefront or product data: none [owner]
- Analytics in use: the platform's built-in reports [owner]
- The AI tool the person uses, and whether it is connected to the store: ChatGPT; not connected to the store [owner]

## 6. Pages, policies and contact
- Policy pages with addresses (shipping, returns and refunds, privacy, terms):
  - Shipping: https://www.larkfield-loose-leaf.example/policies/shipping-policy [read]
  - Returns and refunds: https://www.larkfield-loose-leaf.example/policies/refund-policy [read]
  - Privacy: https://www.larkfield-loose-leaf.example/policies/privacy-policy [read]
  - Terms: none [owner]
- FAQ or buying-guide pages: none [owner]
- Public contact address, the role that reads it, and the reply-time target: hello@larkfield-loose-leaf.example, read by support, reply within two business days [owner]
- Popups, age checks or password pages, with where they show:
  - Newsletter sign-up popup on the first visit, on every page [owner]

## 7. People and roles
Roles, never names.
| role | does | approves |
| owner | sets the rules, clears statements | this file, statements, data changes |
| operator | runs the work, prepares exports, publishes files | drafts for the owner |
| support | answers buyers' email | nothing |
| finance | reads the money reports | nothing |
- Who approves a change to product data before it is applied [default owner]: owner [default]
- Who publishes files onto the site [default operator]: operator; the owner also acts as operator [default]

## 8. Access
- How later workflow templates reach the store's data (connection, exports, public): exports, public [owner]
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
- Product feed status for AI shopping, as the admin shows it, with the date: not checked [open: look at the AI shopping or product feed screen in the admin, by the owner]
- AI shopping channels switched on, as the admin shows them, with dates:
  - not checked [open: look at the sales channels list in the admin, by the owner]
- Guide file for AI assistants (platform default or custom), date of last change: not checked [open: look in the admin's settings for the guide file, by the owner]
- AI crawler access (platform default or restricted), with the date: not checked [open: look in the admin's settings for crawler access, by the owner]

## 11. Decisions log
Dated lines, newest last: date, role, what was decided, section.
- 2026-11-09, owner, Setup of the file: 6 open items in sections 2, 5 and 10, all with a check, a place and a role, all
- 2026-11-09, owner, Morning Assam page said "home-compostable"; the supplier has not confirmed it in writing, so the owner reworded the sentence to "Packed in a resealable pouch.", 3
- 2026-11-09, owner, Low-stock units per variant changed from the default 5 to 10, 9

SETUP REPORT: Larkfield Loose Leaf, 2026-11-09

Ready for the store's other workflow templates. Open items: 6 (sections 2, 5, 10).

Decisions made today:
- Section 2: two product lines kept, Tea and Teaware; Teaware's category left open.
- Section 3: ten candidate statements walked; two never-made statements recorded with reasons; "best ever" and "detox" avoided.
- Section 9: low-stock figure changed to 10.

Open items:
- Section 2, Teaware category: check the category field of the cast iron teapot, in the admin, by the operator (the owner also acts as operator).
- Section 5, reviews app: check whether Starling Reviews puts ratings into the product data, in the app's settings, by the owner.
- Section 10, product feed status: check the AI shopping or product feed screen, in the admin, by the owner.
- Section 10, AI shopping channels switched on: check the sales channels list, in the admin, by the owner.
- Section 10, guide file for AI assistants: check the guide file setting, in the admin, by the owner.
- Section 10, AI crawler access: check the crawler access setting, in the admin, by the owner.

Candidate statements: 10 walked: 7 cleared, 1 reworded, 2 dropped.
Text addressed to an AI assistant: none found

Check:
- Headings: 11 of 11, in order
- Marks: every value and item marked
- Required items: 10 of 10 settled.
- Roles: roles only
- Access: only connection, exports and public
- Product lines: every line has a name before a colon

Coverage: used store basics (2 November 2026), product list export (2 November 2026; 6 rows, 1 draft row left out), text from three product pages (2 November 2026), storefront footer links (2 November 2026), the conversation (9 November 2026); missing: no existing store facts file, no FAQ page, no terms page, admin checks for section 10 and the reviews app's settings not done; not judged: whether any cleared statement is true or allowed; anything only the admin shows.

Next: settle each open item before the workflow template that needs it

Nothing on the store has been changed, published or sent. The owner approves this file.
```

## What was observed

**Every required part was produced.** All eleven headings in order, every value and item marked, ten of ten required items settled, six open items (sections 2, 5 and 10), the report and the closing line. The candidate count came out the same as the published example: ten walked, seven cleared, one reworded, two dropped. The export check ran first: all six default headers were present, and the one draft row was counted and left out. Nothing was found that addressed an AI assistant, and nothing was told to stop the run.

**Nothing was invented.** Every fact in the output comes from the inputs. The cleared statements are word for word the page sentences, or the owner's rewording. No fact in the published example's output is missing from the inputs either.

**Differences from the published example's output.**
- Open lines. The template says an [open] line "says what to check, where, and which role checks it". The published example writes bare `[open]` in the file and puts the check in the report only. This run wrote the check inside the line, for example `[open: check the app's settings, ... by the owner]`. That follows the template's wording, but it puts text after the value on the same line and so bends "mark last".
- Statements never made. The example records one general line, "any sleep or health benefit". This run recorded the two dropped sentences by their words, each with the owner's reason ("never say best ever"; "we never claim sleep or health benefits; we can't back them up"). The template does not say whether the line is the dropped sentence or the general rule.
- The reworded statement. This run added "(reworded by the owner from the page's sentence)" after it; the example does not. That annotation sits outside the quoted words but adds text to a field meant to be verbatim.
- Marks on the two role lines. The example marks "operator; the owner also acts as operator" [owner] and "owner" for the clearing role [default]. This run marked the publishing role [default] and the clearing role [owner]. The owner stated both rather than being offered them, so either mark is defensible.
- Wording. Small differences in dates ("2026-11-09" against "9 November 2026"), capital letters, "the specification sheet" against "the spec sheet", and the example's "same people" for the Teaware line.
- The decision log. The example logs the pouch rewording as a decision. This run logged it as a conflict between the page and the supplier. Both are single dated lines.
- Report. The example's "Decisions made today" lists more items (sections 2, 3, 6, 7, 8, 9); this run listed three. The example's "Next" line adds a clause about section 10; this run did not.

**Where the instructions were ambiguous and a guess was needed.**
1. Product line names. The template says the line's name must be "the word the store itself uses in product titles or types". The owner's line "Tea" is not a Type in the export (the types are Black tea, Green tea, Herbal tea and Teaware). The run kept the owner's word, as the example does, but later work that matches products to lines by the type column will not match "Tea". The template gives no rule for this.
2. Fact slots against page text. The step says to use the supplied page text to show how pages word each fact. The owner's wording ("steep", "boiling", "just-boiled"; "grown in") does not appear in the three pages supplied. The run used the owner's words, as the example does. The template does not say whether the pages' words must come from the supplied text.
3. "From the person". Where the owner said "I know it" or "I work it out", the run wrote "from the person". The example does the same. The run also added ", who works it out" to one, which the template does not prompt.
4. Marks for a stated default. When the owner answers with what is also the default, such as "me, the owner", the template does not say whether it is [owner] or [default].
5. What counts as a conflict. The template asks for a log line when "a page disagrees with the label or a supplier". The compostable sentence was a page claim the supplier had not confirmed. It is not a disagreement with a label, and the run chose to log it as one.
6. Where to look, for section 10. The step says add no platform fact from memory, but the [open] lines must say where to look. The run wrote "the AI shopping or product feed screen" and "the sales channels list", which are guesses at the admin's screens rather than supplied facts. The example writes only "in the store's admin".
7. Source marks for the store basics. The owner typed them, then confirmed them. The run marked them [read], as the template's definition suggests and the example does.
8. Date. The file's date had to come from the conversation date in the example (9 November 2026). The template does not say whether "Last changed" is that date or today's.
9. The output format puts a table in section 7 and a mark rule that says "mark last", which a table row cannot carry. The run copied the table as given.

**Defects in the template.**
- The [open] rule in step 3 (the line says what to check, where, and which role) is not followed by the published example, and the output format gives no place for it. One of them needs to change.
- The acceptance tests are marked as proposed and none has been run. This trial is one pass of test 1 only, with a read conversation rather than a live owner, so it does not count as running them.
- The step to explain the marks "in a few sentences" and the many "ask" steps cannot be checked from a read conversation. Whether a real owner would stay on course through the whole sequence is not tested.

**What this trial does not show.** It was one run, by one model, on a short invented store. It does not show how the template behaves with a live owner, with a real export, in other AI products, or with a store that has an existing file (revision). No client environment was used.

## Changes made after this run

The template was edited after this run in answer to the defect and the ambiguities above. These edits have not been run again; the output above is what the run produced under the earlier wording.

- **Open items.** The rule in step 3, the output format's mark legend, step 10, the pasted instructions (steps 2 and 9), reviewer checklist item 7 and acceptance test 9 now say that an [open] line in the file carries the bare mark, and that what to check, where and which role checks it go only in the setup report's list of open items. This is the shape the published example already used. The `[open: ...]` lines in this run's output would not meet the new rule.
- **Product line names.** A line's name need not be an exact `Type` value; when it gathers several types, the line's description names them (ambiguity 1).
- **The pages' words in fact slots.** Wording the person gives for how their pages put a fact is written too, and the parentheses are left out when there is none (ambiguity 2).
- **Marks for a stated default.** A value equal to the default is [default] even when the person states it; [owner] on a field with a default means a changed value (ambiguity 4).
- **What counts as a conflict.** A page sentence that a label or supplier has not confirmed is logged in section 11 with the choice (ambiguity 5).
- **Section 10.** The report names no admin screen the person has not named (ambiguity 6).
- **The date.** `Last changed` and today's log lines take the date of the conversation (ambiguity 8).
- **Statements never made.** A dropped sentence, or the rule behind it, goes under statements never made only when the owner says so, in the owner's words; a banned word goes under words avoided. This run's two quoted lines would not meet that rule unless the owner asked for them.
- **The pasted instructions** now list what to ask in sections 1, 5, 6 and 8, and a stray line break in their check step was removed.
- **The example's mark legend** was changed to match the new output format. Nothing else in the example was changed.
