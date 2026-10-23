# AxmolFighter-UI

FairyGUI 5.x UI source for **AxmolFighter** (Cocos2dx/Axmol). This repository has no application runtime, package manager, tests, or linters.

## Cursor Cloud specific instructions

This workspace is UI XML/PNG/OGG/TTF only. There is nothing to `npm install`, `pip install`, or `cargo run` here. Future cloud sessions should treat the startup update script as a no-op.

**What this repo is:** packages under `assets/` (`Common`, `Login`, `Launch`, `CharacterLobby`, `Game`) plus `ui.fairy` and `settings/`. Design resolution is 1280×720 (`settings/Adaptation.json`).

**How to edit/publish:** open `ui.fairy` in FairyGUI Editor 5.x (Windows/macOS). File → Publish writes `.fui` packs to `../AxmolFighter-Client/Content/UI/{publish_file_name}` as configured in `settings/Publish.json`. That sibling client is **not** in this workspace. FairyGUI Editor is a desktop app and is not available in this Linux cloud VM.

**How to sanity-check without the editor:** parse every `assets/**/*.xml` and confirm referenced `fileName` image paths exist on disk. There are no lint/test/build scripts in-repo.

**End-to-end gameplay** (login → character → town/battle) requires sibling repos (`AxmolFighter-Client`, `AxmolFighter-Server`), PostgreSQL, and the gateway/game processes. Those services are out of scope for this UI repository.

`.objs/` is FairyGUI editor cache and is gitignored.
