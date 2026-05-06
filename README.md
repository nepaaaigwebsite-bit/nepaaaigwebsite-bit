# NEPA Intergroup Meetings

A single-page meeting finder for the [Northeast Pennsylvania Intergroup of Alcoholics Anonymous](https://nepaig.org), hosted at [meetings.nepaig.org](https://meetings.nepaig.org).

## What this is

This repository is one HTML file. That file embeds [TSML UI](https://tsml-ui.code4recovery.org/) — an open-source recovery meeting finder built by [Code for Recovery](https://code4recovery.org) — and points it at our intergroup's meeting data.

Meeting data lives in a Google Sheet maintained by the intergroup. The [Code for Recovery Sheets Importer](https://sheets.code4recovery.org/) converts that sheet into a [Meeting Guide-spec](https://github.com/code4recovery/spec) JSON feed, which TSML UI reads and renders as a searchable, filterable list with maps.

## Why it lives here

The main NEPA Intergroup site is on Google Sites, which sandboxes custom HTML inside iframes. That breaks important TSML UI features — deep links to specific meetings (`?meeting=slug`) don't reach the iframe, and the list can't expand to its natural height. Hosting the meeting finder on its own GitHub Pages subdomain sidesteps all of that and gives users a clean, full-page experience.

The rest of nepaig.org continues to live on Google Sites; the meetings page just links here.

## How to update the meeting list

You don't change anything in this repo to add, remove, or edit meetings. Open the [meetings Google Sheet](https://docs.google.com/spreadsheets/d/1qPGcc3KbOGdywOAJPDImmIFU0mVXnLLK300lKTQH9cc) and edit it there. The importer re-fetches periodically, so changes show up on the site automatically without a deploy.

For details on what each spreadsheet column means, see the [Meeting Guide spec](https://github.com/code4recovery/spec).

## How to update the page itself

Edit `index.html` and push to `main`. GitHub Pages will redeploy within a minute or so.

The TSML UI snippet inside that file is documented at <https://tsml-ui.code4recovery.org/>. If you change the data source, update the `data-src` attribute. If the intergroup ever changes timezones (it won't), update `data-timezone`.

## Links

- **Live site:** <https://meetings.nepaig.org>
- **Meeting data feed:** <https://sheets.code4recovery.org/storage/1qPGcc3KbOGdywOAJPDImmIFU0mVXnLLK300lKTQH9cc.json>
- **TSML UI documentation:** <https://tsml-ui.code4recovery.org/>
- **TSML UI source:** <https://github.com/code4recovery/tsml-ui>
- **Sheets Importer:** <https://sheets.code4recovery.org/>
- **Meeting Guide spec:** <https://github.com/code4recovery/spec>
- **Code for Recovery:** <https://code4recovery.org>

## Credits

TSML UI, the Sheets Importer, and the Meeting Guide spec are all built and maintained by [Code for Recovery](https://code4recovery.org), a non-profit that develops open-source tools for the recovery community. This repo is just configuration on top of their work.
