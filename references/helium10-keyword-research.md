# Helium 10 Keyword Research: Complete Reference Guide

A step-by-step guide to using Helium 10's full keyword suite — Cerebro, Magnet, Frankenstein, Scribbles, and Keyword Tracker — to build a keyword strategy that wins organic rank and drives sales.

---

## Table of Contents
1. [The Tool Stack](#tool-stack)
2. [Metrics Glossary](#metrics-glossary)
3. [Phase 1 — Competitor Intelligence with Cerebro](#phase-1-cerebro)
4. [Phase 2 — Seed Expansion with Magnet](#phase-2-magnet)
5. [Phase 3 — Cleaning with Frankenstein](#phase-3-frankenstein)
6. [Phase 4 — Listing Build with Scribbles](#phase-4-scribbles)
7. [Phase 5 — Rank Monitoring with Keyword Tracker](#phase-5-keyword-tracker)
8. [The Complete Workflow End-to-End](#complete-workflow)
9. [Filter Recipes by Goal](#filter-recipes)
10. [Keyword Tiering and Placement](#keyword-tiering)
11. [Backend Search Term Rules](#backend-rules)
12. [Misspellings and Non-English Keywords](#misspellings)
13. [New Listing vs. Existing Listing Research](#new-vs-existing)
14. [PPC Keyword Alignment](#ppc-alignment)
15. [Common Mistakes](#common-mistakes)

---

## Tool Stack

The Helium 10 keyword workflow is a pipeline. Each tool has one job. They pass output to the next stage.

| Tool | Job | Input | Output |
|------|-----|-------|--------|
| **Cerebro** | Reverse-engineer what competitors rank for | Competitor ASINs (up to 10) | Keywords + rank positions + competition data |
| **Magnet** | Expand from a seed keyword — find demand competitors missed | Seed keywords (up to 200) | Thousands of related search terms with volume + metrics |
| **Frankenstein** | Clean, deduplicate, and frequency-rank the combined raw list | Raw keyword dump from Cerebro + Magnet | Lean, sorted, deduplicated master keyword list |
| **Scribbles** | Write and track the listing — marks keywords as used/unused as you type | Processed keyword list + listing fields | Completed listing copy with full keyword coverage tracked |
| **Keyword Tracker** | Monitor organic rank positions over time | Target keywords | Daily rank positions, trend graphs, alert thresholds |

**Using only one or two of these tools leaves real gaps:**
- Magnet without Cerebro: finds general demand but misses proven converting keywords competitors already validated
- Cerebro without Magnet: finds competitor keywords but misses emerging demand and buyer-language variations
- Neither without Frankenstein: you end up with 3,000 keywords and no way to deploy them
- All research without Scribbles: keywords stay in a spreadsheet and never make it into the listing consistently
- No Keyword Tracker: you optimize once and never know if it worked

---

## Metrics Glossary

These same metrics appear across all Helium 10 tools. Know them before you start filtering.

### Search Volume
Estimated monthly Amazon searches for this exact phrase. Derived from Amazon's actual search data.

**What to know:**
- Directional, not exact — treat it as a relative signal
- Monthly figures are averaged; check the trend graph for seasonal keywords
- 500 monthly searches is a reasonable minimum threshold for primary keywords
- Under 100/month: long-tail territory — still valuable in backend and bullets but won't drive launch traffic

### Cerebro IQ Score / Magnet IQ Score
`Search Volume ÷ Competing Products` — the demand/competition ratio in a single number.

| Score | Interpretation |
|-------|---------------|
| 100+ | High opportunity — strong demand, lower competition |
| 40–99 | Solid target, especially if keyword is highly relevant |
| 15–39 | Competitive, needs strong listing + PPC to crack |
| Under 15 | Heavily contested — not a primary organic target for new listings |

**Caveat:** IQ Score is an opportunity signal, not a guarantee. A high-IQ keyword that's only loosely relevant to your product still won't convert.

### Organic Rank
Position (1–306+) where a specific ASIN appears in organic (non-sponsored) search results for a keyword.

- **Rank 1–10:** Top of page 1. Drives the majority of clicks and conversions.
- **Rank 11–20:** Low page 1/top page 2. Meaningful visibility.
- **Rank 21–50:** Page 2+. Minimal organic traffic — keyword is indexed but not effectively ranked.
- **Rank 300+:** Technically indexed. No practical organic visibility.

In Cerebro context: a competitor's organic rank tells you how strong their foothold is on that keyword.

### Title Density
Number of page-1 products that include this exact keyword phrase in their title.

| Density | Meaning |
|---------|---------|
| 0–3 | Most competitors haven't used this in their title — first-mover advantage if you do |
| 4–7 | Keyword is established but not saturated |
| 8–10 | Every serious competitor uses it — table stakes, you must include it |

**Low title density + high search volume = underexploited opportunity.**

### Competing Products
Total product count returned in an Amazon search for this keyword (the full results pool).

| Count | Difficulty |
|-------|-----------|
| Under 1,000 | Low — highly targetable for new listings |
| 1,000–5,000 | Moderate — achievable with good listing + some PPC |
| 5,000–20,000 | Competitive — needs strong conversion rate and review velocity |
| 20,000+ | Very competitive — not a primary organic target for launches |

### Search Volume Trend
Percentage change in search volume over the last 30 days. Positive = rising demand, negative = falling or seasonal.

**Use:** Identify rising keywords before competitors saturate them. Flag seasonal keywords for planned listing refreshes.

### CPR (Cerebro Product Rank) / 8-Day Giveaway Number
Estimated units you'd need to sell at a steep discount over 8 days to reach page 1 for this keyword. Lower = easier to rank organically through launch velocity.

### Match Type
How the keyword was detected:
- **Organic:** ASIN ranks naturally in search results for this keyword
- **Sponsored:** ASIN runs paid ads against this keyword
- **Amazon Recommended:** Amazon's algorithm associates this product with this keyword regardless of explicit optimization

### ABA Total Click Rate *(Platinum/Diamond plans)*
Amazon Brand Analytics data showing combined click share of the top 3 ASINs. High concentration = a few dominant ASINs own this keyword. Distributed = room for new entrants.

### Keyword Sales *(Diamond plan, US only)*
Estimated monthly units sold attributed to each keyword. The most direct measure of commercial value — actual purchase intent, not just traffic.

---

## Phase 1 — Competitor Intelligence with Cerebro

### What Cerebro Does
Takes competitor ASINs and reverse-engineers every keyword they rank for — organic, sponsored, and Amazon-recommended — along with their rank position, search volume, and competition level for each term.

It answers: *"What keywords are your top competitors using to drive sales, and how hard is each one to take?"*

---

### Step 1: Identify the Right ASINs

Don't just grab the #1 bestseller. The category leader's keyword footprint includes brand terms, legacy authority, and terms that took years to earn. You want mid-tier established sellers — strong but not dominant.

**Tier 1 ASINs (3–5, your primary analysis group):**
- BSR in the top 1% of their sub-category
- 300–2,000 reviews with 4.0–4.6 stars
- Priced within 20% of your target price
- Clearly well-optimized listings (good copy, full image gallery, A+ Content)

**Tier 2 ASINs (3–5 more, for breadth):**
- Ranked slightly below your Tier 1 picks
- Products with a different positioning angle in the same category
- Products appearing in "Frequently Bought Together" carousels with Tier 1

**How to find them fast:** Install the Helium 10 Chrome Extension. On any Amazon search page, the ASIN Grabber tool extracts all visible ASINs in one click with their BSR, price, review count, and rating. Copy candidates directly into Cerebro.

---

### Step 2: Run the Cerebro Search

1. Open Cerebro from the Helium 10 dashboard (Keyword Research section)
2. Confirm the marketplace — flag icon, top right of search bar
3. Paste ASINs one at a time (up to 10 per search)
4. Click **Get Keywords** — allow 30–90 seconds for large batches

**Single ASIN vs. Multi-ASIN:**
- **Single ASIN:** Deep dive on one competitor's full keyword strategy. Best for your most direct head-to-head competitor.
- **Multi-ASIN (3–10):** Surfaces keywords multiple competitors rank for simultaneously — these are the category's non-negotiable core keywords. Use the **Ranking Competitors** filter to find them.

---

### Step 3: Standard Filters for New Listings

Run this filter set first. It takes thousands of results down to 50–200 high-quality targets.

| Filter | Recommended Setting | Reason |
|--------|--------------------|----|
| Search Volume (min) | 300 | Cuts noise. Below 300/month rarely drives meaningful traffic. |
| Organic Rank (max) | 30 | Focus on keywords competitors actually rank well for — proven convertible. |
| Competing Products (max) | 5,000 | Keeps targets achievable without heavy PPC spend. |
| Cerebro IQ Score (min) | 40 | Demand/competition balance filter. |
| Word Count (min) | 2 | Removes single broad head terms (e.g., "knife") that are near-impossible to rank for cold. |

Apply together. Export this filtered set — it's your **core keyword list**.

---

### Step 4: The Advanced Rank Filter — Finding Hidden Gems

The standard filters miss a critical segment: keywords where only 1–3 competitors rank well, but the keyword has real demand. These are underexploited opportunities with low competition.

**Setup:**
1. Remove the standard Organic Rank filter
2. Scroll to **Advanced Rank Filter** section
3. **Filter 1:** Min ASINs = 1, Max ASINs = 3 (keywords only a few competitors use)
4. **Rank Range:** 1–20 (must be ranking well for it, just few doing so)
5. Keep Search Volume min at 300+
6. Click Apply

These results show keywords where 1–3 of your 10 input ASINs rank on page 1 while everyone else ignores them. These go into your **opportunity keyword list** — backend search terms and exact match PPC campaigns first, then work toward organic rank.

**Helium 10's recommended baseline (multi-ASIN searches):**
- Search Volume: 1,000+
- Position Rank: 1–25
- Ranking Competitors: minimum 4

Adjust based on your category's average competition level.

---

### Step 5: Keyword Segmentation

After filtering, categorize your results into four buckets:

**Category A — Core Keywords (Must Have)**
High volume (1,000+), multiple competitors ranking organically, directly describe the product.
*→ Title placement. You cannot launch without these.*
Example: "chef knife", "8 inch chef knife", "kitchen knife"

**Category B — Modifier Keywords (Differentiators)**
Medium volume (300–1,000), describe a specific attribute, material, or feature.
*→ Bullets 1–3 and backend search terms.*
Example: "german steel chef knife", "full tang knife", "professional kitchen knife"

**Category C — Long-tail / Buyer-Intent Keywords**
Lower volume (50–300) but high purchase intent. Often describe a use case or buyer problem.
*→ Bullets 4–5, product description, and backend.*
Example: "knife for cutting through bone", "chef knife that holds an edge", "knife with sheath"

**Category D — Opportunity Keywords**
Found via Advanced Rank Filter. Low competition, specific.
*→ Backend first, then exact match PPC, then push to organic.*
Example: "german chef knife with wooden handle", "8 inch kitchen knife with sheath"

---

### Step 6: Use Word Frequency

After filtering, open the **Word Frequency** panel in Cerebro results. This shows every individual word across all results, ranked by how many times it appears.

**What it tells you:**
The highest-frequency words are the fundamental vocabulary of your category. If "stainless" appears 847 times and "carbon" appears 12 times, buyers in this category are overwhelmingly searching for stainless steel products — not carbon steel. This shapes both keyword selection and copy direction.

Export word frequency data separately. It feeds directly into Frankenstein.

---

### Step 7: Export

Click **Export → CSV**. Save per-ASIN-batch. You'll combine in Frankenstein.

Name files clearly: `cerebro-asin1-B07XYZ.csv`, `cerebro-batch-5asins.csv`

---

## Phase 2 — Seed Expansion with Magnet

### What Magnet Does
Cerebro looks backward (what are competitors ranking for?). Magnet looks outward — it takes a seed keyword and generates every related variation, synonym, and long-tail phrase Amazon's database has indexed. It finds demand that competitors haven't captured yet.

---

### Step 1: Choose Seed Keywords

Start with 5–10 seeds per research session. Good seed types:

1. **Core product noun:** "chef knife", "resistance band", "protein powder"
2. **Use-case descriptor:** "knife for cutting meat", "band for pull-up assist"
3. **Buyer-type descriptor:** "professional chef knife", "beginner yoga mat"
4. **Material/feature descriptor:** "german steel knife", "latex free resistance band"
5. **Problem-descriptor:** "knife that stays sharp", "non-slip yoga mat"

Run each seed separately to see different result clusters.

---

### Step 2: Run Magnet — Find Suggestions Mode

1. Open Magnet → **Find Suggestions** tab
2. Select your marketplace
3. Enter one seed keyword
4. Click **Get Keywords**

Results load with all variations, related terms, and smart-complete phrases Amazon has indexed.

---

### Step 3: Apply Magnet Filters

| Filter | Recommended Setting | What It Does |
|--------|--------------------|----|
| Search Volume (min) | 300 | Cuts low-volume noise |
| Magnet IQ Score (min) | 60 | High-opportunity demand/competition ratio |
| Competing Products (max) | 5,000 | Keeps results targetable |
| Word Count (min) | 2 | Removes single head terms |
| Title Density (max) | 7 | Finds keywords page-1 competitors haven't saturated in titles |
| Search Volume Trend | Positive | Rising keywords — capture before saturation |

**For opportunity hunting specifically:** Set Magnet IQ Score to 60+, Competing Products under 200, Search Volume 300+. This surfaces the sweet spot — real demand, low competition.

---

### Step 4: Analyze Keywords Mode (for a list you already have)

After you've built a preliminary keyword list from Cerebro, paste it into Magnet's **Analyze Keywords** tab (up to 200 keywords at a time).

Magnet returns volume, trend, title density, and IQ score for each keyword simultaneously. This lets you quickly rank-order a large keyword list without running each one individually.

**Use this to:**
- Validate Cerebro keywords before committing them to your listing
- Spot which of your current keywords have declining trends (worth swapping)
- Compare competing products count across your whole list at once

---

### Step 5: Mine Smart Complete

Magnet's **Smart Complete** match type surfaces phrases Amazon's algorithm associates with your seed keyword — phrases that Amazon completes in autocomplete when buyers start typing. These are high-intent phrases because they represent actual search behavior.

Filter by Match Type → Smart Complete to isolate these.

---

### Step 6: Check Amazon Choice Filter

Enable the **Amazon's Choice Only** filter to see keywords where an Amazon's Choice badge is active. These keywords have:
- Clear commercial intent
- A product Amazon itself is promoting
- High conversion rates (that's why Amazon chose it)

If you can rank for Amazon's Choice keywords, you can earn the badge yourself — significant conversion boost.

---

### Step 7: Export

Export Magnet results as CSV. Keep separate from Cerebro exports — you'll combine in Frankenstein but want to know which source each keyword came from.

---

## Phase 3 — Cleaning with Frankenstein

### What Frankenstein Does
Takes your raw combined keyword lists (potentially 3,000–10,000 terms from Cerebro + Magnet runs) and turns them into a clean, deduplicated, frequency-ranked master list ready for listing deployment.

Without Frankenstein, you'd spend hours manually cleaning spreadsheets. With it, the same process takes under 5 minutes.

---

### Step 1: Import Your Raw Keywords

1. Open Frankenstein from the Helium 10 dashboard
2. Paste all keywords from your Cerebro and Magnet exports into the input box
3. One keyword phrase per line (or comma-separated — Frankenstein handles both)
4. For large batches (5,000+ keywords): paste in sections

---

### Step 2: Select Processing Options

**Always enable:**
- ☑ **Remove duplicates** — eliminates exact repeats
- ☑ **Convert to lowercase** — normalizes case for deduplication
- ☑ **One word/phrase per line** — required format for Scribbles import
- ☑ **Include word frequency count** — shows which individual words appear most often across all phrases (critical for understanding what Amazon's algorithm sees as core to your category)

**Situationally enable:**
- ☑ **Remove common words** — removes "the", "a", "for", "with" when you need a pure keyword token list
- ☑ **Remove single-letter words** — clean up stray characters
- ☐ **Remove numbers** — leave unchecked if size/count numbers are keywords (e.g., "8 inch", "3 pack")

**Sort options:**
- **Sort by frequency (high to low):** Shows you which individual words appear most across all phrases — these are your highest-priority keyword roots
- **Alphabetical:** Better for manual review of a processed list

---

### Step 3: Read the Word Frequency Output

After processing, click the **Frequency** tab. This ranks every individual word by how many times it appeared across all input phrases.

**How to use it:**
- The top 10–15 words are your category's keyword DNA — they need to be in your title
- Words that appear 10+ times are almost certainly indexing targets
- Words that appear only 1–2 times across thousands of phrases are niche or spurious — lower priority

Copy the top 30 words + their frequency counts into your keyword planning spreadsheet. This is the most distilled intelligence Helium 10 produces.

---

### Step 4: Export the Processed List

Export the cleaned list as `.txt`. You can also:
- **Send directly to Scribbles:** Click the Scribbles button at bottom right of Frankenstein. Up to 1,000 phrases transfer directly. *Note: Frankenstein has a 1,000-phrase limit to Scribbles — filter your list to the best 1,000 before sending.*
- **Copy to clipboard:** For manual pasting into Scribbles or a spreadsheet
- **Save to My List:** Save the processed keyword list to Helium 10's My Lists for future reference and tracking

**If your filtered list exceeds 1,000 keywords:** Sort by IQ Score or search volume and take the top 1,000. The marginal keyword #1,001 rarely justifies the additional complexity.

---

## Phase 4 — Listing Build with Scribbles

### What Scribbles Does
Scribbles is a listing editor that imports your keyword list and tracks whether each keyword has been used as you write. Keywords move from "unused" to "used" as you incorporate them into title, bullets, description, and search terms. Color-coding shows priority by search volume.

The goal: build the highest-converting copy that also covers your full priority keyword list. No keyword left behind accidentally.

---

### Step 1: Import Keywords

1. Open Scribbles from the Helium 10 dashboard
2. **Option A:** Import from My List → select your saved Frankenstein output
3. **Option B:** Paste keywords directly into the left panel
4. **Option C:** Import from Frankenstein → click Scribbles button in Frankenstein (transfers up to 1,000)
5. Click **Apply** — Scribbles sorts keywords by search volume and color-codes them

**Color coding:**
- 🔴 Red: Highest search volume — must use
- 🟡 Yellow: Medium volume — use where natural
- ⚪ White: Lower volume — use in backend if not fitting naturally elsewhere

---

### Step 2: Import Existing Listing (for optimization)

If you're optimizing an existing listing (not building from scratch):
1. Click **Import Existing Listing**
2. Paste the product ASIN
3. Scribbles pulls in your current title, bullets, description, and search terms
4. Your existing copy populates the editor fields
5. Keywords already used move to the "used" column automatically

This lets you see which of your target keywords are missing from your current listing without starting from scratch.

---

### Step 3: Write the Listing — Field by Field

Work through each field in order. The left panel shows remaining unused keywords. The right panel is your listing editor.

**Title first:**
- Start with your 2–3 highest-volume core keywords (Category A from Cerebro)
- Build a natural-reading title around them — not a keyword string
- Check character count as you type — Scribbles shows it in real time
- First 80 characters are the mobile display cutoff — all critical keywords must be here

**Bullets next (1–5):**
- Bullet 1: highest-impact benefit tied to your #2 and #3 keywords
- Bullets 2–4: Feature → spec → benefit structure, working through Category B keywords
- Bullet 5: Use case, compatibility, or warranty — Category C and D keywords

**Description:**
- Long-tail keywords, conversational phrases, use-case scenarios
- Amazon indexes this field but weights it less than title/bullets
- Aim to use remaining medium-priority keywords here naturally

**Search Terms (Backend):**
- Everything unused that doesn't fit naturally in copy
- Misspellings, synonyms, foreign language terms
- Hard 250-byte limit — Scribbles tracks byte count in real time

**Subject Matter fields (if available):**
- Additional keyword fields Amazon indexes but doesn't display
- Use for overflow keywords that don't fit in search terms

---

### Step 4: Track Coverage

As you write, watch the left panel. Move through keywords systematically:
- Red keywords (high volume): if you can't naturally fit one, force a slight rewrite to accommodate it — these drive the most traffic
- Yellow keywords: fit where natural in bullets and description
- White keywords: backend search terms if they don't flow naturally into copy

**Target: 0 red keywords unused when you finish.**

---

### Step 5: Export the Completed Listing

When done:
- **Export listing:** Downloads a file with all fields populated — use as your flat file input
- **Export used/unused report:** Shows which keywords made it in and which didn't — important for your ongoing tracking
- **Save to Amazon (if integrated):** Scribbles can push directly to Seller Central for connected accounts

---

## Phase 5 — Rank Monitoring with Keyword Tracker

### What Keyword Tracker Does
After your listing is live, Keyword Tracker monitors your organic rank for each target keyword on a daily basis (up to 24 times per day on Diamond plan). It shows rank trends over time, alerts you to significant drops, and lets you measure the impact of listing changes.

---

### Step 1: Set Up Tracking

1. Open Keyword Tracker from the dashboard
2. Click **Add Keywords**
3. Import from **My List** or paste your target keywords manually
4. Set the ASIN to track
5. Select tracking frequency (daily is standard; higher frequency available on Diamond)

Start tracking **before** you optimize the listing — you need a baseline to measure change against.

---

### Step 2: Prioritize Which Keywords to Watch Closely

You don't need to stare at every keyword daily. Set alert thresholds for:

**Critical keywords (check weekly):**
- Your top 5–10 highest-volume Category A keywords
- Any keyword you rank in the top 10 for — drops here cost real revenue

**Growth keywords (check bi-weekly):**
- Keywords where you rank 11–30 — these are your "almost there" opportunities
- Small rank improvements here can move you to page 1

**PPC validation keywords (check after campaign changes):**
- Keywords you're actively running ads against — watch for organic rank improvement as PPC drives conversions

---

### Step 3: Interpret Rank Movement

| Signal | What It Means |
|--------|--------------|
| Sudden rank drop (10+ positions overnight) | Possible listing suppression, competitor launched PPC against your keyword, or Amazon algorithm shift |
| Gradual rank improvement over 2–4 weeks | Organic listing optimization working — conversions accumulating |
| Rank stuck at position 15–30 | Need PPC support or higher conversion rate to push through |
| Rank improving on PPC but not organic | PPC is driving traffic but conversion rate isn't strong enough for Amazon to reward organic rank |
| Rank drops when PPC paused | Keyword is PPC-dependent — listing copy needs strengthening |

---

### Step 4: Ongoing Research Cadence

| Frequency | Action |
|-----------|--------|
| **Weekly** | Check Keyword Tracker for rank changes on top 10 keywords |
| **Monthly** | Run Magnet on your top keywords to check for rising trend variations |
| **Quarterly** | Full Cerebro refresh on top 5 competitors — new products enter the market, keyword strategies evolve |
| **Seasonally** | Before peak season (Q4, Prime Day), add seasonal keywords identified by Search Volume Trend data |
| **After listing changes** | Track rank before/after — 2–4 weeks for Amazon to index and reflect changes |

---

## Complete Workflow End-to-End

Here is the exact sequence for a new listing keyword research session. Total time: 2–4 hours for a thorough job.

### Session 1: Research (90–120 minutes)

**Step 1 — Competition mapping (30 min):**
1. Search your main keyword on Amazon
2. Use ASIN Grabber (Chrome Extension) to grab ASINs from the top 15 results
3. Select 5 Tier 1 ASINs and 3 Tier 2 ASINs per criteria above
4. Note: price range, review counts, BSR, positioning angle of each

**Step 2 — Cerebro batch run (30 min):**
1. Run all 8 ASINs together in one Cerebro search
2. Apply standard filters (SV 300+, Organic Rank ≤30, Competing Products ≤5,000, IQ ≥40)
3. Export filtered results as CSV
4. Re-run with Advanced Rank Filter (2–3 ASINs ranking 1–20)
5. Export that set separately
6. Note Word Frequency top 20 words

**Step 3 — Magnet seed expansion (30 min):**
1. Run 5 seed keywords through Magnet individually
2. Apply Magnet filters (SV 300+, IQ 60+, Competing Products ≤5,000)
3. Export each filtered set
4. Run your combined list through Magnet's Analyze Keywords tab for validation

**Step 4 — Frankenstein cleaning (15 min):**
1. Paste all Cerebro and Magnet exports into Frankenstein
2. Enable: Remove duplicates, Lowercase, One per line, Word Frequency
3. Sort by frequency
4. Export processed list
5. Save to My Lists

---

### Session 2: Listing Build (60–90 minutes)

**Step 5 — Keyword tiering (20 min):**
1. Open processed list
2. Tag each keyword: Category A / B / C / D per criteria above
3. Plan title structure around your top 3 Category A keywords
4. Map Category B keywords to bullet slots 1–3
5. Map Category C to bullets 4–5 and description

**Step 6 — Scribbles build (40–60 min):**
1. Import keyword list into Scribbles
2. Write title first — target 80–160 characters depending on category
3. Write 5 bullets — apply humanizer check as you go (no AI vocabulary, no -ing clauses, specs over adjectives)
4. Write description — long-tail keywords, use cases, conversational
5. Fill backend search terms — stay under 250 bytes
6. Verify: zero red keywords unused
7. Export completed listing

**Step 7 — Set up tracking:**
1. Add top 20–30 keywords to Keyword Tracker
2. Note baseline ranks before listing goes live
3. Set alerts for drops on top 10 keywords

---

## Filter Recipes by Goal

Specific filter combinations for specific situations:

### "I need to launch a new product into a competitive category"
**Cerebro:**
- Search Volume: 500–8,000 (avoid massive head terms)
- Organic Rank: 1–20
- Competing Products: max 3,000
- Cerebro IQ: min 50
- Word Count: min 2
*Focus on keywords where you can realistically rank within 90 days*

### "I want to find keywords my competitors are sleeping on"
**Cerebro — Advanced Rank Filter:**
- Advanced Filter: 1–3 ASINs ranking in positions 1–20
- Search Volume: 300+
- Competing Products: max 2,000
*Keywords that are real demand with no dominant competitor*

### "I'm optimizing an existing listing that's stalled"
**Cerebro on your own ASIN:**
- Your ASIN + top 3 competitors
- Competing Products filter: look for keywords where competitors rank 1–10 but you rank 30+
- These are the keyword gaps — your listing is indexed but converting poorly on them
*Fix: strengthen the listing sections where these keywords appear + run targeted PPC*

### "I want to find rising trend keywords before saturation"
**Magnet:**
- Search Volume Trend: positive (last 30 days)
- Search Volume: 200+ (still early stage)
- Competing Products: max 2,000
- Title Density: max 3 (nobody's put it in their title yet)

### "I need backend search terms fast"
**Magnet — run main keyword:**
- Word Count: min 3 (long-tail phrases)
- Title Density: 0–2 (not in any competitor title)
- Search Volume: 50–300 (below what you'd target organically)
- Match Type: Smart Complete + Organic
*These are the terms nobody is consciously targeting but buyers search — perfect for backend*

---

## Keyword Tiering and Placement

The placement hierarchy directly affects ranking weight. Higher-priority placements get more algorithmic credit.

### Tier 1 — Title (Highest Weight)
**What goes here:** 2–3 highest-volume core keywords that directly describe the product.
**Rules:**
- First 80 characters display on mobile — all critical terms must fit here
- Keywords must read naturally — not a keyword string
- Brand name first (unless private label just entering the market)
- No repetition — each keyword appears once

### Tier 2 — Bullets 1–3 (High Weight)
**What goes here:** Secondary keywords woven into benefit/feature statements.
**Strategy:**
- Bullet 1: The highest-converting benefit — your #2 keyword prominent
- Bullet 2: Key differentiating feature — material, spec, certification
- Bullet 3: Use case keyword + supporting spec

### Tier 3 — Bullets 4–5 + Description (Medium Weight)
**What goes here:** Long-tail keywords, use-case phrases, buyer-type keywords.
**Strategy:**
- Bullet 4: Secondary use case or compatibility keyword
- Bullet 5: Trust signal (warranty, certifications) + remaining Category C keywords
- Description: Conversational long-tail phrases, question-format keywords, scenario-based copy

### Tier 4 — Backend Search Terms (Indexed, Not Displayed)
**What goes here:** Everything that didn't fit naturally in visible copy.
- Misspellings of product and brand names
- Foreign language equivalents (Spanish, German, French — depending on marketplace)
- Abbreviations and acronyms
- Synonyms not already in copy
- Size/color variants not mentioned above
- Related use-case terms
**What does NOT go here:**
- Words already in your title or bullets (wasted bytes)
- Competitor brand names
- Prohibited terms: "best", "cheap", "free", "#1"
- Your own brand name (already indexed)

### Byte Count for Backend
`generic_keywords` limit is 250 **bytes**, not characters.
- Standard ASCII characters: 1 byte each
- Accented characters (é, ñ, ü): 2 bytes each
- Safe practice: keep backend keywords under 200 characters to ensure you never hit the byte ceiling
- If you exceed 250 bytes, Amazon silently ignores ALL backend terms — not just the overflow

---

## Backend Search Terms — Rules and Tactics

### The 250-Byte Rule (Critical)
Amazon silently ignores ALL backend keywords if you exceed 250 bytes. There's no error message. You won't know. Your terms just stop working.

**Verification:** After uploading, wait 48–72 hours and use Helium 10's Index Checker to confirm your backend terms are indexed.

### What to Include
1. Spelling variations of your product name: "colagen" for "collagen", "resistence" for "resistance"
2. Common misspellings of brand name
3. Synonyms not in visible copy: "chef's knife" if you used "chef knife" in title
4. Foreign language terms relevant to your market:
   - Spanish equivalents for US market (large Spanish-speaking buyer segment)
   - German terms if selling EU
5. Abbreviations: "USB-C" and "USBC", "stainless" and "SS"
6. Related product terms: "knife for steak", "carving knife" (if your chef knife works for carving)

### What to Exclude
- Words already anywhere in title, bullets, or description
- Your own brand name (Amazon auto-indexes it)
- Competitor brand names (policy violation — can trigger suppression)
- "Amazon's Choice", "best seller", "top rated"
- "Free", "cheap", "sale", "discount"
- HTML tags or special characters

### Format
No commas needed. Amazon tokenizes space-separated terms:
`german stainless steel knife cuchillo acero inoxidable kochen messer sharp blade full tang`

---

## Misspellings and Non-English Keywords

### Why Misspellings Matter
Amazon buyers don't always spell correctly. Amazon's autocomplete sometimes doesn't correct these searches, meaning the misspelled keyword returns different (less competitive) results. Helium 10's **Misspellinator** tool generates common misspellings systematically.

**Never put misspellings in:**
- Title
- Bullets
- Description

**Always put misspellings in:**
- Backend search terms only

Examples of high-value misspelling targets:
- "colagen" → "collagen"
- "diper" → "diaper"
- "excersise" → "exercise"
- "protien" → "protein"

### Non-English Keywords (US Marketplace)
The US marketplace has tens of millions of Spanish-speaking buyers. Spanish-language keywords in your backend search terms index for Spanish searches.

Standard practice for relevant products:
- Run your top 5 keywords through Google Translate → add Spanish equivalents to backend
- Focus on product nouns and descriptors, not full phrases

Example: "chef knife" backend additions: `cuchillo de chef cuchillo cocina cuchillo profesional`

---

## New Listing vs. Existing Listing Research

### New Listing (No Sales History)
**Priority:** Finding keywords you can rank for — not just keywords that exist.
**Approach:**
1. Cerebro on 3–5 mid-tier competitors (not the top sellers)
2. Filter: Competing Products max 3,000, IQ min 50, Organic Rank ≤20
3. Focus on Category B and C keywords initially — head terms are too competitive to win cold
4. Plan PPC campaigns around exact match on Category A keywords to build initial rank
5. Target 15–20 keywords total for your launch listing

**Realistic ranking timeline:**
- Low-competition keywords (Competing Products < 1,000): visible rank within 2–4 weeks
- Medium-competition (1,000–5,000): 4–12 weeks with consistent PPC support
- High-competition (5,000+): 3–6 months minimum

### Existing Listing (Needs Optimization)
**Priority:** Finding keyword gaps and fixing underperformance.
**Approach:**
1. Run Cerebro on your own ASIN first — see where you currently rank
2. Run Cerebro on your top 3–5 competitors
3. Cross-reference: find keywords competitors rank 1–10 for that you rank 20–50+ for
4. These gaps are your optimization targets — your listing is indexed but not converting on these terms
5. Identify which listing field those keywords should be in and strengthen that section

**Key question for each gap keyword:** *Is this keyword in my title/bullets and I'm not converting — or is it not in my listing at all?*
- Not in listing: add it in the appropriate field
- In listing but poor rank: conversion rate issue — improve images, price, reviews, or copy for that section

---

## PPC Keyword Alignment

Keyword research informs both organic and paid strategy. The two should be aligned, not siloed.

### The Keyword → PPC → Organic Flywheel
1. Run broad match PPC campaigns against your target keywords
2. Harvest converting keywords from Search Term Reports in Seller Central
3. Keywords with proven conversion history at low ACoS → move to exact match PPC + prioritize in organic listing
4. As organic rank improves for a keyword → reduce PPC bid (you're getting organic visibility for free)
5. Keyword ranking organically in top 3 → pause PPC for that keyword, reallocate budget

### Using Cerebro's Sponsored Rank Data
Cerebro shows you where competitors are running paid ads. A competitor with:
- **High sponsored rank, no organic rank:** They're paying to be visible but haven't earned organic position — potentially vulnerable to organic strategy
- **High organic rank, low sponsored rank:** Strong organic player — not defending with PPC — potentially lower PPC competition for those keywords
- **High organic AND sponsored rank:** Dominant player defending their position — expensive to compete head-on, look for flanking keywords

### Suggested PPC Bids
Cerebro returns suggested PPC bid ranges for each keyword. Use these for:
- **Budget planning:** Estimate monthly PPC spend across your target keyword list
- **Prioritization:** High bid = high competition = may need organic rank before PPC is cost-effective
- **New keyword discovery:** Keywords with bid data but no current competitor PPC activity = potential low-cost traffic opportunity

---

## Common Mistakes

### Mistake 1: Using Only Magnet or Only Cerebro
Magnet finds potential. Cerebro finds proven. You need both. Magnet without Cerebro produces a keyword list full of terms nobody has validated convert. Cerebro without Magnet misses demand that competitors haven't captured.

### Mistake 2: Not Deduplicating Before Scribbles
Pasting raw Cerebro and Magnet exports directly into Scribbles (skipping Frankenstein) results in duplicate keywords inflating the "unused" count and obscuring actual coverage. Always clean through Frankenstein first.

### Mistake 3: Repeating Keywords Across Listing Fields
If a keyword is in your title, don't put it in your backend. Amazon doesn't give additional weight for repetition — it's wasted character count. The Index Checker tool can confirm you're indexed for a term without it appearing multiple times.

### Mistake 4: Exceeding the 250-Byte Backend Limit
The consequence is silent and total: all backend terms ignored. Always verify using Helium 10's Index Checker after upload. If your terms aren't indexed 72 hours post-upload, check your byte count first.

### Mistake 5: Static Keyword Research
Keyword data goes stale. Trends shift, new competitors enter, seasonal patterns emerge. Quarterly Cerebro refreshes and monthly Magnet trend checks are minimum maintenance for a live listing. Set a calendar reminder.

### Mistake 6: Targeting Only High-Volume Head Terms
Head terms ("yoga mat", "chef knife") are searched millions of times and fought over by thousands of sellers with thousands of reviews. New listings rarely rank for them organically. Target modifier and long-tail keywords first — build sales history — then let that velocity push you toward head term ranking.

### Mistake 7: Ignoring the Scribbles "Unused" Column
The unused keyword list in Scribbles is a direct action item, not a report to archive. Every red keyword unused is a missed traffic opportunity. If a high-volume keyword doesn't fit naturally into copy, rewrite the copy until it does.

### Mistake 8: Assuming Rank = Revenue
A keyword ranking at position 7 for "german steel chef knife" generates more revenue than ranking at position 2 for "best knife ever" (a low-volume vanity keyword). Prioritize keywords with high search volume AND high relevance to your specific product. Relevance determines conversion rate; volume determines traffic ceiling.
