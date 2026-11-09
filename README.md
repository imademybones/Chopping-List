# Chopping List

A shared shopping list for two phones. Tick things off as you shop, add staples with one tap, and see when you last bought anything.

It's a single-page web app you install to your phone's home screen. It has no build step. Data lives in an Airtable table that both phones read and write.

## Features
- **List**: items are grouped by aisle. Tap an item to tick it into "In the trolley", then tap **Done shopping**. Ticked items also clear themselves after 12 hours.
- **Staples**: one-tap chips, starting with about 30 defaults (bread, milk, butter, eggs…). Press and hold a chip to edit it.
- **Quantities**: type "2 milk", "3x eggs" or "bananas x6" in the add box, or tap − / + right on the list row. Quantities reset when an item comes off the list, and the history records how many you bought.
- **Shop tags**: tag items Aldi, Coles, Woolworths, Big W and/or Kmart, then tap a shop above the list to see just what you need there. Untagged items show for every shop. Each tick records which shop you were filtering by, and the Tracker shows it ("Today at Aldi").
- **Tracker**: for every item, when it was last bought, by whom, how often, and the full history. Staples you've gone longer than usual without show up as "Probably running low".
- Typing suggests things you've bought before, new items are put in an aisle automatically, changes made with poor signal are queued until you're back online, and there's light and dark mode.

## Setup
1. Turn on GitHub Pages for this repo: Settings → Pages → *Deploy from a branch* → `main` / root.
2. In Airtable, create a base (or reuse one). Then create a personal access token at airtable.com/create/tokens with `data.records:read`, `data.records:write`, `schema.bases:read` and `schema.bases:write` on that base.
3. Open the Pages URL in Chrome and enter your name, the base ID and the token. The app creates a `Chopping List` table and fills in the staples.
4. Go to Settings → **Share invite link** and send it to the other phone. They open it, add their name and tap **Join the list**.
5. In Chrome, use ⋮ → **Install app** to put it on the home screen.

The invite link contains the Airtable token, so only send it to people who should be able to edit the list.

## Files
- `index.html`: the whole app (HTML, CSS, JS)
- `sw.js`: service worker that caches the app so it opens offline
- `manifest.json`, `icon-*.png`: install metadata and icons
