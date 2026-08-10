# Voice 360 — Fundraising module

Everything designed and specified for Fundraising. 61 screens, FR-01 – FR-13.5.
Last updated 10 August 2026.

---

## What to read first

| Order | File | Who it's for |
|---|---|---|
| 1 | `01-engineering-handover.html` | Backend + frontend leads. **The binding document.** |
| 2 | `02-flow-map.html` | Everyone. The whole module as a map, screen gallery and clickable prototype. |
| 3 | `03-all-screens.html` | Designers + QA. All 61 screens rendered at 402×874 with notes. |
| 4 | `pdf/fundraising-full-flow.pdf` | Print / share outside the team. |

The three HTML files are **self-contained** — no build step, no server, no
internet. Double-click, or open with any browser. They work from a file:// path,
so a reviewer can download one file from GitHub and open it.

---

## File by file

### `01-engineering-handover.html` — the specification
Thirteen sections: 10 invariant rules, site map, routes, the 61-screen
inventory, data model, source-of-truth tags, permissions matrix, five state
machines, 23 corner cases, notification triggers, API surface, six build waves,
and 14 open decisions.

**Do this with it:** print to PDF for distribution (Ctrl/Cmd-P — it is already
paginated for Letter). Work through **§13 Decision register** in a meeting and
record the answers; D-01 (who bears the payment fee) blocks Wave 1 and D-04
(does the provider support recurring mandates) blocks Wave 4. Treat §1 as
non-negotiable and §11 as the starting point for the API contract, not the
finished one.

### `02-flow-map.html` — flow, screens, prototype
Three modes in one file: **Flow** (the tree, every node carries its FR code),
**Screen** (live thumbnails per journey, click to zoom) and **Prototype** (a
clickable walkthrough).

**Do this with it:** use it for scoping and standups. Ticket titles should quote
the FR code so a ticket, a screen and a spec row always agree.

### `03-all-screens.html` — the screen set
Every screen in live DOM at device size with its FROM / GOES TO routing note.

**Do this with it:** QA writes test cases against it; frontend lifts exact
spacing, colours and copy from it rather than eyeballing a screenshot. It is
also the file to hand a Figma importer if you want editable frames.

### `pdf/fundraising-full-flow.pdf`
The earlier printed flow. Historical — where it disagrees with
`01-engineering-handover.html`, the handover wins.

### `source-images/`
The original design boards these deliverables were built from. Reference only.

### `source/` — editable sources
The `.dc.html` originals plus the two runtime files they need
(`support.js`, `doc-page.js`). They must stay **in the same flat folder** —
each file loads `./support.js` next to it, and the flow map and screen set load
`Voice 360 Mobile : Fundraising Dashboard.dc.html` by filename.

**Do this with it:** only if you want to edit and re-export. For reading and
reviewing, use the three bundled files above.

> ⚠️ Two source filenames contain a colon (`Voice 360 Mobile : …`). Git stores
> them fine, but **Windows cannot check them out** — a Windows clone of this
> folder will fail. If any teammate is on Windows, either keep `source/` out of
> the repo (the bundled HTML files carry the same content), or rename those two
> files and update the matching `dc-import name="…"` inside
> `Voice 360 Fundraising - User Flow.dc.html` and
> `Voice 360 Mobile : Fundraising Screens.dc.html`.

---

## Suggested repo placement

```
design/
  fundraising/
    README.md                     <- this file
    01-engineering-handover.html
    02-flow-map.html
    03-all-screens.html
    pdf/
    source-images/
    source/                       <- optional, see the Windows warning
```

`02-flow-map.html` is ~20 MB and `03-all-screens.html` ~2 MB — under GitHub's
100 MB limit, so no Git LFS needed, but keep them out of any folder your CI
copies on every build.

## Not in this folder

The Community, Parliamentary, Business Hub and Pages modules, and the Framework
site that indexes all of them. Ask before duplicating any of these here — the
Framework is the single index and should be uploaded once, not per module.
