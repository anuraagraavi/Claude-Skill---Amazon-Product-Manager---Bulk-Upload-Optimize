# Amazon Store Manager — Claude Skill

A Claude skill for building, optimizing, and managing Amazon product listings. Covers flat file bulk uploads, keyword research, SEO-optimized copy, category compliance, and conversion rate optimization — with the humanizer system built in so every listing output sounds like it was written by a person who actually knows the product.

---

## What This Skill Does

When you activate this skill, Claude becomes an expert Amazon Store Manager. You can ask it to:

- **Write optimized listings** — title, 5 bullets, description, backend search terms — from a product brief or URL
- **Build flat file bulk upload sheets** — with correct formatting, field values, and variation structure
- **Set up parent-child variation listings** — Color, Size, SizeColor, Flavor, and other themes
- **Troubleshoot flat file errors** — paste an error code and get a specific fix
- **Run keyword strategy** — tell Claude your product and it will structure a full keyword tiering plan (Tier 1 title keywords → Tier 4 backend misspellings)
- **Check category compliance** — gated/ungated status, certification requirements, prohibited claims
- **Audit existing listings** — spot humanizer violations, missing keywords, policy issues
- **Guide Helium 10 workflows** — step-by-step Cerebro → Magnet → Frankenstein → Scribbles process

---

## What Makes This Different

Most Amazon listing tools produce copy that sounds like it was assembled rather than written. You can spot it immediately: "premium quality," "crafted with precision," "elevating your experience" — words that mean nothing to a buyer who's choosing between 50 similar products.

This skill includes a full implementation of the **humanizer system** — a 24-pattern framework for removing AI-generated language from listing copy. Every title, bullet, and description the skill produces is checked against:

- Significance inflation ("testament to," "pivotal moment")
- Vague promotional language ("premium," "innovative," "groundbreaking")
- Fake depth (-ing clauses that add no fact)
- AI vocabulary clusters ("additionally," "showcase," "vibrant," "intricate")
- Copula avoidance ("serves as," "stands as," "boasts")
- Generic conclusions ("elevate your lifestyle," "transform your routine")
- And 18 more patterns — with Amazon-specific before/after examples for each

The result is copy that actually sounds like it came from someone who knows the product. Specific. Direct. Believable.

---

## Skill Structure

```
amazon-store-manager/
├── SKILL.md                          # Main skill file — load this
└── references/
    ├── category-rules.md             # Compliance rules by category
    ├── flat-file-columns.md          # Every flat file column explained
    ├── helium10-keyword-research.md  # Full Helium 10 workflow (Cerebro → Scribbles)
    ├── humanizer-amazon.md           # 24-pattern humanizer guide for Amazon copy
    ├── keyword-research-methodology.md  # Manual keyword research (no tools needed)
    └── seo-formulas.md               # Title formulas and keyword placement by category
```

### File Guide

**`SKILL.md`** — The main skill definition. Contains:
- A10 algorithm ranking factors
- Listing anatomy (character limits, 2025 policy updates)
- Flat file system (structure, Update vs. PartialUpdate, FBA/FBM, variations, error codes)
- Category rules and compliance overview
- Keyword strategy principles
- CRO conversion hierarchy
- Account health metrics
- Workflow guides (new listings, updating existing, price/quantity)
- Full 24-pattern humanizer rules applied to Amazon copy

**`references/flat-file-columns.md`** — Every column in a standard Amazon flat file:
- Required / Conditional / Optional status
- Accepted values and character limits
- The critical difference between `Update` and `PartialUpdate`
- All common error codes with specific fixes
- FBA vs. FBM field rules

