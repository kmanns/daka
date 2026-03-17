# DAKA Theme Direction Analysis

## Task

Adapt the DAKA storefront theme to blend:

- the local `300blackout` repo's visual language
- merchandising and category-presentation ideas from `https://www.classicfirearms.com/`

This is primarily a theming and storefront-presentational change, not a platform or architecture rewrite.

## Reference Analysis

### DAKA current state

- DAKA is already on the same Adobe Commerce + EDS boilerplate structure as `300blackout`.
- Core theming is driven from [`styles/styles.css`](/Users/kmanns/Documents/Edge%20Delivery/daka/styles/styles.css).
- The existing header implementation already matches `300blackout` structurally; the local diff shows no CSS differences in [`blocks/header/header.css`](/Users/kmanns/Documents/Edge%20Delivery/daka/blocks/header/header.css).
- The current DAKA default look is still mostly neutral boilerplate styling with gray brand tokens and a simple hero block.

### 300blackout

Key reusable elements from the local `300blackout` repo:

- warm brass accent palette layered over a near-black background
- condensed, military/editorial headline typography
- uppercase headings and stronger section titling
- darker chrome for header/footer
- more premium/tactical mood created mostly through token overrides, not structural rewrites

Most of the visible theme shift comes from a compact override block appended to `styles/styles.css`, especially:

- brand colors
- background color
- type scale and font family
- uppercase heading treatment
- section-title treatment
- header/footer surface styling

### Classic Firearms

Observed from the live homepage HTML on March 17, 2026:

- a high-density commerce homepage with a large sale/clearance hero plus stacked side promos
- very deep merchandising navigation with image-backed megamenu panels
- heavy emphasis on categories like long guns, handguns, ammo, accessories, rebates, and specials
- strong CTA repetition such as `SHOP NOW`, product-spotlight links, and category-led entry points
- homepage sections that alternate between promotional storytelling and direct product/category conversion

Useful ideas to borrow:

- merchandising density, not necessarily their exact layout
- category-first navigation and landing-page emphasis
- stacked promo modules adjacent to hero content
- visual prioritization of sale, in-stock, featured, and category campaigns

## Recommended Blend

### From 300blackout

Adopt as the base theme:

- dark tactical palette
- brass/sand accent color family
- condensed display typography
- uppercase section headings
- darker header/footer surfaces

### From Classic Firearms

Adopt as the commerce UX layer:

- more assertive homepage merchandising
- richer navigation panels with featured category art/cards
- campaign-led hero area with adjacent promo cards
- stronger product-list and category-page merchandising modules

### What not to copy directly

- the very crowded legacy HTML patterns from Classic Firearms
- any brittle inline-styled megamenu markup
- old-school homepage density that hurts readability on mobile

The right target is:

`300blackout` for mood and polish, plus Classic Firearms for conversion-oriented merchandising patterns.

## Suggested Implementation Phases

### Phase 1: Core visual skin

- Port the `300blackout` token overrides into [`styles/styles.css`](/Users/kmanns/Documents/Edge%20Delivery/daka/styles/styles.css)
- Add any missing font assets/loading if needed
- Restyle global headings, buttons, section titles, header surface, and footer surface

### Phase 2: Homepage merchandising

- Upgrade the existing hero block in [`blocks/hero/hero.css`](/Users/kmanns/Documents/Edge%20Delivery/daka/blocks/hero/hero.css) to support:
  - darker overlays
  - split layouts or adjacent promo cards
  - stronger CTA treatment
- Reuse existing blocks like `cards`, `carousel`, and `product-recommendations` to build Classic-Firearms-style campaign zones before inventing new blocks

### Phase 3: Navigation and category discovery

- Enhance header/nav presentation if needed, starting from the existing header block
- Consider featured visual tiles inside nav/dropdowns rather than a full legacy megamenu clone
- Improve category-entry visibility for top storefront journeys

### Phase 4: PLP/PDP refinement

- Restyle [`blocks/product-list-page/product-list-page.css`](/Users/kmanns/Documents/Edge%20Delivery/daka/blocks/product-list-page/product-list-page.css) to align with the darker, more premium theme
- Tune PDP, recommendation, and promo modules so the merchandising language stays consistent beyond the homepage

## Acceptance Criteria

- The storefront clearly shifts from boilerplate neutral styling to a dark, tactical, premium visual identity.
- The base mood aligns closely with `300blackout` through color, typography, and chrome treatments.
- The homepage and navigation feel more conversion-focused, borrowing category and campaign ideas from Classic Firearms without copying its legacy markup.
- The updated theme remains responsive and readable on mobile.
- Existing commerce functionality and drop-in behavior remain unchanged.
- The implementation prefers reusable block styling and composition over hardcoded page-specific hacks.

## Recommendation

Start with Phase 1 and Phase 2 together. That will create the biggest visual lift quickly while keeping risk low.
