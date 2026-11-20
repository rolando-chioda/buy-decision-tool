# Quick guide

**English** · [Italiano](GUIDE.it.md) · [Français](GUIDE.fr.md)

> It is not a budgeting tool: if you put an item on the list, it is because you can afford it. It only helps you work out whether and when to buy it.

## Installation

There is nothing to install. Pick one option:

1. **On your computer**: download [`buy-decision-tool.html`](https://github.com/rolando-chioda/buy-decision-tool/raw/main/buy-decision-tool.html) and double-click it. Data stays in that browser.
2. **On your website**: upload the file to any static host. Each visitor keeps their own data in their browser.
3. **On claude.ai**: ask Claude to publish the file as an artifact with the `db` and `downloads` capabilities. Data is saved in your account and follows you on every device.

## Use

1. **Settings**: choose your currency. If you want, change the criteria and their weights.
2. **Items → + Add item**: enter name, price, MoSCoW, urgent/important, uses per month, lifespan and the 1–10 criteria scores. Click a row to review the data, then **Edit** to change it.
3. **★ Results**: see the recommended next purchase, what is ready and what is still waiting. Click a row to see every detail.
4. **After buying**: in ★ Results, use the status menu next to the item (no need to open it) and set it to *Bought*, *No longer needed* or *Postponed* by N days or months.
5. **Backup**: in Settings → Data & backup, use **Download backup (JSON)** often. To restore, use **Import JSON**.

To try it out: Settings → Data & backup → **Load example**.

The results are only indicative: see the [disclaimer](DISCLAIMER.md).
