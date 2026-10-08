# Omya Events site

Live site: https://omyaevents.info, deployed by Netlify from the `main` branch of this repo. Every push to `main` goes live in about a minute. There is no build step.

## Files
- `index.html`: the whole page. Edit this file.
- `support.js`: the runtime that renders `index.html`. Never edit it.
- `uploads/`: all photos. `uploads/logo/` holds the logo, favicon and apple-touch icon.
- `og-cover.jpg`: social share image.

## How index.html is structured
- `<x-dc>` … `</x-dc>` holds the page template (HTML with `{{ path }}` holes, `<sc-for>` loops and `<sc-if>` conditionals). Holes are plain dotted lookups only, never expressions.
- `<script data-dc-script>` holds `class Component extends DCLogic { … }`, the page logic. The **event data** lives here as a list of objects, one per event (`id:'inner-circle-austin'`, `id:'executive-playbook-sf'`, …).
- Styles are inline `style="…"` attributes. Keep it that way; don't add classes or stylesheets.

## Common edits
- **Event text, dates, prices, schedules:** edit that event's object. Schedules go in `agendaGrouped` (days, each with `items:[{time, desc, hasNote, note}]`).
- **Cover photo:** set `gradient:"url('uploads/NAME.jpg') center/cover no-repeat"` on the event.
- **Gallery:** `gallery:[{caption, gradient}]`. Leave out `gradient` for an empty placeholder slot.
- **Hide an event:** add `hidden:true`. Delete it to show the event again.
- **Past events:** an event is marked concluded once its date has passed, and moves to "Past Events" after 6 months.
- **New photos:** resize to about 1400px wide, save as JPEG (quality ~0.84), put in `uploads/`, and add a matching `<meta name="ext-resource-dependency" content="uploads/NAME.jpg">` in `<head>`.

## Workflow
1. Make the change.
2. Open `index.html` in a local browser to check it (e.g. run `npx serve .` and open the URL).
3. Commit with a plain message ("Add SF gallery photos") and push to `main`.

Event copy the user supplies goes in verbatim. Don't rewrite it.
