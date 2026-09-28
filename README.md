# droidtop-theme-patches

Real ES-DE themes have no artwork or metadata for the "systems" that
[droidtop](https://github.com/bi0shacker001/droidtop) invents on top of
them: the game-engine categories (Ren'Py, RPG Maker MV/MZ/VX Ace, KiriKiri)
droidtop detects and groups games by, which aren't part of ES-DE's own
system list because they aren't consoles.

This repo is a base for per-system theme overlay fragments for those
invented systems, in the same per-system metadata format ES-DE themes
themselves use (`system/metadata/<id>.xml`, a `<theme>`/`<variables>`
block, confirmed against the per-system metadata files bundled with the
decaffe-es-de theme).

It intentionally starts with no filled-in content. [systems.json](systems.json)
lists the system ids that need a patch (droidtop's own
`${system.theme}`-style identifiers, from
`library-core/src/main/kotlin/dev/droidtop/library/EsDeArtwork.kt`), and
[system/metadata/TEMPLATE.xml](system/metadata/TEMPLATE.xml) shows the
field format to fill in. Contributions should use sourced information —
verifiable facts about the engine, accent colors from its actual branding —
not placeholder values.

droidtop clones this repo once, alongside whichever ES-DE theme is active,
and layers any filled-in fragments in as an overlay after loading that
theme, bundled or downloaded, so every theme droidtop can load gets
support for these systems without forking or patching the theme itself.

## Content

- `systems.json` — the system ids that need a patch.
- `system/metadata/TEMPLATE.xml` — the per-system metadata field format to
  copy from when adding `system/metadata/<id>.xml`.

Logo and box-art assets for these engines aren't covered yet either; that's
separate per-engine artwork work.
