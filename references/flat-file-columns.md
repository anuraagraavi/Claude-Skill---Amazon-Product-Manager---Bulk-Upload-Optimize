# Amazon Flat File — Universal Column Reference

This reference covers every column you will encounter across standard Amazon flat file templates.
Organized by function: identity, content, pricing, fulfillment, variations, and compliance.

---

## How to Use This Reference

When you see an unfamiliar column in a flat file template:
1. Find it in the section below
2. Check whether it is Required, Conditional, or Optional
3. Check the accepted values — Amazon rejects fields with values outside the Valid Values list
4. Check the character limit — truncation causes silent errors

**Template tabs to always read before filling:**
- **Data Definitions tab:** authoritative description of every field for that specific category
- **Valid Values tab:** dropdown-equivalent values for constrained fields (color, size type, department)
- **Example tab:** a filled-in sample row — use it to sanity-check your format

---

## Column Status Key

| Status | Meaning |
|--------|---------|
| **Required** | Must have a value or Amazon rejects the row |
| **Conditional** | Required only when certain other fields are filled (e.g., parent/child) |
| **Optional** | Recommended for discoverability but upload won't fail without it |

---

## SECTION 1: IDENTITY AND TAXONOMY

### `item_sku`
**Status:** Required
**What it is:** Your internal unique identifier for this product. Amazon uses this to match updates to existing listings.
**Rules:**
- Max 40 characters
- Alphanumeric + hyphens/underscores only
- Must be unique within your seller account
- Once created, cannot be changed without creating a new ASIN
**Naming convention:** `[BRAND]-[PRODUCT]-[VARIANT]` e.g., `MYKNIFE-CHEF8-BLK`

### `item_type`
**Status:** Required (in most templates)
**What it is:** The browse node path that tells Amazon which sub-category this product belongs to.
**How to find it:** Check the Browse Data tab in your category template → find the item_type value that best matches your product.
**Rules:** Must match exactly — case sensitive. Use the Valid Values tab.

### `feed_product_type`
**Status:** Required
**What it is:** The top-level product type for the flat file format you're using.
**Example values:** `home`, `kitchen`, `apparel`, `health_beauty`, `sports`
**Note:** This determines which columns are available and which are required. Wrong feed_product_type = upload fails or data goes to wrong fields.

### `parent_child`
**Status:** Conditional (required for variations)
**Accepted values:** `parent` | `child`
**Rules:**
- Parent rows: `parent`
- Child rows: `child`
- Standalone products (no variations): leave blank or `standalone`

### `parent_sku`
**Status:** Conditional (required for child rows)
**What it is:** The `item_sku` value of the parent row this child belongs to.
**Rule:** Must exactly match the `item_sku` in the parent row of the same file.

### `relationship_type`
**Status:** Conditional (required for child rows)
**Accepted value:** `Variation`
**Note:** Only supported relationship type in standard flat files.

### `variation_theme`
**Status:** Conditional (required for parent rows)
**What it is:** Tells Amazon which attributes differentiate the child listings.
**Common values:**
- `Size` — only size varies
- `Color` — only color varies
- `SizeColor` — both size and color vary
- `Flavor` — for food/supplements
- `Count` — quantity packs vary
- `Scent` — for beauty/home fragrance
- `Style` — for home décor, furniture
**Rule:** The variation_theme determines which child columns must be filled. If theme is `SizeColor`, every child needs both `size` and `color` populated.

---

## SECTION 2: PRODUCT IDENTIFICATION

### `external_product_id`
**Status:** Required (for new ASINs in most categories)
**What it is:** The UPC, EAN, ISBN, or other industry barcode for this specific product variant.
**Rules:**
- Must be GS1-certified (purchased from GS1.org, not resold barcodes)
- Unique to this variant — a 2-pack must have a different barcode than a 1-pack
- Parent rows: leave blank
- Child rows: each child needs its own unique barcode

### `external_product_id_type`
**Status:** Conditional (required when `external_product_id` is filled)
**Accepted values:** `UPC` | `EAN` | `GTIN` | `ISBN` | `ASIN`
**Note:** For existing ASINs you're adding to your catalog (reselling), use `ASIN` here and put the ASIN in `external_product_id`.

### `update_delete`
**Status:** Required for upload operations
**The most important column in the flat file.**
**Accepted values:**
- `Update` — overwrites ALL fields in the row. Any blank cell wipes existing data.
- `PartialUpdate` — only updates cells that have values. Blank cells leave existing data untouched.
- `Delete` — removes the listing (use with extreme caution)

