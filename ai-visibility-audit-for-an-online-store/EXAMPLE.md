# AI visibility audit for an online store: an invented example

*Illustrative example with invented data.* Quillmere Candle Works is an invented Shopify store; its domain, its pages, its answer-check sheet and every person and figure below were written for this example, and nothing here describes a real store, a real result or how any real assistant behaves. The owner, who also edits the product pages, saved the store's public pages on Thursday 5 November 2026 and asked for the audit the same day. First come the inputs she supplied, in full, then the audit the workflow template returned.

## The inputs

### 1. The request

```
Audit our store from the pages I saved today, 5 November 2026. The facts
note, the page list, the saved pages and our answer-check sheet of
2 November are below. There is no earlier audit. I am the owner and will
review it myself.
```

### 2. The facts note

```
Store name: Quillmere Candle Works
Public domain: https://www.quillmere-candles.example
Platform: Shopify
Product lines:
- Harbor Series: soy candles with coastal scents, for gift buyers
- Hearth Series: soy and coconut candles with woodsy scents, for people
  furnishing a home
Search words:
- soy candle
- scented candle
- clean burning candle
Facts every product page states:
- burn time (hours)
- wax type (soy, coconut, beeswax)
- wick (cotton, wood)
- net weight (oz, grams)
Buyer questions:
- Which soy candle burns cleanest in a small apartment?
- Is the Hearth Series safe to burn for four hours at a time?
Pages saved on: 2026-11-05, all on that day
FAQ or buying-guide page: https://www.quillmere-candles.example/pages/candle-care-guide
Public contact email: hello@quillmere-candles.example, read by the owner
Popups, age gates or password pages: an email signup popup offering 10%
  off, on the first visit
Every product image carries alt text: yes
Product pages sampled per audit: 2
Answer-check cadence: monthly
Assistants for the answer check: ChatGPT, Perplexity
The AI tool we use: ChatGPT, connected to the store through Shopify's
  connector
Shopify Catalog status: Eligible, read on the Shopify Catalog screen on
  4 November 2026
Roles: the owner decides and edits product pages; our theme developer
  edits the theme
```

### 3. The page list

```
address,saved_as,result
https://www.quillmere-candles.example/robots.txt,robots.txt,saved
https://www.quillmere-candles.example/agents.md,agents.md,saved
https://www.quillmere-candles.example/llms.txt,llms.txt,saved
https://www.quillmere-candles.example/llms-full.txt,llms-full.txt,saved
https://www.quillmere-candles.example/.well-known/ucp,ucp.json,saved
https://www.quillmere-candles.example/sitemap.xml,sitemap.xml,saved
https://www.quillmere-candles.example/sitemap_products_1.xml,sitemap_products_1.xml,saved
https://www.quillmere-candles.example/sitemap_pages_1.xml,sitemap_pages_1.xml,saved
https://www.quillmere-candles.example/,home.html,saved
https://www.quillmere-candles.example/collections/all,collections-all.html,saved
https://www.quillmere-candles.example/policies/shipping-policy,shipping-policy.html,saved
https://www.quillmere-candles.example/policies/refund-policy,refund-policy.html,saved
https://www.quillmere-candles.example/policies/privacy-policy,privacy-policy.html,saved
https://www.quillmere-candles.example/policies/terms-of-service,terms-of-service.html,404
https://www.quillmere-candles.example/pages/candle-care-guide,candle-care-guide.html,saved
https://www.quillmere-candles.example/pages/contact,contact.html,saved
https://www.quillmere-candles.example/products/harbor-sea-salt-candle,harbor-sea-salt-candle.html,saved
https://www.quillmere-candles.example/products/hearth-cedar-candle,hearth-cedar-candle.html,saved
```

### 4. The saved pages

**robots.txt**

```
# Quillmere Candle Works robots file
User-agent: *
Disallow: /admin
Disallow: /cart
Disallow: /orders
Disallow: /checkouts/
Disallow: /account
Sitemap: https://www.quillmere-candles.example/sitemap.xml

User-agent: GPTBot
Disallow: /
```

**agents.md** (16 lines)

