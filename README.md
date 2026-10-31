# Scrapbook Press

A free, local-first tool for laying out scrapbook pages and exporting them as
print-ready PNGs and PDFs at true physical size.

Live at **https://scrapbookpress.com**

---

## How it is built

The whole program is one file: `index.html`. No build step, no package manager,
no framework, no dependencies. Open it in a browser and it runs.

That is deliberate. A single HTML file can be emailed, copied to a USB stick,
archived, and opened in ten years, because browsers treat breaking old pages as
a bug. An installer, a bundler or a framework version is one more thing that can
stop working.

| file | purpose |
|---|---|
| `index.html` | the entire application |
| `CNAME` | holds the custom domain for GitHub Pages — do not delete |
| `README.md` | this file |

## Running it locally

Open `index.html` in Chrome or Edge. That is the whole procedure.

## Deploying

Commit and push to `main`. GitHub Pages rebuilds within a minute and
scrapbookpress.com updates. There is nothing to compile.

## How projects are stored

**Save project as…** writes a `.json` file wherever you choose. It contains the
page layouts, the text, your template library, and the photos themselves,
embedded as data URLs. One file is the whole project — back it up and you have
backed up everything.

Photos are downscaled to 2400px on their longest side when added. That is enough
for a sharp 8-inch print at 300 DPI and keeps project files manageable. It also
means the project file is **not** an archive of the originals — keep those.

A full year of pages can reach 50–100 MB. Splitting a year into a project per
season keeps saves fast and limits what a single mishap costs.

## What is kept in the browser

All of it is local, and none of it is required — the project file is the real copy.

| store | key | holds |
|---|---|---|
| IndexedDB | `scrapbook-builder` → `state` | autosave snapshot plus a reference to the project file |
| IndexedDB | `scrapbook-builder` → `recents` | the last 8 projects opened |
| localStorage | `scrapbook-templates` | custom page templates |
| localStorage | `scrapbook-sections` | which inspector sections are collapsed |
| localStorage | `scrapbook-panels` | which side panels are hidden |

Clearing browsing data erases these. It cannot touch a saved project file.
Templates also travel inside project files, so opening a project restores them.

## Browser support

| | Chrome / Edge | Safari / Firefox |
|---|---|---|
| Lay out, export PNG and PDF | yes | yes |
| Save back to the same file | yes | no — downloads a copy each time |
| Recent projects, welcome card | yes | no |

On phones and tablets you can add photos and write; arranging a page wants a
real screen and a mouse.

## Configuration

Near the top of the contact-form code:

```js
const CONTACT = {
  web3formsKey: "",   // a Web3Forms access key
  endpoint: ""        // or a full form endpoint (Formspree, FormSubmit, ...)
};
```

Leave both empty and the feedback form composes an email instead, which keeps
the page free of network requests. Fill in **one** to accept messages in-page.

## Privacy

The page makes no network requests of its own. No accounts, no uploads, no
analytics, no external fonts or scripts. Photos are read from disk by the
browser and stay there.

You can check this: search `index.html` for `http`. There are exactly two
matches. One is `http://www.w3.org/2000/svg`, the XML namespace on the inline
icons, which is a name rather than an address and is never fetched. The other is
the form endpoint above, which is only contacted if you put a key in `CONTACT` —
left empty, as it ships, nothing is ever sent.

Or just disconnect from the internet and use it. Nothing changes.

The feedback form hands off to the operating system's mail client via `mailto:`,
which sends nothing itself. The contact address is assembled at runtime so that
scraping the source finds no address to harvest.

## Keyboard

| | |
|---|---|
| `Ctrl/⌘ + S` | save project |
| `Ctrl/⌘ + Z` / `Ctrl/⌘ + Y` | undo / redo (60 steps) |
| `Ctrl/⌘ + F` | find a page by title or by its text |
| `Ctrl/⌘ + M` | new page |
| `Ctrl/⌘ + D` | duplicate the selected zone |
| `Ctrl/⌘ + C` / `V` | copy and paste a zone, or the whole page if nothing is selected |
| `Ctrl/⌘ + B` / `I` / `U` | bold, italic, underline the selected text zone |
| `Delete` | remove the selected zone |
| `Arrows` / `Shift + Arrows` | nudge |
| `PgUp` / `PgDn` | previous / next page |
| `Alt` while dragging | ignore snapping and alignment guides |
| `Esc` | deselect, or cancel a drag |

## Known limits

- Undo is 60 steps and resets when the page reloads.
- Dragging pages to reorder them is mouse-only; the context menu has Move up and
  Move down for everything else.
- Alignment guides use each zone's unrotated box, so a rotated zone snaps by
  where it would sit at 0°.
- There is no cloud sync. Keeping project files in a synced folder (iCloud,
  Dropbox, OneDrive) works, one device at a time — there is no merge.
- Do not keep the git repository itself inside a synced folder; OneDrive and
  `.git` fight over locked files.
