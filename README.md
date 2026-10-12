# docker-xml

Poag's Unraid Community Applications template repository. Each app has one XML file under `templates/`, referenced by Unraid via its raw GitHub URL on the `main` branch, and picked up automatically by Community Applications' periodic feed scan.

## Apps

| App | What it does | Source |
|---|---|---|
| [buffarr](templates/buffar.xml) | Two media-automation tools in one container: **prefetch** grabs upcoming episodes of a show you're watching on Jellyfin/Emby/Plex/Tautulli before you catch up to them; **unmonitor** stops Sonarr/Radarr grabbing fake or low-quality pre-release files by holding monitoring until the real air/release date (plus a configurable delay). | [Poag/buffarr](https://github.com/Poag/buffarr) -- image `ghcr.io/poag/buffarr:main` |
| [Decluttarr](templates/decluttarr.xml) | Cleans up stuck, failed, and orphaned downloads across Sonarr, Radarr, Lidarr, Readarr, and Whisparr. | [ManiMatter/decluttarr](https://github.com/ManiMatter/decluttarr) -- image `ghcr.io/manimatter/decluttarr:latest` |
| [Fileflows-Forge](templates/fileflows-forge.xml) | Additional processing node for a FileFlows server, adding remote encode/transcode capacity; supports optional NVIDIA/CUDA GPU acceleration via `ENABLE_CUDA`. | [FileFlows](https://fileflows.com/) -- image `revenz/fileflows-forge` |
| [iPlayarr](templates/iplayarr.xml) | Indexer and download client for Sonarr/Radarr that wraps `get_iplayer`, so BBC iPlayer content can be searched and grabbed like any other release. | [Nikorag/iplayarr](https://github.com/Nikorag/iplayarr) -- image `nikorag/iplayarr:latest` |
| [MeshDash](templates/meshdash.xml) | Self-hosted Meshtastic mesh radio dashboard: packet history, telemetry graphs, node map, messaging. Self-updating runner image that re-downloads the app on every start. Beta. | [ruspea/MeshDash](https://github.com/ruspea/MeshDash) -- image `rusjpmd/meshdash-runner:latest` |
| [MeshSense](templates/meshsense.xml) | Headless web UI that monitors and maps a Meshtastic network over a WiFi/TCP node. | [Affirmatech/MeshSense](https://github.com/Affirmatech/MeshSense) -- image `ghcr.io/poag/meshsense:latest` |
| [TwitchMiner](templates/twitchminer.xml) | Watches Twitch streams on your behalf to farm channel points, catch watch streaks, follow raids, and claim drops. Beta -- first login needs the container console. | [Poag/TwitchMiner](https://github.com/Poag/TwitchMiner) -- image `ghcr.io/poag/twitchminer:latest` |
| [unmonitarr](templates/unmonitarr.xml) | Holds Sonarr monitoring off an episode until it has actually aired, preventing fake or wrong pre-release grabs. | [unmonitarr/unmonitarr](https://github.com/unmonitarr/unmonitarr) -- image `ghcr.io/unmonitarr/unmonitarr:latest` |
| [Watchable](templates/watchable.xml) | Syncs watch state (played/unplayed, in-progress position) between Plex, Jellyfin, and Emby through a local database -- nothing syncs server-to-server directly. YAML-configured. Beta. | [Poag/watchable](https://github.com/Poag/watchable) -- image `ghcr.io/poag/watchable:latest` |

## Repository layout

- `templates/<name>.xml` -- one Unraid CA template per app.
- `images/` -- icons for templates that host their own icon locally rather than pointing at the upstream project's repo.
- `ca_profile.xml` -- repository-level metadata (profile name, icon) shown in Community Applications; not per-app.
- `.unraid/community-apps-claim.json` -- the CA repository ownership claim for this repo.