**`references/helium10-keyword-research.md`** — The complete Helium 10 keyword research workflow:
- Phase 1: Cerebro — how to pick ASINs, apply filters, use Advanced Rank Filter, export
- Phase 2: Magnet — seed expansion, filter recipes, Analyze Keywords mode
- Phase 3: Frankenstein — processing settings, word frequency analysis, Scribbles handoff
- Phase 4: Scribbles — listing build, keyword tracking, field-by-field strategy
- Phase 5: Keyword Tracker — setup, rank monitoring, ongoing cadence
- Keyword tiering (Tier 1 title → Tier 4 backend)
- Backend search term rules (250-byte limit, what's included/excluded)
- PPC alignment strategy

**`references/humanizer-amazon.md`** — Deep reference for writing human-sounding Amazon copy:
- All 24 AI writing patterns with Amazon-specific before/after examples
- Category tone calibration (Electronics, Health, Apparel, Kitchen, Automotive, Baby)
- Prohibited language (what Amazon bans) vs. Required language (what regulated categories must keep)
- The two-pass audit process
- Full transformation examples by listing field

**`references/keyword-research-methodology.md`** — For when you don't have Helium 10:
- Amazon autocomplete mining (systematic A–Z + modifier extraction)
- SERP analysis via Amazon search URL
- Competitor listing deconstruction
- Volume and competition estimation without paid tools
- Complete worked example (chef knife research session)

**`references/seo-formulas.md`** — Title formulas for every major category + keyword placement rules

**`references/category-rules.md`** — Category-specific compliance:
- Gated vs. ungated status for every major category
- Required certifications (CPC, FCC, UL, NSF, FDA compliance)
- Category-specific field requirements
- Gating approval process and common rejection reasons

---

## Installation

### Recommended (Claude Code — clone directly into skills directory)

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/YOUR-USERNAME/amazon-store-manager.git ~/.claude/skills/amazon-store-manager
```

### Manual install

```bash
mkdir -p ~/.claude/skills/amazon-store-manager/references
cp SKILL.md ~/.claude/skills/amazon-store-manager/
cp references/*.md ~/.claude/skills/amazon-store-manager/references/
```

---

## Usage

### In Claude Code

Invoke the skill directly:

```
/amazon-store-manager

I need to create a listing for a 3-piece silicone baking mat set. Material is 100% food-grade silicone, BPA-free. Comes in a set of 3 sizes (quarter sheet, half sheet, full sheet). Colors: red, grey, black. We're FBA. Price point $19.99. Main competitor ASIN: B07XYZ1234.
```

Or ask Claude directly — the skill description triggers it for any Amazon listing request:

```
Write me 5 optimized Amazon bullet points for a yoga mat. 6mm thick, non-slip, TPE material, 72"x24", carrying strap included.
```

```
I'm getting error 8541 on my flat file upload. What does that mean and how do I fix it?
```

```
Walk me through how to set up a parent-child variation listing for a t-shirt that comes in 3 colors and 5 sizes.
```

### In Claude.ai

Upload `SKILL.md` and the relevant reference files to a Claude Project, then ask:

```
Using the Amazon Store Manager skill, write an optimized listing for [product].
```

---

## Example Outputs

### Example 1: Title from a product brief
**Input:** Chef knife, 8-inch, German 1.4116 steel, full tang, pakkawood handle, with leather sheath. Competitor ASINs: B07ABC, B07DEF.

**Output:**
> `[Brand] Chef Knife 8 Inch — German 1.4116 Steel, Full Tang, Pakkawood Handle, Kitchen Knife with Leather Sheath`

95 characters. 6 keywords covered. No vague adjectives. Zero AI vocabulary.

---

### Example 2: Bullet before/after

**Before (AI-generated):**
> Crafted with precision using premium materials, our innovative full tang design showcases our commitment to culinary excellence, ensuring superior performance for the discerning home chef.

**After (skill output):**
> Full-tang blade extends through the handle to the end cap — no flex, no torque, balanced for long prep sessions. 1.4116 German steel holds an edge through 6 months of daily use without honing.

---

### Example 3: Flat file error diagnosis
**Input:** "Getting error 8541 on upload."

**Output:**
> Error 8541 means the UPC/barcode you've entered is already associated with a different ASIN in Amazon's catalog — the barcode and ASIN don't match. Three likely causes: (1) You're using a resold/duplicate barcode — Amazon requires GS1-certified barcodes purchased directly from gs1.org. (2) This exact product already has an ASIN on Amazon — you should match to that ASIN instead of creating a new one. (3) You're uploading a variation child with a barcode that was previously used on a standalone listing. Fix: verify your barcode source, check whether the product already exists in Amazon's catalog, and if it does, use "Match an Existing Listing" instead of creating a new ASIN.

---

## Coverage

| Topic | Coverage |
|-------|---------|
| A10 Algorithm | ✅ Full ranking factors |
| Title optimization | ✅ All categories, 2025 rules |
| Bullet copy | ✅ With humanizer |
| Description / A+ | ✅ |
| Backend keywords | ✅ 250-byte rules, tactics |
| Flat file: new listings | ✅ |
| Flat file: variations | ✅ Parent-child setup |
| Flat file: error codes | ✅ 10 most common errors |
| FBA vs FBM fields | ✅ |
| Keyword research (Helium 10) | ✅ Full 5-phase workflow |
| Keyword research (no tools) | ✅ Manual methodology |
| Category compliance | ✅ 12+ categories |
| Gating / approval process | ✅ |
| Humanizer (24 patterns) | ✅ Amazon-specific |
| CRO principles | ✅ |
| Account health metrics | ✅ |
| PPC alignment | ✅ |

---

## What This Skill Does Not Cover

- **Sponsored Ads campaign management** — PPC strategy beyond keyword selection
- **A+ Content / EBC layout** — The content guidelines are included, but not design templates
- **Inventory management** — Reorder points, FBA inventory planning
- **Analytics and reporting** — Sales performance analysis
- **Brand Registry setup** — Process for applying for Brand Registry
- **Amazon DSP** — Display advertising

These are outside the listing optimization scope. A natural next version could expand into PPC management.

---

## Background

Built as a structured knowledge base for Claude to act as an expert Amazon Store Manager. The skill format means Claude reads these files before responding, so every output is grounded in the actual rules of the Amazon platform — not hallucinated best practices.

The humanizer integration is intentional: AI-generated Amazon listings are identifiable to experienced buyers and Amazon moderators alike. Listings that read like humans wrote them convert better. The 24-pattern system from Wikipedia's "Signs of AI Writing" guide, fully translated to Amazon copy, is the core differentiator.

---

## Version

**v1.0.0** — Initial public release
- Full SKILL.md with 9 parts
- 6 reference files
- Helium 10 complete workflow
- Humanizer 24-pattern implementation
- Flat file column reference
- Category compliance guide

---

## License

MIT — use freely, contribute improvements, share widely.

If this skill helps you ship better Amazon listings, that's the point.
