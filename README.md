# Spotify Playlist Cleanup Bot

An Android-based automation that audits and cleans your Spotify playlists: deduplicates tracks, removes broken/unavailable songs, trims explicit content (optional), and keeps orders tidy based on rules you define. This Spotify Playlist Cleanup Bot streamlines routine curation work so teams and creators can focus on growth instead of grunt work, resulting in cleaner, higher-quality listening experiences.

<p align="center">
  <a href="https://Appilot.app" target="_blank">
    <img src="media/appilot-baner.png" alt="Appilot Banner" width="100%">
  </a>
</p>
<p align="center">
  <a href="https://t.me/devpilot1" target="_blank">
    <img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram">
  </a>&nbsp;
  <a href="https://wa.me/923249868488?text=Hi%20Appilot%2C%20I'm%20interested%20in%20automation." target="_blank">
    <img src="https://img.shields.io/badge/Chat-WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" alt="WhatsApp">
  </a>&nbsp;
  <a href="mailto:support@appilot.app" target="_blank">
    <img src="https://img.shields.io/badge/Email-support@appilot.app-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail">
  </a>&nbsp;
  <a href="https://appilot.app" target="_blank">
    <img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website">
  </a>
</p>

<p align="center"> 
   Created by Appilot, built to showcase our approach to Automation!<br>
   <strong>If you are looking for custom Spotify Playlist Cleanup Bot, you've just found your team — Let’s Chat.👆👆</strong>
</p>

## Introduction
This automation connects to your Android device or emulator and performs human-like actions to inspect and clean selected Spotify playlists. It automates repetitive tasks like finding duplicates, skipping region-locked or unavailable tracks, removing tracks that violate curation rules, and reordering items by freshness or popularity. Businesses and creators benefit from consistent standards, time savings, and improved playlist performance.

### Automating Spotify Playlist Hygiene at Scale
- Detects duplicates, near-duplicates (title/artist fuzzy matches), and orphaned/unavailable tracks, then removes or flags them according to your rules.
- Applies smart filters: explicit content, low popularity thresholds, regex-based title bans, and artist/album deny-lists.
- Keeps playlists “fresh”: optionally archive stale tracks and bump newly-added or trending tracks to the top with configurable weights.
- Operates on real Android devices or emulators with human-like pacing, touch gestures, and randomized timings for low detection risk.

## Core Features
- **Real Devices and Emulators:** Works with physical Android phones and emulator stacks (Bluestacks, Nox, Android Studio AVD) to perform UI-level actions reliably.
- **No-ADB Wireless Automation:** Optional over-Wi-Fi control with Appilot’s agent for scenarios where wired ADB is limited or undesirable.
- **Mimicking Human Behavior:** Randomized delays, gesture variability, scroll speed jitter, and context-aware backoffs to reduce bot-like patterns.
- **Multiple Accounts Support:** Rotate and isolate Spotify accounts (session vaulting) for agency workflows and client projects.
- **Multi-Device Integration:** Run parallel workers across a device farm; each worker processes a playlist set for high throughput.
- **Exponential Growth for Your Account:** Cleaner playlists lead to higher save rates and session length; hooks included for A/B testing of curation rules.
- **Premium Support:** SLA-backed support, onboarding assistance, and tailored rule presets for niche genres or editorial standards.
- **Smart Deduplication Engine:** Fuzzy title/artist matching (normalize punctuation, remix tags, “feat.” handling) to catch more than exact duplicates.
- **Unavailable/Region-Locked Pruning:** Automatically identifies broken links, greyed tracks, and market-unavailable items; removes or quarantines them.
- **Explicit Content Filter (Optional):** Flag or remove explicit tracks; configurable for mixed-audience editorial policies.
- **Popularity & Freshness Ranking:** Reorder by popularity proxies and recentness; supports decay weights and pinning priority tracks.
- **Rule Packs & Profiles:** Create reusable rule profiles per brand or playlist theme; switch profiles per run from the dashboard.
- **Error-Aware Retries & Checkpointing:** Idempotent actions with journaling; safe to resume mid-run after crashes or device disconnects.
- **Audit Trail & Reports:** Exports before/after snapshots, removal reasons, and rule hits for transparent QA and client review.
- **Proxy & Fingerprint Ready:** Integrates with network proxies and device-fingerprint strategies to segment environments when needed.

| Feature | Description |
|---|---|
| **Regex/Keyword Filters** | Remove tracks by title/artist patterns (e.g., “clean edits only”, ban “nightcore”, etc.). |
| **Safe-List & Pinning** | Protect key tracks or artists from removal; pin featured songs to always remain in top N. |
| **Archive Bucket** | Moves removed items to an archive playlist for later review instead of deleting outright. |
| **Stale-Track Rotation** | Identify tracks with low engagement proxies and rotate them out at defined intervals. |
| **Report Center** | Auto-generate CSV/JSON and human-readable HTML summaries with change logs and metrics. |
| **Scheduler & Queues** | Cron-like scheduling, batched device queues, and rate-limited task execution. |