**Default rule:** Always use `PartialUpdate` unless you are doing a complete listing overwrite. `Update` on a row with empty cells WILL delete data from your live listing.

---

## SECTION 3: LISTING CONTENT

### `item_name`
**Status:** Required
**What it is:** The product title that appears on the detail page.
**Character limits:**
- General: 200 characters max
- Electronics: 150–200 characters
- Clothing/Apparel: 80–150 characters
- Some categories: 80 characters
**2025 enforcement rules:**
- Special characters banned in titles: `!`, `$`, `?`, `~`
- Pipe character `|` and forward slash `/` still allowed as separators
- All-caps words prohibited (except acronyms)
- Repeated words limited — Amazon auto-corrects and may truncate
- First 80 characters display on mobile — load your primary keywords here

### `bullet_point1` through `bullet_point5`
**Status:** Optional (strongly recommended)
**What they are:** The 5 feature bullets displayed under "About this item."
**Character limit:** 250 characters each (some categories 200)
**Total indexed:** approximately the first 1,000 characters across all bullets
**Rules:**
- No promotional phrases: `sale`, `% off`, `free shipping`
- No claims starting with `#1` or `best` without a verified badge
- No ALL CAPS words
- No HTML tags
- No pricing, shipping, or seller contact information
- No questions or exclamation points as sentence endings
- No emojis
**Format:** Sentence case. End without punctuation (Amazon convention — not enforced but standard).

### `product_description`
**Status:** Optional (Brand Registry members use A+ Content instead)
**Character limit:** 2,000 characters
**Allowed:** Plain text, basic punctuation
**Not allowed:** HTML tags, markdown, line breaks (Amazon ignores them)
**Note:** If you have Brand Registry, this field is largely replaced by A+ Content. Still fill it for non-Brand-Registry fallback.

### `generic_keywords` (Backend Search Terms)
**Status:** Optional (but extremely valuable)
**Character limit:** 250 bytes HARD LIMIT
**Critical notes:**
- 250 bytes ≠ 250 characters. Non-ASCII characters (accents, special chars) consume multiple bytes. Stay under 200 characters to be safe.
- Exceeding 250 bytes causes Amazon to IGNORE ALL backend terms silently.
- No commas needed — Amazon parses space-separated terms
- Do NOT repeat words already in your title, bullets, or description
- Do NOT include competitor brand names
- DO include: common misspellings, synonyms, foreign language equivalents, abbreviations
**Format:** `word1 word2 phrase three long tail keyword variant`

### `subject_matter` (Subject Keywords — some templates)
**Status:** Optional
**What it is:** Additional keyword fields (5 slots in some templates) that Amazon indexes but doesn't display.
**Useful for:** Overflow keywords that didn't fit in `generic_keywords`.
**Character limit:** 50 characters per field.

---

## SECTION 4: PRICING

### `standard_price`
**Status:** Required
**What it is:** The regular selling price.
**Format:** Numeric only — no currency symbols. `29.99` not `$29.99`
**Rule:** Must be a positive number. For variations, each child SKU can have its own price.

### `sale_price`
**Status:** Optional
**What it is:** The sale/discounted price. Displays as a strikethrough with original price shown.
**Rules:**
- Must be lower than `standard_price`
- `sale_price_start_date` and `sale_price_end_date` must also be populated when using sale price
- Date format: `YYYY-MM-DD`

### `quantity`
**Status:** Conditional
**Rules:**
- **FBM sellers:** Required. Set to actual inventory count.
- **FBA sellers:** Leave blank. FBA manages inventory separately.
- **FBA note:** Setting quantity on an FBA listing confuses inventory management — leave it empty.

---

## SECTION 5: FULFILLMENT

### `fulfillment_center_id`
**Status:** Conditional
**FBA value:** `AMAZON_NA` (North America)
**FBM value:** Leave blank
**Other marketplace FBA values:**
- Europe (UK, DE, FR, IT, ES): `AMAZON_EU`
- Japan: `AMAZON_JP`
- Australia: `AMAZON_AU`

### `handling_time`
**Status:** Optional (FBM sellers should fill this)
**What it is:** Business days between order and ship date for FBM.
**Recommended values:** `1` or `2` — longer handling times hurt conversion and Buy Box eligibility.

### `merchant_shipping_group_name`
**Status:** Optional
**What it is:** Maps to a shipping template in Seller Central.
**Use:** If you've set up custom shipping templates (free shipping, expedited options), reference the template name here.

