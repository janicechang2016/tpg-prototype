# TPG Product Vision — Internal Tools Prototype Suite

A set of self-contained, interactive product prototypes exploring how AI-native internal
tooling could transform an editorial CMS — built around The Points Guy's publishing
workflow as the case study.

**Live:** https://janicechang2016.github.io/tpg-prototype/

> **Disclaimer:** This is independent concept work by Janice Chang. It is not affiliated
> with, endorsed by, or produced for publication by The Points Guy, Red Ventures, or any
> card issuer. All card data, point valuations, and article content are illustrative.
> Trademarks belong to their respective owners.

## The product story

Editorial teams at content businesses live or die by trust: stale offers, wrong point
valuations, and slow coverage of time-sensitive news all erode it. The thesis of this
suite is that the CMS — not a bolted-on chatbot — is the engine that makes AI features
trustworthy. Structured metadata, freshness tracking, and content tagging are what
separate a grounded, citable AI answer from a generic one.

Start at **[`index.html`](index.html)** — a product vision page (persona, pain points,
vision pillars, guided tour) that frames three working demos:

| Demo | What it shows |
|---|---|
| **Content Health Dashboard** (`tpg_cms_dashboard.html`) | CMS-integrated freshness signals — staleness scores, affiliate link status, changed data fields — turning manual content audits into a prioritized queue. |
| **Contextual AI Chat** (`tpg_prototype.html`) | An AI panel embedded in a card-review article, grounded in that article's CMS-verified content. Source attribution pills, suggested questions, and a toggleable "how this works" metadata panel. |
| **CMS CLI** (`tpg_cli.html`) | AI-assisted editorial tooling in a command-line idiom — scaffolding drafts from structured data feeds. |

Three further explorations live alongside them: an award-search explorer
(`tpg_award_search.html`), a card-stack recommender (`tpg_card_recommender.html`),
and a points-portfolio tracker (`tpg_portfolio.html`).

## Design decisions worth noting

- **Grounded, not generic.** The chat is deliberately scoped to the article's verified
  content — a product constraint (trust, compliance) rather than a technical limitation.
- **Citation as UX.** Source pills under every AI answer keep the reader anchored to
  editorial content instead of a free-floating assistant.
- **The CMS connection is visible.** Freshness badges and a metadata panel make the
  invisible infrastructure — the actual product surface for an internal-tools PM — tangible.
- **Honest simulation.** Responses are mocked client-side; the pages document the real
  production architecture (RAG over CMS content, server-side prompt assembly, re-indexing
  triggers) that the mock stands in for.

## Running it

No build step, no backend, no API keys. Open `index.html` in a browser, or serve the
folder statically:

```bash
python3 -m http.server 8000
```

Everything runs client-side; all responses are pre-authored mock data.
