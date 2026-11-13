# CampaignOps

**Build, check and fix campaign links before they go live.** A free tool for digital marketers that catches UTM tagging mistakes, broken-looking links and breaks of your team's naming rules, and shows how GA4 is likely to classify each link. Everything runs in your browser; nothing is uploaded.

**▶ Open CampaignOps: https://ashrithpapai.github.io/campaignops/**

![The CampaignOps report for a CSV of campaign links](docs/images/report.png)

## What it does

| Tab | Use it to |
|---|---|
| 🔗 **Build links** | Create correctly tagged links for several channels at once, following your team's rules |
| ✍ **Check pasted links** | Paste a few links and see every problem, with a plain explanation and a suggested fix |
| 📄 **Check a CSV file** | Check thousands of links from a spreadsheet, fix them in bulk, and download a report |

It finds problems such as:

- **Tagging mistakes:** missing tags, capital letters, spaces, tags placed after the `#`, the same tag twice, unfilled placeholders like `%%name%%` or `{{name}}`
- **Link problems:** links that aren't valid web addresses, `http://` instead of `https://`, links to `localhost`, private networks or test sites
- **Your team's rules:** approved sources and mediums, and a campaign naming pattern (for example `brand_region_campaign_year`)
- **Problems across a whole file:** duplicate links, the same value spelled several ways (`Diwali_2026`, `diwali-2026`), and one source tagged with different mediums in the same campaign

It can also **fix** many problems for you (always showing a before and after first), produce a one-page **report** you can download or print, and save your rules as **profiles** for different brands or clients.

## Your data stays with you

- CampaignOps is a single web page. It **loads nothing from the internet and sends nothing anywhere**: your links and files never leave your computer.
- It also **works offline**: save the page and open the file in any modern browser.
- Rules are kept in the open page only. You can export them as a file, or turn on **"Remember profiles on this computer"** (off by default). Other pages on the same site, or other HTML files on your computer if you use a saved copy, can read what's remembered this way, so CampaignOps warns you before turning it on.

## About the GA4 predictions

For GA4 users, CampaignOps shows the **channel GA4 is likely to report** for each link (Paid Search, Email, Organic Social and so on). It follows Google's published default channel rules for tagged links and Google's list of source categories.

It is a **prediction from the link's tags, not a live GA4 result**. GA4 can still differ because of things a link can't show: custom channel groups, Google Ads auto-tagging settings, and, for untagged links, where the visitor clicked. The predictions were checked against a live GA4 property before release: **16 of 17 test links matched**; see [the live test](docs/USER_GUIDE.md#how-accurate-are-the-ga4-predictions) for the one difference and how CampaignOps flags it.

If you don't use GA4, simply ignore those lines; every other check works the same for any analytics tool.

## For automation and spreadsheets

Problem **codes** (such as `UTM_CASE_MISMATCH`) and CSV **column names** (such as `CampaignOps_Audit_Status`) are stable: they won't change between versions. Build scripts and formulas on those. The human-readable **messages** may be reworded to make them clearer.

## Documentation

- **[User guide](docs/USER_GUIDE.md):** step by step, with screenshots, and the full list of problem codes.

## Licence

Free and open source under the [MIT licence](LICENSE): you may use, change and share CampaignOps, including at work. It comes with no warranty.

Made by **Ashrith Papai**.