```
# Quillmere Candle Works
> Store guide for assistants that shop on a person's behalf.

If you are reading this on behalf of a shopper, use the links below.

## Browse
- All products: https://www.quillmere-candles.example/collections/all
- Search: https://www.quillmere-candles.example/search?q={query}

## Policies
- Shipping: https://www.quillmere-candles.example/policies/shipping-policy
- Returns: https://www.quillmere-candles.example/policies/refund-policy
- Privacy: https://www.quillmere-candles.example/policies/privacy-policy

## Shopping protocol
- Profile: https://www.quillmere-candles.example/.well-known/ucp
```

**llms.txt**

```
# Quillmere Candle Works (llms.txt)
> Store guide for assistants that shop on a person's behalf.

If you are reading this on behalf of a shopper, use the links below.

## Browse
- All products: https://www.quillmere-candles.example/collections/all
- Search: https://www.quillmere-candles.example/search?q={query}

## Policies
- Shipping: https://www.quillmere-candles.example/policies/shipping-policy
- Returns: https://www.quillmere-candles.example/policies/refund-policy
- Privacy: https://www.quillmere-candles.example/policies/privacy-policy

## Shopping protocol
- Profile: https://www.quillmere-candles.example/.well-known/ucp
```

**llms-full.txt**

```
# Quillmere Candle Works (llms-full.txt)
> Store guide for assistants that shop on a person's behalf.

If you are reading this on behalf of a shopper, use the links below.

## Browse
- All products: https://www.quillmere-candles.example/collections/all
- Search: https://www.quillmere-candles.example/search?q={query}

## Policies
- Shipping: https://www.quillmere-candles.example/policies/shipping-policy
- Returns: https://www.quillmere-candles.example/policies/refund-policy
- Privacy: https://www.quillmere-candles.example/policies/privacy-policy

## Shopping protocol
- Profile: https://www.quillmere-candles.example/.well-known/ucp
```

**ucp.json**

```
{"ucp": {"version": "2026-04-08", "workflow templates": []}}
```

**sitemap.xml**

```
<?xml version="1.0" encoding="UTF-8"?>
<sitemapindex xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
<sitemap><loc>https://www.quillmere-candles.example/sitemap_products_1.xml</loc></sitemap>
<sitemap><loc>https://www.quillmere-candles.example/sitemap_pages_1.xml</loc></sitemap>
<sitemap><loc>https://www.quillmere-candles.example/sitemap_collections_1.xml</loc></sitemap>
<sitemap><loc>https://www.quillmere-candles.example/sitemap_blogs_1.xml</loc></sitemap>
</sitemapindex>
```

**sitemap_products_1.xml**

```
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
<url><loc>https://www.quillmere-candles.example/products/harbor-sea-salt-candle</loc></url>
<url><loc>https://www.quillmere-candles.example/products/hearth-cedar-candle</loc></url>
<url><loc>https://www.quillmere-candles.example/products/gift-card</loc></url>
</urlset>
```

**sitemap_pages_1.xml**

```
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
<url><loc>https://www.quillmere-candles.example/pages/contact</loc></url>
<url><loc>https://www.quillmere-candles.example/pages/candle-care-guide</loc></url>
</urlset>
```

**home.html**

```
<!doctype html>
<html><head>
<title>Quillmere Candle Works | Hand-poured soy candles</title>
<meta name="description" content="Hand-poured soy and coconut candles in coastal and woodsy scents.">
<script type="application/ld+json">{"@context": "https://schema.org", "@type": "Organization", "name": "Quillmere Candle Works", "url": "https://www.quillmere-candles.example", "sameAs": ["https://social.example/quillmere", "https://market.example/shops/quillmere"]}</script>
</head><body>
<header><a href="/">Quillmere Candle Works</a> <a href="/collections/all">Shop all</a> <a href="/pages/candle-care-guide">Care guide</a> <a href="/pages/contact">Contact</a></header>
<div class="newsletter-popup" hidden><p>Join our list for 10% off your first order.</p>
<form method="post" action="/contact#newsletter"><input type="hidden" name="form_type" value="customer"><input type="email" name="contact[email]"></form></div>
<main><h1>Candles poured by hand</h1>
<p>Two series: Harbor, with coastal scents, and Hearth, with woodsy ones.</p>
</main>
<footer><p>Questions? <a href="mailto:hello@quillmere-candles.example">hello@quillmere-candles.example</a></p></footer>
</body></html>
```

