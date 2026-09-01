# OMARCHY100 — Plan

A 100-plugin catalog for Omarchy Quattro, built native to the shell instead
of bolted on. This file covers positioning, how Omarchy plugins actually
work, what the marketplace already looks like, and the build order. The
full 100-item catalog with brief features lives in [`plugins.md`](./plugins.md).

## Positioning

Seven series, 100 plugins:

| # | Series | Focus | Count |
|---|--------|-------|-------|
| 01 | omarchy-plus | Enhanced versions of built-in bar widgets | 15 |
| 02 | omarchy-productivity | Timers, notes, tasks, quick-lookup overlays | 20 |
| 03 | omarchy-dev | GitHub/GitLab/Linear/Jira, Docker, K8s, SSH, ports, envs | 20 |
| 04 | omarchy-system | CPU/GPU/RAM/disk/temp/fan/process monitoring | 15 |
| 05 | omarchy-media | MPRIS, Spotify, lyrics, album art, mixers | 10 |
| 06 | omarchy-desktop | Window/workspace management and switching | 10 |
| 07 | omarchy-theme | Fonts, cursors, backups, profiles, desktop overview | 10 |

The strongest, most differentiated series is **01 — omarchy-plus**: every
first-party bar widget in Omarchy today is intentionally minimal, so
"better" versions have real room to add value rather than duplicating
something that already exists.

## How Omarchy plugins actually work

Omarchy Quattro's shell (`omarchy-shell`) is a single long-running
**Quickshell/QML** process — not waybar, not a shell-script bar. The bar,
panels, notifications, lock screen, and overlays all live inside it.

- **Manifest contract**: every plugin ships a `manifest.json`
  (`schemaVersion: 1`) with `id` (reverse-DNS, e.g.
  `io.github.aryan-techie.<slug>`), `name`, `version`, `author`, `license`,
  `description`, `kinds` (`bar-widget`, `panel`, `overlay`, `service`,
  `menu`, `bar`), and `entryPoints` mapping each kind to a QML file. Bar
  widgets add a `barWidget` block: `displayName`, `description`,
  `category`, `allowMultiple`, `defaultSection`/`settingsForm`.
- **Native look for free**: import `qs.Commons` (theme-reactive `Color`,
  `Style`, `Border`, `Util` singletons, driven by the active theme's
  `colors.toml`/`shell.toml`) and `qs.Ui` (`BarWidget`, `WidgetButton`,
  `BarIconButton`, `Panel`, `PanelSectionHeader`, `PanelSlider`,
  `PanelActionButton`, `PopupCard`, `Toggle`, `Dropdown`,
  `SearchableDropdown`, `TextField`, `ConfirmDialog`, and more — full set
  in `/usr/share/omarchy/shell/Ui/`). Build on these instead of hand-rolled
  styling; it's what makes a plugin indistinguishable from a first-party
  widget.
- **Where plugins live**: `~/.config/omarchy/plugins/<plugin-id>/`,
  hot-reloaded on save. Force a reload with
  `omarchy-shell shell rescanPlugins` if a change doesn't pick up.
- **The clone workflow**: `omarchy plugin clone omarchy.<widget>` copies a
  first-party widget into your user plugin directory as a starting point.
  This is Omarchy's own documented path for "better built-in" plugins —
  use it for every Series 01/06 item that has a first-party counterpart
  instead of building from a blank file.
