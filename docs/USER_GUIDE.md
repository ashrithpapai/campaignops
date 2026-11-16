# CampaignOps user guide

CampaignOps checks campaign links before they go live, so your reports aren't split, mislabelled or missing traffic. Everything happens in your browser; nothing is uploaded.

**Open it:** https://ashrithpapai.github.io/campaignops/

- [Your first check in 2 minutes](#your-first-check-in-2-minutes)
- [Build links](#build-links)
- [Check pasted links](#check-pasted-links)
- [Fix a link](#fix-a-link)
- [Check a CSV file](#check-a-csv-file)
- [The report](#the-report)
- [Problems across a whole file](#problems-across-a-whole-file)
- [Your team's rules and profiles](#your-teams-rules-and-profiles)
- [How accurate are the GA4 predictions?](#how-accurate-are-the-ga4-predictions)
- [Common questions](#common-questions)
- [Problem codes](#problem-codes)

## Your first check in 2 minutes

1. Open CampaignOps and click **✍ Check pasted links**.
2. Click **Load 16 example links**, then **Check links**.
3. Scroll through the results. Each link shows its status (**Clean**, **Warning** or **Critical**), every problem in plain words, and a suggested fix.

Then paste your own links, one per line, and click **Check links** again.

## Build links

Use **🔗 Build links** to create correctly tagged links instead of typing tags by hand.

![Building two links for one campaign](images/build-links.png)

1. Enter the **landing page link**.
2. Fill in the **campaign** parts. They follow your team's naming pattern (see [rules](#your-teams-rules-and-profiles)), so `nike`, `in`, `diwali`, `2026` becomes `nike_in_diwali_2026`. Use **letters and numbers only** in each box: CampaignOps adds the `_` between parts for you. Tick **Free text** to type the whole name yourself.
3. For each link, enter `utm_source` and `utm_medium`, or use **Quick-add a link…** for common ones (Google Ads, Facebook, Instagram, LinkedIn and YouTube ads, Email, SMS).
4. Each link is checked as you type. **Apply fixes** appears when there's something CampaignOps can correct for you, such as capital letters.
5. Click **Copy** for one link, **Copy all**, **Export CSV**, or **Open in Check pasted links** to review them in detail.

Also useful:

- **Custom parameters (optional)** adds non-UTM parameters your site needs, such as `ref=newsletter`, to every link.
- If the landing page link **already has UTM tags**, CampaignOps stops and offers **Replace existing UTMs**, so tags are never doubled.
- You can build up to **50 links** at once.

## Check pasted links

Paste links into **✍ Check pasted links**, one per line, and click **Check links**.

![A checked link with two problems](images/check-pasted-links.png)

Each result shows:

- **Status:** **Critical** (the link is broken or will be badly mis-tracked), **Warning** (worth fixing) or **Clean**.
- **Problems**, grouped as Critical, Warnings and For your information. Each one shows what was found, the evidence, and how to fix it.
- **Problem type:** **Link format** (how the link is written), **Destination** (where it goes) or **Team rules** (your team's tagging rules).
- **For GA4 users:** the channel GA4 is likely to report. Ignore this if you use another analytics tool.

## Fix a link

Under any result with something to fix, click **Fix this link**.

![The fix panel with safe fixes and a decision](images/fix-a-link.png)

Fixes come in three groups:

| Group | Meaning | Example |
|---|---|---|
| **We can fix this for you** | Safe formatting fixes that don't change what the link means. Ticked for you. | Removing spaces, lowercasing `Facebook` |
| **Needs your decision** | Fixes that change meaning, so you choose | Picking an approved medium, switching to https |
| **You'll need to fix this yourself** | Nothing can be fixed safely; CampaignOps explains why | A missing campaign name, a link to a test site |

You always see the link **before and after** before anything changes. Click **Apply** to update the link in the box (**Undo last fix** puts it back), or **Copy fixed link**. **Fix all safe issues** at the top applies only the first group, to every link at once, after showing you each change.

CampaignOps never makes up a value: it only reformats what's there or uses a value you pick. If a formatting fix would change the GA4 channel (for example `social media` becoming `social_media`, which GA4 doesn't recognise as social), it's moved to **Needs your decision** instead of being applied automatically.

## Check a CSV file

Use **📄 Check a CSV file** for many links at once, for example an export from your ad or email platform.

1. Drop in a CSV file (up to 25 MB, separated by commas or semicolons), or click **Load example CSV** to try it.
2. Choose **which column has the links**. CampaignOps guesses; check the preview.
3. Click **Check all links**. Large files are checked in batches, and you can cancel at any time.

![CSV results with filters](images/csv-results.png)

**Filter** the results by status, problem type, a specific problem, across-file issues or GA4 channel, or search the links. Results show 50 rows per page. Click **Details** on a row for the full explanation.

**Fix in bulk:** click **🔧 Review fixes**. Safe fixes are grouped by type ("Remove spaces: 120 rows"), so you approve each type once instead of row by row. Choices like "which approved medium?" are grouped by identical values. You see how many rows will change before applying, and **Discard fixes** undoes everything.

**Downloads:**

- **Export All Results (CSV):** your original columns plus CampaignOps' results for every row, in columns starting with `CampaignOps_`. The most useful: `CampaignOps_Audit_Status` (Clean, Warning or Critical), `CampaignOps_Primary_Codes` (problem codes), `CampaignOps_Suggested_Fixes`, `CampaignOps_GA4_Predicted_Channel`, `CampaignOps_Fixed_URL` and `CampaignOps_Status_After_Fix` (after fixing), and `CampaignOps_Across_File_Checks`. To protect you when opening it in a spreadsheet, any cell starting with `=`, `+`, `-` or `@` gets a `'` in front, so it can't run as a formula.
- **Export cleaned file:** your uploaded file with the fixed links in place and **every other cell exactly as it was**, ready to re-upload to your ad platform, email platform or CRM. It no longer contains the original links, so keep your original file. If a file came from someone you don't trust, open the cleaned file with the same care as the original.
- **Export manual-fix list:** the rows you need to fix yourself, with the reasons.

## The report

After checking a CSV file, click **📊 Report** for a one-page summary: link health, top problems, problem types, GA4 channels, your team's rules and the sources and mediums used.

![The report](images/report.png)

- Click **View N links →** on any row to see exactly those links in the table.
- **Download report** saves a single page you can email or print. It contains counts and values only, **never the list of links**.
- **Print / Save as PDF** prints just the report.
- After applying fixes, switch between **Before fixes** and **After fixes**.

## Problems across a whole file

Some problems only show when links are compared with each other. After a CSV check, affected rows show a **⧉ Across file** label, and the **Across file** filter lists them.

![An across-file explanation in Details](images/across-file.png)

| Check | Example | Why it matters |
|---|---|---|
| **Duplicate links** | The same link in rows 4, 9 and 12 | You can't tell those ads apart in your reports; usually `utm_content` should differ |
| **Spelling variants** | `Diwali_2026`, `diwali-2026`, `DIWALI 2026` | Reports show each spelling as a separate campaign |
| **Mixed mediums** | In one campaign, `facebook` tagged `cpc` and `paid_social` | The same channel's traffic is split |

Links can count as duplicates even when they're written differently (tags in a different order, capitals in the domain, `:443`, `%20` vs `+`). The Details panel explains exactly how. These checks never change a row's own status.

## Your team's rules and profiles

Click **Your team's tagging rules** at the top to open the rules.

![The rules panel](images/team-rules.png)

1. **Required tags:** which tags every link must have.
2. **Lowercase:** tag values must be lowercase.
3. **Approved values:** the sources and mediums your team allows.
4. **Campaign naming:** the parts and order of campaign names.

**Profiles** save a set of rules under a name, for example one per brand, region or client.

![The profiles menu](images/profiles-menu.png)

- Choose a profile in the **Rules** menu to switch. If you have unsaved changes, CampaignOps asks first.
- **More ▾** lets you save, rename, duplicate, delete, **export** and **import** profiles. Exported profile files are the safest way to keep rules and share them with colleagues.
- **Remember profiles on this computer** is off by default. If you use a copy of CampaignOps saved on your computer, other HTML files you open from your computer in the same browser can read what's remembered; on the website, other pages on the same site can. Only turn it on if your rules aren't confidential, and use **Export** to keep them safely in a file.
- **Default** is always there and can't be changed, so you can get back to the standard rules.

If you change rules after a check, a yellow banner tells you the results were checked with different rules, with a **Run again** button.

## How accurate are the GA4 predictions?

CampaignOps predicts the channel GA4 is likely to report, from the link's tags, using Google's published default channel rules and source list.

**Live test, November 2026.** 17 links with deliberately tricky tags were sent to a real GA4 property and compared with CampaignOps' predictions: **16 of 17 matched**, including capital letters, a source with a space, a paid-looking medium GA4 treats as organic, made-up tags, and tags hidden after the `#`.

The one difference: a link tagged `utm_source=meta&utm_medium=paid_social`. Google's published rules put an unlisted source in **Paid Other**, which is what CampaignOps predicts, but GA4 reported **Paid Social**, so Google appears to recognise some sources that aren't on its published list. CampaignOps flags this case as **Review required** and tells you that GA4 may report the other channel anyway. Using a source on Google's list (`facebook` instead of `meta`) removes the doubt.

A prediction can still differ from GA4 when GA4 uses information a link doesn't show: custom channel groups, Google Ads auto-tagging, or, for untagged links, where the visitor clicked.

**Google Ads auto-tagging:** if a link carries Google Ads' click ID (`gclid`, `gbraid`, `wbraid` or `gad_…`), GA4's channel depends on your Google Ads and GA4 link settings, not just the tags. CampaignOps then shows **Google Ads auto-tagged** (no UTM tags) or adds **(Conditional on integration)** to its prediction.

## Common questions

**Is my data uploaded anywhere?**
No. CampaignOps loads nothing from the internet and sends nothing anywhere. You can even use it offline.

**Why is my link flagged when it works fine?**
A link can open the right page and still be tracked badly, for example `Facebook` and `facebook` show as two different sources in reports. Each problem explains why it matters.

**I don't use GA4. Is CampaignOps still useful?**
Yes. Every check except the GA4 channel lines works the same for any analytics tool, or none.

**Why does a placeholder like `%%name%%` show as Critical?**
It means the link hasn't been filled in yet. That's expected inside an email template; check a link from a real send to see the final version.

**Can I change the rules?**
Yes, in **Your team's tagging rules**. Save them as a profile so you don't have to set them again.

## Problem codes

Codes never change between versions, so you can rely on them in scripts and spreadsheets.

| Code | Type | Severity | Meaning |
|---|---|---|---|
| `RAW_WHITESPACE_PADDING` | Link format | Warning | Spaces before or after the link |
| `RAW_UNENCODED_WHITESPACE` | Link format | Critical | Spaces inside the link |
| `QUERY_AFTER_FRAGMENT` | Link format | Warning | Tags placed after the # in the link |
| `MULTIPLE_QUESTION_MARKS` | Link format | Critical | More than one "?" in the link |
| `MALFORMED_PERCENT_ENCODING` | Link format | Critical | A "%" that isn't a valid code |
| `INVALID_URL_SYNTAX` | Link format | Critical | Not a valid web address |
| `DUPLICATE_QUERY_PARAM` | Link format | Critical | The same name appears more than once |
| `UNRENDERED_TEMPLATE_TOKEN` | Link format | Critical | A placeholder that hasn't been filled in |
| `UTM_WHITESPACE_IN_VALUE` | Link format | Critical | Spaces in a tag value |
| `UNSUPPORTED_PROTOCOL` | Destination | Critical | Not an http:// or https:// link |
| `INSECURE_HTTP` | Destination | Warning | http:// instead of https:// |
| `LOCALHOST_TARGET` | Destination | Critical | Points to a computer's own address |
| `PRIVATE_IP_TARGET` | Destination | Critical | Points to a private network address |
| `STAGING_SUBDOMAIN_LEAK` | Destination | Warning | The address suggests a test site (dev, test, staging and similar) |
| `MISSING_REQUIRED_UTM` | Team rules | Critical | A required tag is missing |
| `UTM_CASE_MISMATCH` | Team rules | Warning | Capital letters in a tag value |
| `UTM_SOURCE_NOT_ALLOWED` | Team rules | Warning | Source not on your approved list |
| `UTM_VALUE_NOT_ALLOWED` | Team rules | Warning | Medium not on your approved list |
| `CAMPAIGN_NAMING_VIOLATION` | Team rules | Warning | Campaign name doesn't follow your naming rule |

Across-file checks use the codes `DUPLICATE_LINK`, `SPELLING_VARIANT` and `MIXED_MEDIUMS` in the export's `CampaignOps_Across_File_Checks` column.

### GA4 notes

These appear only in the GA4 part of a result, and explain why a prediction is uncertain or unavailable. They're useful for GA4 users; anyone else can ignore them.

| Code | Severity | Meaning |
|---|---|---|
| `UTM_AFTER_FRAGMENT` | Critical (Warning if tags are also before the #) | Tags after the # aren't read by GA4 |
| `DUPLICATE_UTM` | Critical | The same UTM tag appears twice, so GA4's choice can't be predicted |
| `UNRESOLVED_TEMPLATE` | Critical | A placeholder in a UTM tag hasn't been filled in |
| `MALFORMED_ENCODING` | Critical | A broken "%" code in a UTM tag |
| `UNREACHABLE_DESTINATION` | Critical | Visitors can't reach the page, so there's nothing to predict |
| `NO_URL` | Critical | The cell is empty |
| `UPPERCASE_UTM_KEY` | Warning | A tag name in capitals, such as `UTM_SOURCE`, which GA4 may not read |
| `MISSING_SOURCE`, `MISSING_MEDIUM` | Warning | utm_source or utm_medium is missing |
| `EMPTY_SOURCE`, `EMPTY_MEDIUM` | Warning | utm_source or utm_medium is there but empty |
| `PAID_INTENT_NOT_RECOGNIZED` | Warning | A medium that looks paid, but GA4 won't treat as paid |
| `CHANNEL_CONFLICT` | Warning | The source and medium point to different channels |
| `TAGGING_HINT` | Warning | The source isn't on Google's list, but a listed equivalent exists (for example `meta` and `facebook`) |
| `AUTO_TAGGING_DETECTED` | For your information | Google Ads auto-tagging was found in the link |
| `UNTAGGED` | For your information | No UTM tags, so GA4 decides from where the visitor clicked |
