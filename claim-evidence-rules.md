# Claim Evidence Rules

Use this reference before compliance profiling and copywriting. The goal is to prevent unsupported claims while making the page more persuasive through visible evidence.

## Claim types

Classify each selling point as one or more of:

- `feature`: what the product has or is.
- `benefit`: what the buyer gets from the feature.
- `experience`: sensory, lifestyle, convenience, or emotional feeling.
- `proof`: certificate, test, review, data, process, origin, award, or official fact.
- `offer`: price, bundle, gift, shipping, after-sales, guarantee.
- `comparison`: contrast with alternatives, old habit, ordinary product, or SKU choice.
- `trust`: service, store, brand, qualification, buyer proof, production proof.

## Claim strength levels

- `strong`: exact, measurable, official, comparative, guaranteed, medical, functional, or performance-specific.
- `moderate`: feature-benefit relationship that is plausible but not quantified.
- `soft`: scenario, lifestyle, texture, mood, convenience, routine, or preference-based expression.

## Evidence source levels

- `user_provided`: explicitly supplied by the user.
- `visible_product_proof`: observable from uploaded product image or visible structure/material/packaging.
- `derived_from_category`: cautious category-level inference, must remain soft.
- `unsupported`: no source; must not be written as a fact.

## Evidence gate

Use this gate for every claim:

1. If the claim is strong and has no user-provided evidence, remove it or downgrade it.
2. If the claim uses certification, test report, award, ranking, origin, sales volume, celebrity, doctor, institution, government, platform, or expert endorsement, require explicit user-provided evidence.
3. If a claim is only inferred from category, write it as a soft scenario or usage possibility, not as a fact.
4. If a claim is visible in the product image, describe what can be seen rather than inventing why it exists.
5. If a claim is important but unsupported, ask the page to create a proof slot or mark it as missing evidence, not as customer-facing copy.

## Safe downgrade patterns

- Exact efficacy -> daily experience or routine language.
- Medical or physiological improvement -> lifestyle companionship or ordinary use scene.
- Best/first/top -> suitable choice, practical upgrade, thoughtful detail.
- Guaranteed result -> designed to support, helps create, easier to, more convenient for.
- Origin/process if unknown -> visible material texture, clean presentation, detail close-up.
- Sales/reviews if unknown -> remove; never fake social proof.
- Certification if unknown -> remove; never create badge-like visuals.

## Claim-evidence mapping fields

For each claim, record:

- `claim`: original or proposed claim.
- `claim_type`: feature, benefit, experience, proof, offer, comparison, or trust.
- `source`: user_provided, visible_product_proof, derived_from_category, or unsupported.
- `claim_strength`: strong, moderate, or soft.
- `evidence_required`: true or false.
- `evidence_available`: true or false.
- `allowed_customer_copy`: the safe version for final page text.
- `visual_proof`: what image/detail/scene should support it.
- `risk_note`: what to avoid.

## Visual proof rules

Good visual proof:

- macro material/texture shot for material claims.
- open package or quantity layout for package claims.
- interface/port/detail shot for electronics compatibility claims.
- scale reference for size claims.
- step-by-step scene for usage claims.
- provided report/photo/review asset for trust claims, without alteration or exaggeration.

Bad visual proof:

- fake seals, fake medals, fake official stamps.
- doctors, hospitals, medical icons for ordinary wellness products.
- before/after transformation for unverified efficacy.
- exaggerated competitor comparison.
- made-up buyer screenshots or review cards.

## Copy decision examples

- User says: material is 316 stainless steel. Allowed: mention 316 stainless steel and show detail proof.
- User says: quality is good. Allowed: write soft texture/detail copy, not quantified quality proof.
- User says: sold 100,000 units. Allowed only if the user provided it and the platform/category allows it; otherwise mark as evidence needed.
- User provides no origin. Do not write source origin, direct from origin, imported, selected from a specific region, or farm-direct.
- User provides no report. Do not create test-report visuals, inspection seals, or certificate badges.
