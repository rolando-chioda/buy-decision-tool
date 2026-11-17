# Buy Decision Tool

**English** · [Italiano](README.it.md) · [Français](README.fr.md)

A single HTML file that helps you decide **what to buy first**. It combines five well-known techniques into one ranking:

| Technique | What it does here |
|---|---|
| **Weighted decision matrix** | You score each item from 1 to 10 on criteria you choose and weight. Price and cost per use are scored automatically. |
| **MoSCoW** | Must / Should / Could / Won't have. Multiplies the score; "Won't have" items are excluded. |
| **Eisenhower matrix** | Urgent × important. Multiplies the score and places each item in one of four quadrants. |
| **Cost per use** | Price ÷ (uses per month × expected lifespan in months). |
| **Waiting rule** | Items wait a few days (or weeks, above a price threshold) before they can be recommended. This filters out impulse buys. |

It also has:

- **Bundles**: link items you should buy together. A bundle is ranked, budgeted and released as one purchase.
- **Budget**: going down the ranking, it marks what you can buy now, what is still waiting and what is over budget.
- **Notes** for each item (links, models, shops, doubts).
- **Status** for each item: *Bought* and *No longer needed* move it to an archive (out of ranking and budget); *Postponed by N days or months* keeps it out of recommendations until that date.
- **Descriptions** under every field and setting, which you can hide once you know them. Settings are grouped in sub-tabs: budget and currency, waiting rule, criteria, data and backup, how it works.
- **Languages**: English, Italiano, Français. The page follows your browser language and has a selector.
- **Currencies**: EUR, USD, GBP, CHF, CAD, AUD, JPY.
- **Backup**: download your data as JSON and import it again anywhere.

## Use it wherever you prefer

There is no server and no account. Your data stays where you run the page.

1. **On your computer.** Download [`buy-decision-tool.html`](buy-decision-tool.html) and open it in any browser (Safari, Chrome, Firefox, Edge). Data is saved in that browser's local storage.
2. **On your own website or hosting.** It is a static file: put it on any static host (your own GitHub Pages, Netlify, a NAS, an intranet). Each visitor's data stays in their own browser.
3. **In your own claude.ai account.** Ask Claude to publish `buy-decision-tool.html` as an artifact with the `db` capability (and `downloads` for backups). The page detects claude.ai by itself and saves to that artifact's database instead of the browser, so the same list follows you on any device where you are signed in.

The page loads two fonts from Google Fonts. If they are unavailable (for example offline), it falls back to system fonts and still works.

## Your data

- **Browser mode** (options 1 and 2): data lives in the browser's `localStorage` for that page. Clearing site data, using a private window or switching browser means starting from an empty list. Use **Download backup** regularly and **Import JSON** to restore.
- **claude.ai mode** (option 3): data lives in your artifact's database, private to you unless you share the artifact.
- The backup file is plain JSON. You can read it, keep it in your own cloud storage, or move it between modes.

The page shows a reminder when your last backup is more than 8 days old.

## How the score is calculated

```
final score = weighted matrix score × MoSCoW factor × Eisenhower factor
```

- Weighted matrix: average of the 1–10 scores, weighted by the criteria weights. Automatic criteria give 10 to the cheapest item and 1 to the most expensive (linear in between).
- MoSCoW: Must ×1, Should ×0.75, Could ×0.5, Won't = excluded.
- Eisenhower: urgent and important ×1.2, important only ×1, urgent only ×0.8, neither ×0.6.
- Waiting rule: an item still waiting stays in the ranking but is not recommended.
- Budget: going down the ranking, each ready item (or bundle) is marked **Buy** if it fits the remaining budget, otherwise **Over budget**.

All of this is in plain JavaScript inside the HTML file, so you can read it and change it.

## Disclaimer

This is a decision aid, not advice. The results depend only on what you enter, may be wrong, and the final decision is yours. See [DISCLAIMER.md](DISCLAIMER.md).

## License

[MIT](LICENSE) © 2026 Rolando Chioda
