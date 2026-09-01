# OMARCHY100 — Plugin Catalog

100 plugins across 7 series. Every id below is a suffix on
`io.github.aryan-techie.<slug>`. Kind values map to Omarchy's
`manifest.json` `kinds` field (`bar-widget`, `panel`, `overlay`,
`service`). See [`plan.md`](./plan.md) for the technical foundation,
market-collision notes, shared-infrastructure grouping, and build order.

---

## Series 01 — omarchy-plus (Better Built-ins)

Enhanced versions of bar widgets Omarchy already ships. Start every item
here with `omarchy plugin clone omarchy.<widget>` where a first-party
counterpart exists.

| # | Plugin | id | Kind | Feature brief |
|---|--------|----|----|----------------|
| 1 | Better Clock | `clock` | bar-widget | Clone `omarchy.clock`; world-clock rows, seconds toggle, ISO week number, agenda dots on the calendar popup. |
| 2 | Better Network | `network` | bar-widget | Clone `omarchy.network`; bandwidth graph, interface/DNS switch, captive-portal detection. |
| 3 | Better Battery | `battery` | bar-widget + service | First bar pill for battery (today it's service-only); charge %, health/wear, time-to-full/empty, inline power-profile switch. |
| 4 | Better Bluetooth | `bluetooth` | bar-widget | Clone `omarchy.bluetooth`; per-device battery %, auto-reconnect toggle, codec display. |
| 5 | Better Audio | `audio` | bar-widget | Output/input switcher plus a per-app volume mixer the first-party panel doesn't have. |
| 6 | Better Workspace | `workspace` | bar-widget | Clone `Workspaces.qml`; per-workspace app-icon counts and live thumbnails. |
| 7 | Better Notifications | `notifications` | panel | Clone `omarchy.notifications`; searchable history, do-not-disturb schedule. |
| 8 | Better System Tray | `tray` | bar-widget | Clone `Tray.qml`; grouping/hide-rules for noisy tray icons. |
| 9 | Better VPN | `vpn` | bar-widget + service | Unify WireGuard, Tailscale, Mullvad, and commercial VPN status in one pill. |
| 10 | Better Brightness | `brightness` | bar-widget | Per-monitor brightness sliders (ddcutil/backlight), not just the laptop panel. |
| 11 | Better Mic | `mic` | bar-widget | Clone `Microphone.qml`; mute-state history, per-app input routing. |
| 12 | Better Display | `display` | panel | Monitor profiles, resolution/refresh switch, quick layout presets. |
| 13 | Better Screenshot | `screenshot` | overlay | Capture, history strip, inline annotate — wraps `omarchy screenshot`. |
| 14 | Better Clipboard | `clipboard` | overlay | Clone `omarchy.clipboard`; search, pinning, image thumbnails. |
| 15 | Better Power | `power` | bar-widget | Clone `omarchy.power`; suspend/hibernate/power-profile picker in one pill. |

---

## Series 02 — omarchy-productivity

Personal daily-use tools. Mostly standalone; no first-party overlap to
worry about.

| # | Plugin | id | Kind | Feature brief |
|---|--------|----|----|----------------|
| 16 | Pomodoro | `pomodoro` | bar-widget | Native focus timer with a bar countdown pill. |
| 17 | Focus Mode | `focus-mode` | bar-widget + service | Mutes notifications and starts a timer together. |
| 18 | Quick Notes | `quick-notes` | overlay | Instant keybind-summoned scratchpad. |
| 19 | Daily Tasks | `daily-tasks` | panel | Today's task list, local storage. |
| 20 | Quick Todo | `quick-todo` | overlay | Keyboard-first single-line task entry. |
| 21 | Habit Tracker | `habit-tracker` | panel | Daily habit check-in grid. |
| 22 | Time Tracker | `time-tracker` | bar-widget | Project/session tracking with a running pill. |
| 23 | Meeting Timer | `meeting-timer` | bar-widget | Visible countdown for meetings. |
| 24 | Agenda | `agenda` | panel | Today's calendar (Better Clock) + tasks (Daily Tasks) merged. |
| 25 | Quick Calendar | `quick-calendar` | overlay | Calendar popup on a keybind. |
| 26 | Timezone Board | `timezone-board` | panel | Multiple cities/timezones at a glance. |
| 27 | Quick Calculator | `quick-calculator` | overlay | Calculator summoned by keybind. |
| 28 | Unit Converter | `unit-converter` | overlay | Units/currency/time conversion. |
| 29 | Dictionary | `dictionary` | overlay | Instant word lookup, selection-aware. |
| 30 | Translator | `translator` | overlay | Selected text to translation. |
| 31 | Quick Search | `quick-search` | overlay | Universal web-search launcher. |
| 32 | Bookmark Manager | `bookmarks` | panel | Keyboard-first bookmark list. |
| 33 | Reading List | `reading-list` | panel | Save URLs for later. |
| 34 | Quick Links | `quick-links` | bar-widget | Customizable URL launcher pill. |
| 35 | Focus Stats | `focus-stats` | panel | Rolls up Pomodoro/Focus Mode/Time Tracker into daily stats. |

---

## Series 03 — omarchy-dev

GitHub cluster (36–41) shares one repo and one API client. Docker cluster
(45–46) shares one poller. Kubernetes cluster (47–48) shares one kubectl
wrapper. See `plan.md` for the shared-infrastructure reasoning.

| # | Plugin | id | Kind | Feature brief |
|---|--------|----|----|----------------|
| 36 | GitHub Dashboard | `gh-dashboard` | bar-widget + panel | PRs/issues/reviews summary. |
| 37 | GitHub PRs | `gh-prs` | bar-widget | Active PR count and list. |
| 38 | GitHub Issues | `gh-issues` | bar-widget | Assigned issues. |
| 39 | GitHub Actions | `gh-actions` | bar-widget | CI run status. |
| 40 | GitHub Notifications | `gh-notifications` | bar-widget | Notification counter. |
| 41 | GitHub Contributions | `gh-contributions` | panel | Contribution streak/heatmap. Reference: installed `ghstats` plugin. |
| 42 | GitLab Dashboard | `gitlab-dashboard` | bar-widget + panel | PRs/issues/pipelines summary. |
| 43 | Linear Dashboard | `linear-dashboard` | bar-widget + panel | Assigned issues and cycle status. |
| 44 | Jira Dashboard | `jira-dashboard` | bar-widget + panel | Assigned tickets and sprint status. |
| 45 | Docker Manager | `docker-manager` | panel | Container list, start/stop/logs. |
| 46 | Docker Stats | `docker-stats` | bar-widget | CPU/RAM/network per container. |
| 47 | Kubernetes Context | `kube-context` | bar-widget | Current cluster/context/namespace. |
| 48 | Kubernetes Pods | `kube-pods` | panel | Pod health across the current context. |
| 49 | SSH Manager | `ssh-manager` | panel | Saved connections, one-click connect. |
| 50 | Port Manager | `port-manager` | panel | Listening ports + owning process. |
| 51 | Localhost Manager | `localhost-manager` | panel | Detect running dev servers. |
| 52 | Process Manager | `process-manager` | panel | Interactive process killer. |
| 53 | Dev Environment | `dev-environment` | bar-widget | Current project/toolchain indicator. |
| 54 | Node Version Switcher | `node-version` | bar-widget | Active Node version, quick switch. |
| 55 | Python Environment Switcher | `python-env` | bar-widget | Active venv/interpreter, quick switch. |

---

## Series 04 — omarchy-system

Build **Hardware Center** (#70) first as the shared polling service;
items 56–69 are thin bar-widgets reading from it instead of each
spawning its own poller.

| # | Plugin | id | Kind | Feature brief |
|---|--------|----|----|----------------|
| 56 | CPU Monitor | `cpu-monitor` | bar-widget | Usage/temp/frequency. |
| 57 | GPU Monitor | `gpu-monitor` | bar-widget | Usage/temp/memory. |
| 58 | RAM Monitor | `ram-monitor` | bar-widget | Memory pressure. |
| 59 | Disk Monitor | `disk-monitor` | bar-widget | Usage + I/O. |
| 60 | Network Monitor | `net-monitor` | bar-widget | Bandwidth over time (distinct from Better Network's connection status). |
| 61 | Network Speed | `net-speed` | bar-widget | Live upload/download numbers. |
| 62 | Temperature Center | `temp-center` | panel | All sensors in one view. |
| 63 | Fan Monitor | `fan-monitor` | bar-widget | Fan RPM. |
| 64 | System Load | `system-load` | bar-widget | Load averages. |
| 65 | Process Monitor | `process-monitor` | panel | Top-N processes (read-only complement to Process Manager's killer). |
| 66 | Systemd Manager | `systemd-manager` | panel | Service status/control. |
| 67 | USB Manager | `usb-manager` | panel | Connected devices. |
| 68 | Drive Manager | `drive-manager` | panel | Mounted drives. |
| 69 | Bluetooth Battery | `bt-battery` | bar-widget | Standalone peripheral-battery pill for people who don't want the full Better Bluetooth widget. |
| 70 | Hardware Center | `hardware-center` | service + panel | Shared polling daemon + unified hardware dashboard. Build first in this series. |

---

## Series 05 — omarchy-media

Build **Better MPRIS** (#71) first; everything else attaches to it. A
prior Spotify plugin (`omaspotify`) was retired from the marketplace —
build the generic MPRIS foundation before any Spotify-specific layer.

| # | Plugin | id | Kind | Feature brief |
|---|--------|----|----|----------------|
| 71 | Better MPRIS | `mpris` | service + bar-widget | Enhanced generic player controls; foundation for the rest of this series. |
| 72 | Better Spotify | `spotify` | panel | Thin layer on Better MPRIS + Spotify Web API for queue/lyrics MPRIS can't provide. |
| 73 | Album Art | `album-art` | bar-widget | Large now-playing art pill. |
| 74 | Lyrics | `lyrics` | panel | Synchronized lyrics overlay. |
| 75 | Media Queue | `media-queue` | panel | Queue management. |
| 76 | Audio Device Switcher | `audio-device-switcher` | bar-widget | Instant output switch (single-purpose, vs. Better Audio's full mixer). |
| 77 | Microphone Studio | `mic-studio` | panel | Input device/gain controls. |
| 78 | Media History | `media-history` | panel | Recently played. |
| 79 | Volume Mixer | `volume-mixer` | panel | Per-application audio levels. |
| 80 | Now Playing Overlay | `now-playing-overlay` | overlay | Large transient now-playing UI on keybind. |

---

## Series 06 — omarchy-desktop

Clone `ActiveWindow.qml` / `Workspaces.qml` where noted — both are
already first-party bar widgets.

| # | Plugin | id | Kind | Feature brief |
|---|--------|----|----|----------------|
| 81 | Omarchy Alt-Tab+ | `alt-tab-plus` | overlay | Smarter window switcher. |
| 82 | Window Overview | `window-overview` | overlay | All windows/workspaces, search-as-you-type. Differentiate from the community `omarchy-overview` plugin, which is thumbnails-only. |
| 83 | Active Window Pro | `active-window-pro` | bar-widget | Clone `ActiveWindow.qml`; icon/title/app metadata. |
| 84 | Workspace Manager | `workspace-manager` | panel | Visual workspace control. |
| 85 | Window Rules Manager | `window-rules-manager` | panel | GUI over Hyprland `windowrulev2`. |
| 86 | Keybind Manager Pro | `keybind-manager-pro` | panel | Visual keybind editor. |
| 87 | Display Manager Pro | `display-manager-pro` | panel | Monitor profiles. |
| 88 | Dock Profiles | `dock-profiles` | service | Automatic monitor/dock layout switching. |
| 89 | Workspace Presets | `workspace-presets` | panel | Save/restore workspace arrangements. |
| 90 | App Launcher Pro | `app-launcher-pro` | overlay | Keyboard-first fuzzy launcher, local-only. Differentiate from the community `omni` plugin, which is cloud/AI-based. |

---

## Series 07 — omarchy-theme

Revised: Theme Switcher Pro and three wallpaper-manager ideas were
dropped — three past plugins in that exact space are already retired from
the marketplace, and Omarchy's own shell docs list `omarchy.theme-switcher`
as a coming first-party feature. Items 97–100 replace them with
lower-collision ideas. Build this series last, and re-check
`omarchy.theme-switcher`'s status before starting #91.

| # | Plugin | id | Kind | Feature brief |
|---|--------|----|----|----------------|
| 91 | Theme Scheduler | `theme-scheduler` | service | Schedule theme changes by time of day. Re-check `omarchy.theme-switcher` first-party status before starting. |
| 92 | Font Manager | `font-manager` | panel | Switch system fonts. |
| 93 | Cursor Manager | `cursor-manager` | panel | Cursor theme switching. |
| 94 | Rice Manager | `rice-manager` | panel | Save/restore dotfiles and config state — full setup snapshots, not colors. |
| 95 | Omarchy Backup | `omarchy-backup` | panel | Backup/restore shell, config, and theme state. |
| 96 | Omarchy Profiles | `omarchy-profiles` | bar-widget + panel | Work / Gaming / Dev / Travel mode switch: bundles wallpaper, app set, DND, and monitor layout together. |
| 97 | Mission Control | `mission-control` | overlay | macOS-style all-workspace grid + app search overview. Differentiate from the community `omarchy-overview` plugin with search and pinned-app launch actions. *(replaces Theme Switcher Pro)* |
| 98 | Icon Theme Switcher | `icon-theme-switcher` | panel | Swap GTK/Qt icon packs system-wide — icon packs, not color themes, so lower collision risk. *(replaces Wallpaper Manager)* |
| 99 | Accent Picker | `accent-picker` | overlay | Live accent-color-only tweaks previewed across bar/panels, short of a full theme swap. *(replaces Dynamic Wallpaper)* |
| 100 | GTK/Qt Sync Checker | `gtk-qt-sync-checker` | bar-widget | Flags when GTK and Qt app theming has drifted apart, one-click re-sync. *(replaces Wallpaper Randomizer)* |

---

## Before building any of these

Search `plugins.omarchy.org` (or grep a freshly pulled `registry.json`
from `github.com/HANCORE-linux/omarchy-plugin-marketplace`) for the
concept first. The marketplace already has 2,026 published plugins —
exact functional duplicates get rejected at maintainer review.
