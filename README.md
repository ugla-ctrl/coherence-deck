# Coherence Gathering — Investment Deck

Hand-coded HTML/CSS investor deck for the COHERENCE Gathering, in the same family as the [Midnight Sun deck](https://github.com/ugla-ctrl/midnight-sun-deck) and [IMXP deck](https://github.com/ugla-ctrl/imxp-deck-v3): a floating 16:9 stage on GitHub Pages, keyboard/click/swipe/wheel nav, dot rail, hash deep links, container-query type scaling.

Everything lives in `index.html` (self-contained, Google Fonts only). Source material in `sources/` — see [sources/README.md](sources/README.md).

## Design

Redesigned from scratch off the brand guide (`sources/coherence-brand-guide.md`), not copied from the other decks:

- Deep indigo night field, teal ring geometry, gold reserved for numbers and moments
- Montserrat (structure) + Playfair Display italic (the poetic lines), per the brand guide
- **The signature move:** one large sacred-geometry mandala sits behind the whole deck and rotates/expands as the viewer advances — the brand's "mandala activates" logo-animation concept applied to deck progress (`#mandala`, driven from `go()`)
- No photography anywhere: the brand guide prohibits stock imagery and no approved photos exist yet, so the deck is built entirely on geometry and type
- House style: no em dashes in copy

16 slides: cover · thesis · concept · pillars · audience · market · place · program arc · lineup · community engine · business model · financials · moats · lineage (IMXP) · roadmap · close.

## Email gate

Same lead-capture flow as the MSF/IMXP decks: name + email into Supabase project `australasia-eclipse-2028` (`qmxhsendoepqeyeolzil`), isolated insert-only-RLS table **`public.coherence_deck_leads`** (created 2026-08-28, write path verified). localStorage key `coherence_deck_access`. Network failure never traps a viewer.

Not yet wired: sheet mirror + email notify (the `deck-leads-export` edge function / notify cron only cover the imxp + midnight_sun tables — extend them when Mitch wants Coherence leads in the reports).

## Outstanding (needs Mitch)

- **The Ask slide** — no raise amount/valuation/use-of-funds exists in any source, so the deck closes with contact instead of an ask. Add slide when numbers arrive.
- **Figures confirmation** — deck uses the event brief's economics (650 target, $400–500K budget, ~$147K net) rather than the strategy doc's aspirational 3,333. Confirm.
- Custom domain `deck.coherencegathering.com` once DNS is available.

## Editing

Edit `.slide` sections in `index.html` directly; type scales via cqw/cqh so nothing else needs touching. Screenshot preview: playwright + `/usr/bin/google-chrome` (`NODE_PATH=/home/clawd/clawd/node_modules`), pre-seed `localStorage.coherence_deck_access` to skip the gate.