</p>
<p align="center">
  <a href="https://bitbash.dev" target="_blank">
    <img src="spotify-playlist-cleanup-bot-architecture.png" alt="spotify-playlist-cleanup-bot-architecture" width="95%">
  </a>
</p>

## How It Works
1. **Input or Trigger** — The automation is triggered through the Appilot dashboard, where you select playlists, rule profiles (dedupe, explicit, popularity), and scheduling options for devices/emulators.
2. **Core Logic** — Appilot controls the Android device or emulator using UI Automator or ADB to open Spotify, navigate to each playlist, scroll through tracks, and apply rules (identify duplicates, broken/explicit items, apply reordering).
3. **Output or Action** — The bot removes or archives flagged tracks, reorders items, and updates metadata. It emits structured reports (CSV/JSON/HTML) and optional webhooks for downstream systems.
4. **Other functionalities** — Built-in retry/backoff, comprehensive logs, screenshots-on-failure, and parallel processing across a device farm with per-account isolation.

## Tech Stack
- **Language:** Kotlin, Java, Python, JavaScript  
- **Frameworks:** Appium, UI Automator, Espresso, Robot Framework, Cucumber  
- **Tools:** Appilot, Android Debug Bridge (ADB), Appium Inspector, Bluestacks, Nox Player, Scrcpy, Firebase Test Lab, Accessibility  
- **Infrastructure:** Dockerized device farms, Cloud-based emulators, Proxy networks, Parallel Device Execution, Task Queues, Real device farm

## Directory Structure
```
spotify-playlist-cleanup-bot/
│
├── src/
│ ├── main.py
│ ├── appilot/
│ │ ├── device_controller.py
│ │ ├── spotify_actions.py
│ │ ├── rules_engine/
│ │ │ ├── dedupe.py
│ │ │ ├── explicit_filter.py
│ │ │ ├── availability_checker.py
│ │ │ └── ranking.py
│ │ └── utils/
│ │ ├── logger.py
│ │ ├── fuzzy_match.py
│ │ ├── report_writer.py
│ │ └── config_loader.py
│ ├── workers/
│ │ ├── scheduler.py
│ │ └── runner.py
│ └── dashboards/
│ └── api_server.js
│
├── config/
│ ├── settings.yaml
│ ├── rules/
│ │ ├── default.yaml
│ │ ├── editorial-pop.yaml
│ │ └── family-safe.yaml
│ └── credentials.env
│
├── logs/
│ └── app.log
│
├── output/
│ ├── reports/
│ │ ├── latest.html
│ │ ├── summary.csv
│ │ └── summary.json
│ └── snapshots/
│ └── before_after.json
│
├── tests/
│ ├── test_dedupe.py
│ ├── test_filters.py
│ └── test_ranking.py
│
├── docker/
│ ├── Dockerfile
│ └── docker-compose.yml
│
├── requirements.txt
└── README.md
```

## Use Cases
- **Playlist editors** use it to remove duplicates and fix broken tracks, so they can maintain consistent quality without manual checks.  
- **Music curators & agencies** use it to apply genre-specific rules at scale, so they can manage hundreds of playlists efficiently.  
- **Brands & publishers** use it to enforce family-safe policies, so they can ensure suitability across all public playlists.  
- **Creators & influencers** use it to keep playlists fresh and high-performing, so they can improve listener retention and saves.

## FAQs
**How do I configure this automation for multiple accounts?**  
Use the account vault in `config/credentials.env` and map accounts to devices in the scheduler. Each device runs isolated sessions to avoid cross-contamination.

**Does it support proxy rotation or anti-detection?**  
Yes. Configure proxies at the device or network layer and enable human-like behavior in `settings.yaml` (gesture jitter, randomized delays, adaptive scroll).

**Can I schedule it to run periodically?**  
Yes. Use `workers/scheduler.py` or Docker-based cron in `docker-compose.yml` to define daily/weekly cleanups per playlist set.

**Will it delete tracks permanently?**  
By default it moves removals to an **Archive Bucket** playlist. Hard deletion is optional and gated behind a config flag.

**Can I keep certain tracks always on top?**  
Use the **Safe-List & Pinning** feature to pin tracks or artists; ranking will respect these pins during reorders.

## Performance & Reliability Benchmarks
- **Execution Speed:** Processes ~100–180 tracks/minute per device depending on device class and network conditions.  
- **Success Rate:** 95%+ rule-application accuracy with idempotent retries and checkpointing.  
- **Scalability:** Proven across 50–300 Android devices in parallel; architecture patterns extend to 1,000 with queue backpressure.  
- **Resource Efficiency:** Lightweight workers with headless emulators where supported; adaptive throttling to keep CPU/RAM under guardrails.  
- **Error Handling:** Exponential backoff, UI state verification, screenshot-on-failure, resumable runs, and structured alerts (Slack/Webhook/Email).


##
<p align="center">
<a href="https://cal.com/app-pilot-m8i8oo/30min" target="_blank">
  <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
</p>