- **CLI you'll use constantly**: `omarchy plugin add / clone / enable /
  disable / list / remove / update / validate`, `omarchy bar move <id>
  --section <left|center|right>`, `omarchy restart shell`, `omarchy
  refresh shell`.
- **Publishing**: public GitHub repo, root `manifest.json`, README +
  LICENSE, a clean `omarchy plugin validate` run, then submit through the
  marketplace's `submit-plugin.yml` issue template on
  `github.com/HANCORE-linux/omarchy-plugin-marketplace`. Automated checks
  run first, then a maintainer reviews and merges into the live registry.
  **Plugins run unsandboxed** — you own the security bar: no destructive
  or uncleanable installs, no logging secrets, safe uninstall.

## What first-party already covers

Checked directly on this machine — these all exist today, and are all
deliberately minimal:

- `omarchy.clock` — date/time label + calendar popup, nothing else.
- `omarchy.network` — Wi-Fi list + connection state, no bandwidth/DNS.
- `omarchy.bluetooth` — device list + connect/disconnect, no battery %.
- `omarchy.battery` — a low-battery warning **service only**, no bar pill.
- `omarchy.media` — MPRIS playback controls, no lyrics/queue/album art.
- `omarchy.audio`, `omarchy.power`, `omarchy.weather`, `omarchy.tailscale`
  — each does exactly one narrow thing.
- `ActiveWindow.qml` and `Workspaces.qml` — first-party bar widgets
  already, both good clone targets for Series 06's "Pro" versions.

The gap between "minimal first-party" and "power-user version" is real,
not invented — that's Series 01's whole reason to exist.

## The marketplace is not empty

`plugins.omarchy.org` (registry: `github.com/HANCORE-linux/omarchy-plugin-marketplace`,
data file `registry.json`) already lists **2,026 published community
plugins** across 2,024 repos, plus 22 retired ones, as of this plan.
Category totals: Widgets 643, Productivity 426, System 288, Developer
Tools 161, Hardware 155, Desktop 152, Appearance 146, Other 55.

This changes how the plan is built, not just what's on the list:

- **Landmines found and routed around**: a Spotify plugin
  (`m4teo.omaspotify`) and three separate wallpaper/theme plugins
  (`theme-picker`, `wallpapermanager`, `wallpaperomarchymanager`) are all
  in the registry's **retired** list. The first-party shell docs also say
  `omarchy.theme-switcher` is "coming soon." Series 07 in `plugins.md`
  already reflects this — the four riskiest theme/wallpaper ideas were
  swapped for lower-collision alternatives.
- **Foundation before feature**: build `Better MPRIS` before `Better
  Spotify` — Spotify's queue/lyrics need its Web API layered on top of
  MPRIS, not instead of it. This is also the likely reason the retired
  Spotify plugin died; don't repeat the shape.
- **Differentiate, don't duplicate**: `omni` (community launcher+AI
  plugin) overlaps `App Launcher Pro` — differentiate as local-only,
  keyboard-first, no cloud/AI dependency. `omarchy-overview` (community
  workspace-overview plugin) overlaps `Window Overview`/`Mission Control`
  — differentiate with search-as-you-type and pinned-app launch, not just
  thumbnails.
- **Standing rule**: before starting any plugin from the list, search
  `plugins.omarchy.org` (or grep a freshly pulled `registry.json`) for the
  concept. Exact functional duplicates get rejected at maintainer review,
  so check first, not after building.

## Shared-infrastructure strategy

Several series share a backend across multiple plugins — build the shared
piece once, then each plugin is a thin front end on top. This mirrors a
pattern already live in the marketplace: `bjarneo/omarchy-shell-plugins`
ships 3 separate plugins from one repo sharing one backend.

- **GitHub cluster** (Dashboard, PRs, Issues, Actions, Notifications,
  Contributions): one repo, one GitHub API client and token handling, six
  manifests. The `ghstats` plugin already installed on this machine
  (`~/.config/omarchy/plugins/io.github.ricky.ghstats/`) is a working
  reference for the GitHub API + bar-widget + panel shape.
- **Docker cluster** (Manager, Stats): one Docker socket poller, two
  manifests.
- **Kubernetes cluster** (Context, Pods): one kubectl wrapper, two
  manifests.
- **Hardware Center**: build the shared polling service first as a
  `service`-kind plugin; every other Series 04 monitor (CPU, GPU, RAM,
  disk, temp, fan, load, etc.) becomes a thin `bar-widget` reading from
  it instead of spawning its own poller — the same split
  `omarchy.battery` and `omarchy.media` already use between `service` and
  `bar-widget`.
- **Better MPRIS**: build first; Album Art, Lyrics, Media Queue, Media
  History, and Now Playing Overlay all attach to it instead of
  re-implementing MPRIS handling five times.

## Build order

1. **Series 01 — omarchy-plus** (15) — clone-and-enhance built-ins. Start
   here: fastest path to something native-feeling, no custom backend work.
2. **Series 06 — omarchy-desktop** (10) — clone-and-enhance
   window/workspace widgets, same reasoning.
3. **Series 04 — omarchy-system** (15) — build `Hardware Center` first,
   then the thin monitor widgets on top of it.
4. **Series 03 — omarchy-dev** (20) — GitHub cluster repo first (best
   visibility, `ghstats` is a working local reference), then Docker/K8s
   clusters, then the standalone tools.
5. **Series 05 — omarchy-media** (10) — `Better MPRIS` foundation first,
   then Spotify and the rest.
6. **Series 02 — omarchy-productivity** (20) — mostly standalone; batch by
   shared local-storage pattern (sqlite/json state file) rather than a
   strict order.
7. **Series 07 — omarchy-theme** (10) — build last. Before starting
   `Theme Scheduler` specifically, re-check whether
   `omarchy.theme-switcher` has shipped first-party in the meantime.

## Quality bar — every plugin, no exceptions

Match the scaffold already used by the `waynergy` plugin on this machine
(`~/.config/omarchy/plugins/io.github.aryan-techie.waynergy/`):

- `README.md`, `LICENSE`, `CHANGELOG.md`
- `manifest.json` with a real, specific `description` (not a placeholder)
- `preview.png`
- `set-keybind.sh` where the widget needs a keybind
- Styling via `qs.Commons` / `qs.Ui` only — no hardcoded colors
- `omarchy plugin validate` clean before every publish
- Id namespaced `io.github.aryan-techie.<slug>`, matching the two plugins
  already shipped (`todoist`, `waynergy`)

## Verification checklist

- [ ] No duplicate id suffixes across all 100 entries in `plugins.md`
- [ ] Every entry namespaced consistently as `io.github.aryan-techie.<slug>`
- [ ] Before each plugin's first commit: fresh `registry.json` pull,
      grep for id/concept collisions
- [ ] `omarchy plugin validate` passes before publishing
- [ ] Manual smoke test: `omarchy plugin clone`/`add`, `omarchy restart
      shell`, confirm hot-reload and bar placement via `omarchy bar move`