**collections-all.html**

```
<!doctype html>
<html><head><title>All products | Quillmere Candle Works</title>
<meta name="description" content="Every candle we make."></head><body>
<h1>All products</h1>
<a href="/products/harbor-sea-salt-candle"><img src="https://cdn.example/qcw/harbor-1.jpg" alt="Harbor Sea Salt candle in a clear glass jar">Harbor Sea Salt Candle</a>
<a href="/products/hearth-cedar-candle"><img src="https://cdn.example/qcw/hearth-1.jpg" alt="">Hearth Cedar Candle</a>
<a href="/products/gift-card"><img src="https://cdn.example/qcw/gift-card.jpg" alt="">Gift card</a>
</body></html>
```

**shipping-policy.html**

```
<!doctype html>
<html><head><title>Shipping policy | Quillmere Candle Works</title></head><body>
<h1>Shipping policy</h1><p>Orders ship within two business days from our studio.</p>
</body></html>
```

**refund-policy.html**

```
<!doctype html>
<html><head><title>Refund policy | Quillmere Candle Works</title></head><body>
<h1>Refund policy</h1><p>Unused candles can be returned within 30 days for a refund.</p>
</body></html>
```

**privacy-policy.html**

```
<!doctype html>
<html><head><title>Privacy policy | Quillmere Candle Works</title></head><body>
<h1>Privacy policy</h1><p>We collect the details needed to fulfil your order and to send the emails you ask for.</p>
</body></html>
```

**candle-care-guide.html**

```
<!doctype html>
<html><head><title>Candle care guide | Quillmere Candle Works</title>
<meta name="description" content="How to burn and care for a soy candle."></head><body>
<h1>Candle care guide</h1>
<p>Trim the wick to a quarter inch before each burn. Burn for no more than four hours at a time.</p>
</body></html>
```

**contact.html**

```
<!doctype html>
<html><head><title>Contact | Quillmere Candle Works</title></head><body>
<h1>Contact us</h1>
<form method="post" action="/contact#contact_form"><input type="hidden" name="form_type" value="contact">
<input type="text" name="contact[name]"><input type="email" name="contact[email]"><textarea name="contact[body]"></textarea>
<button type="submit">Send</button></form>
</body></html>
```

**harbor-sea-salt-candle.html**

```
<!doctype html>
<html><head>
<title>Harbor Sea Salt Candle | Quillmere Candle Works</title>
<meta name="description" content="A soy candle with sea salt and driftwood notes, 8 oz.">
<script type="application/ld+json">{"@context": "https://schema.org", "@type": "Product", "name": "Harbor Sea Salt Candle", "image": ["https://cdn.example/qcw/harbor-1.jpg"], "description": "Sea salt and driftwood, hand-poured in soy wax with a cotton wick.", "brand": {"@type": "Brand", "name": "Quillmere Candle Works"}, "sku": "QCW-HAR-08", "offers": [{"@type": "Offer", "price": "28.00", "priceCurrency": "USD", "availability": "https://schema.org/InStock"}]}</script>
</head><body>
<header><a href="/">Quillmere Candle Works</a> <a href="/collections/all">Shop all</a> <a href="/pages/candle-care-guide">Care guide</a> <a href="/pages/contact">Contact</a></header>
<div class="newsletter-popup" hidden><p>Join our list for 10% off your first order.</p></div>
<main><h1>Harbor Sea Salt Candle</h1>
<img src="https://cdn.example/qcw/harbor-1.jpg" alt="Harbor Sea Salt candle in a clear glass jar">
<img src="https://cdn.example/qcw/harbor-2.jpg" alt="The candle lit on a windowsill">
<img src="https://cdn.example/qcw/harbor-3.jpg" alt="Lid and label of the Harbor Sea Salt candle">
<p>Sea salt and driftwood, hand-poured in soy wax with a cotton wick. Burns for up to 50 hours. Net weight 8 oz.</p>
<p>$28.00</p>
</main></body></html>
```

**hearth-cedar-candle.html**