---

## SECTION 6: IMAGES

### `main_image_url`
**Status:** Required for new listings
**Rules:**
- Must be a publicly accessible URL (HTTP/HTTPS)
- White or pure white background (#FFFFFF) — no exceptions for main image
- Product must fill 85%+ of the frame
- No text, logos, watermarks, borders, or lifestyle props in main image
- Minimum 1,000px on shortest side (2,000px+ recommended for zoom)
- JPEG preferred; PNG, GIF, TIFF accepted

### `other_image_url1` through `other_image_url8`
**Status:** Optional
**What they are:** Secondary images (lifestyle shots, detail views, infographics, packaging).
**Rules:**
- Can include lifestyle imagery, text overlays, comparison charts
- No white background required
- Same size requirements as main image
- Order matters — `other_image_url1` displays first after main

---

## SECTION 7: PRODUCT ATTRIBUTES (Common Fields)

### `brand_name`
**Status:** Required
**Rules:**
- Must match your brand registration if you have Brand Registry
- Max 50 characters
- No special characters

### `manufacturer`
**Status:** Optional (required in some categories)
**Distinction:** `brand_name` = the brand. `manufacturer` = the company that made it. Can be the same or different.

### `color`
**Status:** Conditional (required when `variation_theme` includes Color)
**Rules:**
- Use Amazon's standard color names from the Valid Values tab
- Non-standard colors get normalized by Amazon: `Midnight` becomes `Black`
- For variations, each child must have a distinct color value

### `color_map`
**Status:** Optional (recommended alongside `color`)
**What it is:** A broader color category Amazon uses for color filter navigation.
**Example:** `color` = "Olive Drab", `color_map` = "Green"
**Why it matters:** Without `color_map`, your product may not appear in color-filtered searches.

### `size`
**Status:** Conditional (required when `variation_theme` includes Size)
**Rules:** Use category-standard size values. Apparel sizes must match the Valid Values tab exactly.

### `size_map`
**Status:** Optional (recommended for apparel)
**What it is:** Broad size category for filter navigation: `S`, `M`, `L`, `XL` etc.

### `material_type`
**Status:** Optional (recommended — improves search indexing)
**Examples:** `Stainless Steel`, `100% Cotton`, `Full-Grain Leather`, `Polycarbonate`

### `product_site_launch_date`
**Status:** Optional
**What it is:** Date the product becomes active on Amazon.
**Format:** `YYYY-MM-DDTHH:MM:SS`
**Use:** Schedule launches for specific dates.

---

## SECTION 8: SHIPPING AND COMPLIANCE

### `item_package_dimensions`
**Status:** Optional (recommended for FBA — affects fulfillment fees)
**Fields:** `item_height`, `item_length`, `item_width`, `item_weight`
**Units:** Inches for dimensions, pounds for weight (US marketplace)
**Why it matters:** Inaccurate dimensions = incorrect FBA tier = wrong fees.

### `country_of_origin`
**Status:** Required in some categories (toys, electronics, food, textiles)
**Format:** Full country name or ISO 2-letter code: `China` or `CN`

### `batteries_required`
**Status:** Conditional (required if product contains or uses batteries)
**Accepted values:** `Yes` | `No`
**If Yes:** Additional fields required: `battery_type`, `number_of_batteries`, lithium battery documentation

### `is_adult_product`
**Status:** Optional
**Accepted values:** `true` | `false`
**Note:** Adult products are restricted to buyers who have confirmed adult status. Required for certain health/wellness items.

### `california_proposition_65_warning_type`
**Status:** Conditional (required if product is subject to Prop 65)
**What it is:** California's chemical safety law. Required for products containing listed chemicals sold in CA.
**Accepted values:** Specific warning type codes per chemical category.

---

## SECTION 9: CATEGORY-SPECIFIC CRITICAL FIELDS

### Apparel
| Field | Notes |
|-------|-------|
| `department` | Required. `mens`, `womens`, `boys`, `girls`, `baby-boys`, `baby-girls`, `unisex-adult`, `unisex-child` |
| `size_type` | `regular`, `plus`, `petite`, `maternity`, `big-tall` |
| `age_range_description` | `Adult`, `Teen`, `Child` |

### Supplements / Health
| Field | Notes |
|-------|-------|
| `ingredients` | Complete ingredient list — matches label |
| `serving_size` | Per-serving amount |
| `number_of_servings` | Servings per container |
| `dosage_form` | `Capsule`, `Tablet`, `Powder`, `Liquid`, `Softgel` |
| `item_form` | Similar to dosage_form — check which your template uses |

### Toys (Children's)
| Field | Notes |
|-------|-------|
| `age_range_min` | Minimum age in months or years |
| `age_range_max` | Maximum age |
| `safety_warning` | Required if small parts: `WARNING: CHOKING HAZARD` |
| `cpsc_compliant` | `Yes` if CPC certified |

### Electronics
| Field | Notes |
|-------|-------|
| `wattage` | Required for electrical products |
| `voltage` | `110V`, `220V`, `110-220V` |
| `compatible_devices` | Compatibility list — key for search indexing |
| `wireless_type` | `802.11n`, `Bluetooth 5.0`, etc. |

### Automotive
| Field | Notes |
|-------|-------|
| `fits_years` | Year range the part fits: `2015-2022` |
| `fits_makes` | Vehicle makes: `Ford, Chevrolet, Toyota` |
| `fits_models` | Specific models |
| `part_number` | OEM or aftermarket part number |

---

## SECTION 10: COMMON ERROR CODES AND FIXES

| Error Code | Meaning | Fix |
|------------|---------|-----|
| **5000** | Malformed data or required field missing | Check every Required field has a valid value |
| **5461** | UPC/barcode already associated with different ASIN | Use the existing ASIN's barcode, or apply for GTIN exemption |
| **8541** | Product ID (UPC) doesn't match existing ASIN's records | UPC mismatch — verify your barcode matches Amazon's database |
| **8560** | Required attribute missing | Check the error detail — it names the specific missing field |
| **8002** | Invalid value for a constrained field | Check Valid Values tab — value must match exactly |
| **99010** | Missing value for a variation attribute | Parent or child is missing a field required by the `variation_theme` |
| **8016** | Variation theme mismatch | The attribute you listed as the variation doesn't match what's in `variation_theme` |
| **8059** | Restricted product | This product/category requires approval — apply via Selling Applications |
| **8026** | Duplicate key attribute — SKU already exists | SKU conflict — either update existing SKU or change your SKU |
| **6023** | Image URL not accessible | URL must be publicly accessible HTTP/HTTPS — no authentication required |
| **20001** | ASIN already exists for this product | Product is already in Amazon's catalog — match to existing ASIN instead of creating new |

---

## SECTION 11: FLAT FILE FORMATTING RULES

### File Preparation
- Save final file as: `.txt` (tab-delimited) or `.csv` (comma-delimited)
- Do NOT save as `.xlsx` for upload — Amazon only accepts `.txt` or `.csv`
- UTF-8 encoding (not UTF-16 or ASCII)
- Row 1: column headers (copied from the template — do not modify)
- Row 2: template metadata row (exists in some templates — leave it in)
- Row 3 onward: your product data

### Encoding Traps (Common Causes of Silent Errors)
- **Curly quotes** from Word/Google Docs: `"like this"` → replace with straight quotes `"like this"`
- **Smart apostrophes:** `it's` → `it's`
- **Em dashes** in copy: `—` can corrupt — use regular hyphen `-` in flat files
- **Non-breaking spaces:** look identical but cause field mismatch errors
- **Trailing spaces:** invisible but Amazon treats them as part of the value

### Character vs. Byte Counts
- `generic_keywords` limit is 250 **bytes**, not characters
- ASCII characters: 1 byte each
- Accented characters (é, ñ, ü): 2 bytes each
- Emoji: 3–4 bytes each (avoid entirely in flat files)
- Safe rule: keep backend keywords under 200 characters to stay safely under the byte limit

---

## SECTION 12: THE PARTIALUPDATE CHECKLIST

Before uploading any update file, run this check:

- [ ] `update_delete` column set to `PartialUpdate` (not `Update`)
- [ ] Only columns you intend to change have values — all other columns are blank
- [ ] `item_sku` is present and exactly matches the existing SKU
- [ ] `feed_product_type` is present (required even in PartialUpdate)
- [ ] No trailing spaces in SKU or key fields
- [ ] Price fields: numeric only, no `$` symbol
- [ ] FBA listings: `quantity` column is blank
- [ ] File saved as `.txt` or `.csv`, not `.xlsx`
- [ ] Encoding is UTF-8

**If you run an `Update` instead of `PartialUpdate` accidentally:**
Immediately run a PartialUpdate with all critical fields re-populated (title, bullets, backend keywords, price, images). The window to recover is narrow — Amazon can take 15–60 minutes to process the overwrite.
