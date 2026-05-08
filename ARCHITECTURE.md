# Architecture and Project Understanding

## Background

The existing V&V GUI was originally developed as a
fork of Arbalest (isaacy13/arbalest). When I studied
this fork, I noticed that the V&V specific logic was
mixed directly inside the base Arbalest application
code. This means the validation checks, results panel,
and export features were not separate from Arbalest —
they were baked into it.

This creates a problem because every time Arbalest
updates, the V&V code breaks and has to be manually
fixed. That is exactly what happened — the fork is
now 4 years old.

## My Understanding of the Problem

After studying the codebase and discussing with
mentors, I understood that this project is not just
about updating the old fork to work with the latest
Arbalest. The bigger goal is to properly separate
the V&V logic from the base Arbalest application.

The V&V functionality should work like a plugin or
an overlay on top of Arbalest — not be mixed inside
it. This way, when Arbalest updates in the future,
the V&V plugin can continue to work without breaking
because it uses Arbalest and MOOSE APIs from the
outside rather than being hardcoded inside.

## Current Problem

When I studied the isaacy13/arbalest fork, I found:

- V&V validation logic is mixed inside Arbalest code
- The fork uses Qt5 which is outdated
- Cannot be built with latest BRL-CAD and MOOSE
- Hard to maintain because everything is coupled
  together

## Proposed Approach

**Step 1 — Update to latest codebase**
Get the base Arbalest and MOOSE working with
the latest code. Fix any Qt5 to Qt6 compatibility
issues that come up during this process.

**Step 2 — Separate V&V logic**
Take the V&V specific code from the old fork and
restructure it so it works as a plugin or overlay
on top of Arbalest. The V&V code should use
Arbalest and MOOSE APIs — it should not be
mixed inside the base application.

**Step 3 — Add new features**
Once the separation is done cleanly, add the
new features planned in the proposal:
- Report generator module
- TXT and JSON export
- QTreeView grouping in results panel
- Summary count bar
- Export button in panel
- Viewport linking improvements

## Key Observations from Studying the Tool

After studying the application running on a
shipping container .g model, I noticed these
specific gaps that this project will fix:

- Full Path column shows /all/../.. — useless
  for debugging nested models
- No summary count after a run — have to
  manually count errors vs warnings
- Only CSV export — no TXT or JSON option
- CSV has no header or severity grouping
- Results shown in flat list — hard to navigate
  when there are many issues