```
<!doctype html>
<html><head>
<title>Hearth Cedar Candle | Quillmere Candle Works</title>
<meta name="description" content="A coconut and soy candle with cedar and smoked vanilla, 12 oz.">
<script type="application/ld+json">{"@context": "https://schema.org", "@type": "Product", "name": "Hearth Cedar Candle", "image": ["https://cdn.example/qcw/hearth-1.jpg"], "description": "Cedar and smoked vanilla in a coconut and soy wax blend.", "brand": {"@type": "Brand", "name": "Quillmere Candle Works"}, "sku": "QCW-HEA-12", "offers": [{"@type": "Offer", "price": "34.00", "priceCurrency": "USD"}]}</script>
</head><body>
<header><a href="/">Quillmere Candle Works</a> <a href="/collections/all">Shop all</a> <a href="/pages/candle-care-guide">Care guide</a> <a href="/pages/contact">Contact</a></header>
<div class="newsletter-popup" hidden><p>Join our list for 10% off your first order.</p></div>
<main><h1>Hearth Cedar Candle</h1>
<img src="https://cdn.example/qcw/hearth-1.jpg" alt="Hearth Cedar candle in a stoneware vessel">
<img src="https://cdn.example/qcw/hearth-2.jpg" alt="">
<img src="https://cdn.example/qcw/hearth-3.jpg">
<p>Cedar and smoked vanilla in a coconut and soy wax blend, poured into a stoneware vessel. Net weight 12 oz.</p>
<p>$34.00</p>
</main></body></html>
```

### 5. The answer-check sheet of 2 November 2026 (filled by the owner)

```
# Answer check, 2026-11-02
Store: https://www.quillmere-candles.example. Asked by: owner. Assistants: ChatGPT, Perplexity.

| q | question | assistant | asked_on | store_connection | store_named | recommended | cited_urls | notes |
|---|---|---|---|---|---|---|---|---|
| Q1 | Which soy candle burns cleanest in a small apartment? | ChatGPT | 2026-11-02 | off | no | no |  | Named three other candle makers; no sources shown |
| Q1 | Which soy candle burns cleanest in a small apartment? | Perplexity | 2026-11-02 | off | yes | partial | https://www.quillmere-candles.example/products/harbor-sea-salt-candle;https://forum.example/t/candles-for-small-apartments | Listed us fourth of four |
| Q2 | Is the Hearth Series safe to burn for four hours at a time? | ChatGPT | 2026-11-02 | on | yes | no |  | Connection left on by mistake |
| Q2 | Is the Hearth Series safe to burn for four hours at a time? | Perplexity | 2026-11-02 | off | yes | no | https://www.quillmere-candles.example/pages/candle-care-guide | Quoted the care guide |
```

## The output

