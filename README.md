# OMARCHY100

A 100-plugin suite for [Omarchy](https://omarchy.org) Quattro, built native to the Quickshell/QML shell — enhanced built-ins, productivity tools, dev-tool dashboards, system monitors, media controls, window/desktop management, and theming utilities.

Full catalog with feature briefs, technical foundation, and build order: see [`plan.md`](https://github.com/AROICE-HQ/omarchy100/blob/main/plan.md) and [`plugins.md`](https://github.com/AROICE-HQ/omarchy100/blob/main/plugins.md) in this repo.

This repo is the index/tracker only — no plugin code lives here. Each plugin (or shared-backend cluster) ships from its own repo under this org.

## Status tracker

Status: `Idea → Designing → Building → Testing → Pushed → Submitted → Live → Retired`

| # | Plugin | Series | id suffix | Repo | Status |
|---|--------|--------|-----------|------|--------|
| 1 | Better Clock | S01 omarchy-plus | `clock` | [`omarchy-clock`](https://github.com/AROICE-HQ/omarchy-clock) | Submitted ([#4086](https://github.com/omacom/omarchy-plugin-marketplace/issues/4086)) |
| 2 | Better Network | S01 omarchy-plus | `network` | [`omarchy-network`](https://github.com/AROICE-HQ/omarchy-network) | Submitted ([#4096](https://github.com/omacom/omarchy-plugin-marketplace/issues/4096)) |
| 3 | Better Battery | S01 omarchy-plus | `battery` | [`omarchy-battery`](https://github.com/AROICE-HQ/omarchy-battery) | Submitted ([#4100](https://github.com/omacom/omarchy-plugin-marketplace/issues/4100)) |
| 4 | Better Bluetooth | S01 omarchy-plus | `bluetooth` | [`omarchy-bluetooth`](https://github.com/AROICE-HQ/omarchy-bluetooth) | Submitted ([#4104](https://github.com/omacom/omarchy-plugin-marketplace/issues/4104)) |
| 5 | Better Audio | S01 omarchy-plus | `audio` | `omarchy-audio` | Idea |
| 6 | Better Workspace | S01 omarchy-plus | `workspace` | `omarchy-workspace` | Idea |
| 7 | Better Notifications | S01 omarchy-plus | `notifications` | `omarchy-notifications` | Idea |
| 8 | Better System Tray | S01 omarchy-plus | `tray` | `omarchy-tray` | Idea |
| 9 | Better VPN | S01 omarchy-plus | `vpn` | `omarchy-vpn` | Idea |
| 10 | Better Brightness | S01 omarchy-plus | `brightness` | `omarchy-brightness` | Idea |
| 11 | Better Mic | S01 omarchy-plus | `mic` | `omarchy-mic` | Idea |
| 12 | Better Display | S01 omarchy-plus | `display` | `omarchy-display` | Idea |
| 13 | Better Screenshot | S01 omarchy-plus | `screenshot` | `omarchy-screenshot` | Idea |
| 14 | Better Clipboard | S01 omarchy-plus | `clipboard` | `omarchy-clipboard` | Idea |
| 15 | Better Power | S01 omarchy-plus | `power` | `omarchy-power` | Idea |
| 16 | Pomodoro | S02 omarchy-productivity | `pomodoro` | `omarchy-pomodoro` | Idea |
| 17 | Focus Mode | S02 omarchy-productivity | `focus-mode` | `omarchy-focus-mode` | Idea |
| 18 | Quick Notes | S02 omarchy-productivity | `quick-notes` | `omarchy-quick-notes` | Idea |
| 19 | Daily Tasks | S02 omarchy-productivity | `daily-tasks` | `omarchy-daily-tasks` | Idea |
| 20 | Quick Todo | S02 omarchy-productivity | `quick-todo` | `omarchy-quick-todo` | Idea |
| 21 | Habit Tracker | S02 omarchy-productivity | `habit-tracker` | `omarchy-habit-tracker` | Idea |
| 22 | Time Tracker | S02 omarchy-productivity | `time-tracker` | `omarchy-time-tracker` | Idea |
| 23 | Meeting Timer | S02 omarchy-productivity | `meeting-timer` | `omarchy-meeting-timer` | Idea |
| 24 | Agenda | S02 omarchy-productivity | `agenda` | `omarchy-agenda` | Idea |
| 25 | Quick Calendar | S02 omarchy-productivity | `quick-calendar` | `omarchy-quick-calendar` | Idea |
| 26 | Timezone Board | S02 omarchy-productivity | `timezone-board` | `omarchy-timezone-board` | Idea |
| 27 | Quick Calculator | S02 omarchy-productivity | `quick-calculator` | `omarchy-quick-calculator` | Idea |
| 28 | Unit Converter | S02 omarchy-productivity | `unit-converter` | `omarchy-unit-converter` | Idea |
| 29 | Dictionary | S02 omarchy-productivity | `dictionary` | `omarchy-dictionary` | Idea |
| 30 | Translator | S02 omarchy-productivity | `translator` | `omarchy-translator` | Idea |
| 31 | Quick Search | S02 omarchy-productivity | `quick-search` | `omarchy-quick-search` | Idea |
| 32 | Bookmark Manager | S02 omarchy-productivity | `bookmarks` | `omarchy-bookmarks` | Idea |
| 33 | Reading List | S02 omarchy-productivity | `reading-list` | `omarchy-reading-list` | Idea |
| 34 | Quick Links | S02 omarchy-productivity | `quick-links` | `omarchy-quick-links` | Idea |
| 35 | Focus Stats | S02 omarchy-productivity | `focus-stats` | `omarchy-focus-stats` | Idea |
| 36 | GitHub Dashboard | S03 omarchy-dev | `gh-dashboard` | `omarchy-github (cluster)` | Idea |
| 37 | GitHub PRs | S03 omarchy-dev | `gh-prs` | `omarchy-github (cluster)` | Idea |
| 38 | GitHub Issues | S03 omarchy-dev | `gh-issues` | `omarchy-github (cluster)` | Idea |
| 39 | GitHub Actions | S03 omarchy-dev | `gh-actions` | `omarchy-github (cluster)` | Idea |
| 40 | GitHub Notifications | S03 omarchy-dev | `gh-notifications` | `omarchy-github (cluster)` | Idea |
| 41 | GitHub Contributions | S03 omarchy-dev | `gh-contributions` | `omarchy-github (cluster)` | Idea |
| 42 | GitLab Dashboard | S03 omarchy-dev | `gitlab-dashboard` | `omarchy-gitlab-dashboard` | Idea |
| 43 | Linear Dashboard | S03 omarchy-dev | `linear-dashboard` | `omarchy-linear-dashboard` | Idea |
| 44 | Jira Dashboard | S03 omarchy-dev | `jira-dashboard` | `omarchy-jira-dashboard` | Idea |
| 45 | Docker Manager | S03 omarchy-dev | `docker-manager` | `omarchy-docker (cluster)` | Idea |
| 46 | Docker Stats | S03 omarchy-dev | `docker-stats` | `omarchy-docker (cluster)` | Idea |
| 47 | Kubernetes Context | S03 omarchy-dev | `kube-context` | `omarchy-kubernetes (cluster)` | Idea |
| 48 | Kubernetes Pods | S03 omarchy-dev | `kube-pods` | `omarchy-kubernetes (cluster)` | Idea |
| 49 | SSH Manager | S03 omarchy-dev | `ssh-manager` | `omarchy-ssh-manager` | Idea |
| 50 | Port Manager | S03 omarchy-dev | `port-manager` | `omarchy-port-manager` | Idea |
| 51 | Localhost Manager | S03 omarchy-dev | `localhost-manager` | `omarchy-localhost-manager` | Idea |
| 52 | Process Manager | S03 omarchy-dev | `process-manager` | `omarchy-process-manager` | Idea |
| 53 | Dev Environment | S03 omarchy-dev | `dev-environment` | `omarchy-dev-environment` | Idea |
| 54 | Node Version Switcher | S03 omarchy-dev | `node-version` | `omarchy-node-version` | Idea |
| 55 | Python Environment Switcher | S03 omarchy-dev | `python-env` | `omarchy-python-env` | Idea |
| 56 | CPU Monitor | S04 omarchy-system | `cpu-monitor` | `omarchy-hardware (cluster)` | Idea |
| 57 | GPU Monitor | S04 omarchy-system | `gpu-monitor` | `omarchy-hardware (cluster)` | Idea |
| 58 | RAM Monitor | S04 omarchy-system | `ram-monitor` | `omarchy-hardware (cluster)` | Idea |
| 59 | Disk Monitor | S04 omarchy-system | `disk-monitor` | `omarchy-hardware (cluster)` | Idea |
| 60 | Network Monitor | S04 omarchy-system | `net-monitor` | `omarchy-hardware (cluster)` | Idea |
| 61 | Network Speed | S04 omarchy-system | `net-speed` | `omarchy-hardware (cluster)` | Idea |
| 62 | Temperature Center | S04 omarchy-system | `temp-center` | `omarchy-hardware (cluster)` | Idea |
| 63 | Fan Monitor | S04 omarchy-system | `fan-monitor` | `omarchy-hardware (cluster)` | Idea |
| 64 | System Load | S04 omarchy-system | `system-load` | `omarchy-hardware (cluster)` | Idea |
| 65 | Process Monitor | S04 omarchy-system | `process-monitor` | `omarchy-hardware (cluster)` | Idea |
| 66 | Systemd Manager | S04 omarchy-system | `systemd-manager` | `omarchy-hardware (cluster)` | Idea |
| 67 | USB Manager | S04 omarchy-system | `usb-manager` | `omarchy-hardware (cluster)` | Idea |
| 68 | Drive Manager | S04 omarchy-system | `drive-manager` | `omarchy-hardware (cluster)` | Idea |
| 69 | Bluetooth Battery | S04 omarchy-system | `bt-battery` | `omarchy-hardware (cluster)` | Idea |
| 70 | Hardware Center | S04 omarchy-system | `hardware-center` | `omarchy-hardware (cluster)` | Idea |
| 71 | Better MPRIS | S05 omarchy-media | `mpris` | `omarchy-media (cluster)` | Idea |
| 72 | Better Spotify | S05 omarchy-media | `spotify` | `omarchy-media (cluster)` | Idea |
| 73 | Album Art | S05 omarchy-media | `album-art` | `omarchy-media (cluster)` | Idea |
| 74 | Lyrics | S05 omarchy-media | `lyrics` | `omarchy-media (cluster)` | Idea |
| 75 | Media Queue | S05 omarchy-media | `media-queue` | `omarchy-media (cluster)` | Idea |
| 76 | Audio Device Switcher | S05 omarchy-media | `audio-device-switcher` | `omarchy-media (cluster)` | Idea |
| 77 | Microphone Studio | S05 omarchy-media | `mic-studio` | `omarchy-media (cluster)` | Idea |
| 78 | Media History | S05 omarchy-media | `media-history` | `omarchy-media (cluster)` | Idea |
| 79 | Volume Mixer | S05 omarchy-media | `volume-mixer` | `omarchy-media (cluster)` | Idea |
| 80 | Now Playing Overlay | S05 omarchy-media | `now-playing-overlay` | `omarchy-media (cluster)` | Idea |
| 81 | Omarchy Alt-Tab+ | S06 omarchy-desktop | `alt-tab-plus` | `omarchy-alt-tab-plus` | Idea |
| 82 | Window Overview | S06 omarchy-desktop | `window-overview` | `omarchy-window-overview` | Idea |
| 83 | Active Window Pro | S06 omarchy-desktop | `active-window-pro` | `omarchy-active-window-pro` | Idea |
| 84 | Workspace Manager | S06 omarchy-desktop | `workspace-manager` | `omarchy-workspace-manager` | Idea |
| 85 | Window Rules Manager | S06 omarchy-desktop | `window-rules-manager` | `omarchy-window-rules-manager` | Idea |
| 86 | Keybind Manager Pro | S06 omarchy-desktop | `keybind-manager-pro` | `omarchy-keybind-manager-pro` | Idea |
| 87 | Display Manager Pro | S06 omarchy-desktop | `display-manager-pro` | `omarchy-display-manager-pro` | Idea |
| 88 | Dock Profiles | S06 omarchy-desktop | `dock-profiles` | `omarchy-dock-profiles` | Idea |
| 89 | Workspace Presets | S06 omarchy-desktop | `workspace-presets` | `omarchy-workspace-presets` | Idea |
| 90 | App Launcher Pro | S06 omarchy-desktop | `app-launcher-pro` | `omarchy-app-launcher-pro` | Idea |
| 91 | Theme Scheduler | S07 omarchy-theme | `theme-scheduler` | `omarchy-theme-scheduler` | Idea |
| 92 | Font Manager | S07 omarchy-theme | `font-manager` | `omarchy-font-manager` | Idea |
| 93 | Cursor Manager | S07 omarchy-theme | `cursor-manager` | `omarchy-cursor-manager` | Idea |
| 94 | Rice Manager | S07 omarchy-theme | `rice-manager` | `omarchy-rice-manager` | Idea |
| 95 | Omarchy Backup | S07 omarchy-theme | `omarchy-backup` | `omarchy-omarchy-backup` | Idea |
| 96 | Omarchy Profiles | S07 omarchy-theme | `omarchy-profiles` | `omarchy-omarchy-profiles` | Idea |
| 97 | Mission Control | S07 omarchy-theme | `mission-control` | `omarchy-mission-control` | Idea |
| 98 | Icon Theme Switcher | S07 omarchy-theme | `icon-theme-switcher` | `omarchy-icon-theme-switcher` | Idea |
| 99 | Accent Picker | S07 omarchy-theme | `accent-picker` | `omarchy-accent-picker` | Idea |
| 100 | GTK/Qt Sync Checker | S07 omarchy-theme | `gtk-qt-sync-checker` | `omarchy-gtk-qt-sync-checker` | Idea |