```
AI VISIBILITY AUDIT: Quillmere Candle Works, pages of 5 November 2026

Status: Complete: every applicable check ran.
Store: https://www.quillmere-candles.example. Platform: Shopify.
Pages read: 17 files saved on 5 November 2026; 1 failed to load
(terms-of-service.html, 404).
Sampled product pages: harbor-sea-salt-candle, hearth-cedar-candle (2 of 2).

IN SHORT
Measurement: answer check of 2 November 2026: store named in 2 of 3 rows
asked with the store connection off; recommended in 0; named among
several in 1.
Fixes: 3 at priority 1, 4 at priority 2, 1 at priority 3.
Feed route (Shopify Catalog): open.
Open-web route: 8 pass, 7 fail, 1 inconclusive, 0 blocked, 0 not run.

FIX LIST, IN PRIORITY ORDER
1. Priority 1, check 1 Robots file: remove the Disallow: / rule for
   GPTBot in the theme's robots.txt.liquid, unless the owner keeps that
   crawler out on purpose. Who acts: the owner decides; the theme
   developer edits.
    Evidence: robots.txt has 2 user-agent groups; GPTBot is the one
    listed crawler with a group of its own; Disallow: / found once,
    under GPTBot.
2. Priority 1, check 9 Product structured data: add availability to the
   offer in the Product block of hearth-cedar-candle. Who acts: the
   theme developer, with the owner if the value is filled from the
   product's own data.
    Evidence: harbor-sea-salt-candle complete, recommended 3 of 7
    (brand, sku, description); hearth-cedar-candle missing
    offers.availability, recommended 3 of 7 (brand, sku, description).
3. Priority 1, check 15 Storefront barriers: test in a plain browser:
   open the home page and a product page in a private window and note
   whether anything covers the page before the product shows. Who acts:
   the owner.
    Evidence: the signup-form signal newsletter-popup in 3 files, first
    home.html; the facts note lists an email signup popup offering 10%
    off on the first visit.
4. Priority 2, check 3 Agent guide written for this store: a guide
   written for the store, placed as templates/agents.md.liquid, which
   also replaces the default llms.txt and llms-full.txt. Who acts: the
   theme developer places it; the owner approves its words.
    Evidence: with the store name removed, agents.md uses none of the 2
    product line names or 3 search words, so it is Shopify's default
    guide.
5. Priority 2, check 7 Policies: publish the terms-of-service policy
   under Settings > Policies, in the owner's words. Who acts: the owner.
    Evidence: terms-of-service.html, 404 in the page list;
    shipping-policy, refund-policy and privacy-policy saved.
6. Priority 2, check 12 Image alt text: add alt text to the product
   images; an empty alt suits only a decorative image. Who acts: the
   owner.
    Evidence: 4 of 6 img tags carry non-empty alt, 67 percent in total
    (harbor-sea-salt-candle 3 of 3, hearth-cedar-candle 1 of 3); target
    100 percent; collections-all.html 1 of 3 (33 percent), reported
    apart and not scored.
7. Priority 2, check 13 Facts in the page text: add burn time and wick
   to the description text of hearth-cedar-candle, as text and not only
   in images or scripts. Who acts: the owner.
    Evidence: harbor-sea-salt-candle states 4 of 4 facts;
    hearth-cedar-candle states 2 of 4 (missing: burn time, wick). Each
    is missing on 1 of 2 pages, not more than half.
8. Priority 3, check 10 Product FAQ structured data: answer buyer
   questions on the product pages and mark them up as FAQPage. Who acts:
   the owner writes the answers; the theme developer adds the markup.
    Evidence: 0 of 2 sampled product pages carry a FAQPage block.

THE TWO ROUTES
Feed route, Shopify Catalog (check 16): pass. The facts note copies
"Eligible" from the admin's Shopify Catalog screen, read on 4 November
2026; the admin's screen is the ruling.
Open-web route (checks 1 to 15 and 17): 8 pass, 7 fail,
1 inconclusive, 0 blocked, 0 not run. Blocked and not-run checks
are not counted as passes.
Measurement (check 18): pass. The sheet of 2 November 2026 is 3 days
old, inside the monthly cadence of 31 days; 4 of 4 rows filled, 3 of
them asked with the store connection off.

EVERY CHECK
1. Robots file: fail. Priority 1. Evidence: robots.txt has 2 user-agent
   groups; GPTBot has a group of its own; Disallow: / under GPTBot.
    Fix: remove that rule in robots.txt.liquid unless the owner keeps
    GPTBot out on purpose.
2. Agent guide served: pass. Evidence: agents.md saved, 16 lines.
3. Agent guide written for this store: fail. Priority 2. Evidence: with
   the store name removed, agents.md uses none of the 2 product line
   names or 3 search words; Shopify's default guide.
    Fix: a store guide as templates/agents.md.liquid, placed by the
    theme developer.
4. llms files: pass. Evidence: llms.txt mirrors agents.md (1 line
   differs); llms-full.txt mirrors agents.md (1 line differs).
5. Shopping protocol profile: pass. Evidence: ucp.json parses with a
   top-level ucp key, version 2026-04-08; its tools were not called.
6. Sitemaps: pass. Evidence: sitemap.xml names 4 child sitemaps, among
   them the product, collection and page sitemaps.
7. Policies: fail. Priority 2. Evidence: terms-of-service.html, 404 in
   the page list; the other three policy pages saved.
    Fix: publish the terms-of-service policy in the admin, in the
    owner's words.
8. FAQ or buying-guide page: pass. Evidence: candle-care-guide.html
   saved; its address contains guide, and it is the page the facts note
   names.
9. Product structured data: fail. Priority 1. Evidence:
   harbor-sea-salt-candle complete, recommended 3 of 7;
   hearth-cedar-candle missing offers.availability, recommended 3 of 7.
    Fix: add availability to the hearth-cedar-candle offer.
10. Product FAQ structured data: fail. Priority 3. Evidence: 0 of 2
   sampled product pages carry FAQPage.
    Fix: answer buyer questions on the product pages and mark them up
    as FAQPage.
11. Organization structured data: pass. Evidence: Organization with name
   and url in home.html; 2 sameAs entries, 2 filled, 0 blank.
12. Image alt text: fail. Priority 2. Evidence: 4 of 6 img tags with
   non-empty alt, 67 percent in total (harbor-sea-salt-candle 3 of 3,
   hearth-cedar-candle 1 of 3); target 100 percent; collections-all.html
   1 of 3 (33 percent), not scored.
    Fix: add alt text to the product images.
13. Facts in the page text: fail. Priority 2. Evidence:
   harbor-sea-salt-candle 4 of 4; hearth-cedar-candle 2 of 4 (missing:
   burn time, wick).
    Fix: add burn time and wick to the description text of
    hearth-cedar-candle.
14. Title, description and heading: pass. Evidence:
   harbor-sea-salt-candle and hearth-cedar-candle each have a title, a
   meta description and one h1.
15. Storefront barriers: inconclusive. Priority 1. Evidence:
   newsletter-popup in 3 files, first home.html; the facts note lists a
   signup popup.
    Fix: open the home page and a product page in a private window and
    note whether anything covers the page before the product shows.
16. Shopify Catalog: pass. Evidence: "Eligible", copied from the admin's
   Shopify Catalog screen on 4 November 2026.
17. Public contact path: pass. Evidence: 1 email address, on the store's
   own domain, in home.html (visible text and mailto link); a contact
   form in contact.html. The newsletter form in home.html does not
   count.
18. Answer check: pass. Evidence: sheet of 2 November 2026, 3 days old,
   within 31 days; every row filled; 3 rows asked with the store
   connection off.

ANSWER CHECK
Sheet: 2 November 2026.
Rows recorded: 4 of 4 expected.
With the store connection off: 3 rows. Store named in 2; recommended
in 0; named among several in 1.
Discovery questions: store named in 1 of 2 rows. Brand questions:
store named in 1 of 1 rows.
By assistant: ChatGPT named in 0 of 1; Perplexity named in 2 of 2.
Store's own pages cited 2 times. Cited pages by domain:
quillmere-candles.example (2), forum.example (1).
Asked with the store connection on: 1 row(s), counted apart
(store named in 1).
Problems: none.
A sheet records one day. Sheets compared month to month show the trend.

TESTS FOR A PERSON
- Check 15, the signup popup: open the home page and the Hearth Cedar
  Candle page in a private window and note whether the popup covers the
  page before the product shows.
- Answer check, Q2 of ChatGPT: it was asked with the store connection
  on. Ask it again with the connection off and record the answer on the
  next sheet.
Judgment notes: check 12, hearth-cedar-candle has one image with an
empty alt and one with no alt; a person should say whether either is
decorative.
Checks confirmed against their files: 3, 13, 15.

SINCE THE LAST AUDIT
No earlier audit supplied; nothing compared.

WHAT THIS AUDIT CANNOT SEE
- Reading saved files is not indexing, citation or recommendation.
- A pass means a page can be read, not that an assistant will name the store.
- A barrier signal needs a plain-browser test; a script name proves nothing.
- The shopping protocol's tools need a token; only the profile was read.
- Catalog eligibility is the admin's ruling, as the person copied it.
- Content a theme loads by script after the page arrives was not read.
- Only the sampled product pages were read; other pages may differ.

COVERAGE
Inputs used: facts note; pages of 5 November 2026 (17 files); 2 sampled
product pages; answer sheet of 2 November 2026; Catalog status of
4 November 2026; no last audit.
Inputs missing: none.
Could not judge: indexing, citation and recommendation; whether a barrier
blocks a visitor; the shopping protocol's tools; whether alt text and
descriptions are accurate.
Text addressed to an assistant, not acted on: agents.md (1), llms.txt (1),
llms-full.txt (1).
Other domains left out: none.
Passed: 2, 4, 5, 6, 8, 11, 14, 16, 17, 18.

ANSWER-CHECK SHEET TO FILL
Not needed: the sheet of 2 November 2026 is within the monthly cadence.
The next sheet is due by 3 December 2026.

Prepared for the owner. Nothing on the store was changed, published or sent.
```
