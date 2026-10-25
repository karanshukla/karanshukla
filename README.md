<div align="center">

<img src="assets/fetch.svg" alt="fastfetch-style card: karan@karanshukla.ca, Fedora Linux and KDE Plasma, Canada, full stack developer and mechanical engineer, Rust / TypeScript / PHP / Python / .NET, local AI on the Intel NPU, AT Protocol" width="880">

<br>

<a href="https://karanshukla.ca"><img alt="Website" src="https://img.shields.io/badge/karanshukla.ca-0e0e10?style=for-the-badge&logo=firefoxbrowser&logoColor=56cc78"></a>
<a href="https://bsky.app/profile/karanshukla.ca"><img alt="Bluesky" src="https://img.shields.io/badge/@karanshukla.ca-0e0e10?style=for-the-badge&logo=bluesky&logoColor=0085ff"></a>
<a href="https://social.linux.pizza/@arankays"><img alt="Mastodon" src="https://img.shields.io/badge/@arankays@social.linux.pizza-0e0e10?style=for-the-badge&logo=mastodon&logoColor=c678dd"></a>
<a href="https://www.linkedin.com/in/shuklakaran"><img alt="LinkedIn" src="https://img.shields.io/badge/shuklakaran-0e0e10?style=for-the-badge&logo=linkedin&logoColor=4ea3ff"></a>
<a href="mailto:karan@karanshukla.ca"><img alt="Email" src="https://img.shields.io/badge/karan@karanshukla.ca-0e0e10?style=for-the-badge&logo=maildotru&logoColor=ffab40"></a>

</div>

<img src="assets/divider.svg" width="100%" alt="">

## Hi, I'm Karan 👋

Full stack developer and mechanical engineer in Canada. I build self-hostable web apps,
tools for the [Bluesky / AT Protocol](https://atproto.com) ecosystem, and local AI that runs
on the Intel NPU most new laptops ship with and almost nobody uses.

To be upfront about my bias: **if it can run on your machine, it should.** Most of what is
below is some version of that argument, written in Rust, TypeScript, PHP, Python or .NET,
depending on what the problem wanted. Daily driver is Fedora with KDE Plasma, so the Linux
desktop tooling is scratching my own itch.

<img src="assets/divider.svg" width="100%" alt="">

## 🍷 vino: local AI on the Intel NPU

A family of Linux tools that share one idea: the NPU in a Core Ultra laptop is sitting idle, so put
it to work and keep the data on the machine. They pin the same OpenVINO release so they can share
the NPU without fighting over runtimes, and [vinoWatch](https://github.com/karanshukla/vinoWatch)
knows all of them by name.

| Project | What it does | Stack | Install |
|---|---|---|---|
| **[vinoWhisper](https://github.com/karanshukla/vinoWhisper)** | Live captions for anything playing on your laptop, plus hold-to-talk dictation. No cloud, no API key, no audio leaving the machine. | Python · Whisper · OpenVINO GenAI | [PyPI](https://pypi.org/project/vinowhisper/) |
| **[vinoSpeak](https://github.com/karanshukla/vinoSpeak)** | Text-to-speech on the NPU using Kokoro-82M INT8. Text in, WAV out. | Python · OpenVINO | [PyPI](https://pypi.org/project/vinospeak/) |
| **[vinoSearch](https://github.com/karanshukla/vinoSearch)** | Search files by what is *in* them, from KRunner or GNOME Shell. Finds `IMG_2041.jpg` from "dog watching the sunset". Warm queries in 26 ms (p50). | Rust · KRunner · inotify | source |
| **[vinoPop](https://github.com/karanshukla/vinoPop)** | PopClip for Linux. Highlight text, get a bar of buttons that fit it: translate, summarize, rewrite, run, all on the local model. | Python · Wayland | source |
| **[vinoWatch](https://github.com/karanshukla/vinoWatch)** | Tray daemon showing what your OpenVINO apps cost in CPU, RAM and NPU load. Goes passive when the NPU idles. | Rust · `ivpu` · tray | source |
| **[vinoAuthFace](https://github.com/karanshukla/vinoAuthFace)** | Windows Hello-style IR face unlock through PAM, built for immutable distros (Kinoite, Bazzite, Bluefin). About 2 seconds from camera poll to authenticated. Fork of [authFace](https://github.com/pfalkingham/authFace). | Rust · PAM · OpenVINO | source |
| **[vinoOpenEffects](https://github.com/karanshukla/vinoOpenEffects)** | OpenVINO-powered webcam effects engine for Linux. Fork. | Rust · OpenVINO | source |
| **[ovfetch](https://github.com/karanshukla/ovfetch)** | Finds, downloads and hash-verifies the OpenVINO-enabled ONNX Runtime that matches your NPU and driver. Checks hashes against multiple independent sources before installing anything. | Rust | [crates.io](https://crates.io/crates/ovfetch) |

Plus [openvino-rs](https://github.com/karanshukla/openvino-rs) and
[awesome-openvino](https://github.com/karanshukla/awesome-openvino), forked because I keep needing them.

## 🦋 Bluesky / AT Protocol

| Project | What it does | Stack | Install |
|---|---|---|---|
| **[kodamachi](https://github.com/karanshukla/kodamachi)** · [kodamachi.app](https://kodamachi.app) | Anonymous Q&A, AT Protocol-native. Receive questions through a public inbox link and post answers straight to your Bluesky feed. Bluesky is the identity provider *and* a secondary data store via PDS sync. Formerly Navyfragen. | TypeScript · Bun · OAuth | hosted |
| **[kodamachi-feed](https://github.com/karanshukla/kodamachi-feed)** | The custom feed generator behind it. Jetstream ingestion, backfill, rate limiting and service auth, ported from TypeScript to PHP on [Tempest](https://github.com/tempestphp/tempest-framework). | PHP 8.5 · SQLite | source |
| **[php-atproto-identity](https://github.com/karanshukla/php-atproto-identity)** | The layer `@atproto/identity` occupies, for PHP. Resolves `did:plc` and `did:web` and turns the published signing key into something OpenSSL can verify. PSR-6 / PSR-18, no bignum extension. | PHP 8.4 · ext-openssl | [Packagist](https://packagist.org/packages/karanshukla/php-atproto-identity) |
| **[bluejays.space](https://github.com/karanshukla/bluejays-space)** | A parody site with fake Toronto Blue Jays headlines, posted over AT Protocol. Not affiliated with MLB, or with reality. | TypeScript · AT Protocol | hosted |

## 🏠 Self-hosted

| Project | What it does | Stack | Install |
|---|---|---|---|
| **[OpenResto](https://github.com/karanshukla/openresto)** · [openres.to](https://openres.to) | A booking system for restaurants, bars and cafés. Customers book from a mobile-friendly web app with no account; owners manage reservations, tables and branding from one dashboard. **Ships as a single Docker Compose stack with zero external services.** | .NET 10 · EF Core · Expo / React Native · Docker | [GHCR](https://github.com/karanshukla/openresto/pkgs/container/openresto-backend) |
| **[openresto-cli](https://github.com/karanshukla/openresto/tree/main/openresto-cli)** | Command-line client for the OpenResto admin API, driven by admin API keys. | TypeScript | [npm](https://www.npmjs.com/package/openresto-cli) |

## 🐧 Linux desktop

| Project | What it does | Stack | Install |
|---|---|---|---|
| **[waydroid-tray](https://github.com/karanshukla/waydroid-tray)** | A KDE Plasma tray icon for Waydroid, which does not ship one of its own. Shows whether the Android session is stopped, frozen or running, starts and stops it, and launches installed Android apps from the panel. | Rust · KDE Plasma · D-Bus | [crates.io](https://crates.io/crates/waydroid-tray) |
| **[karanshukla.ca](https://github.com/karanshukla/karanshukla.ca)** | Not a desktop app, but it is riced like one: a Last.fm now-playing widget, commit summaries generated every 3 days by a GitHub Action, and Lighthouse and coverage scores baked in at build time. Numpad keys 1 to 4 navigate. | React 18 · TypeScript · Vite · MUI | [live](https://karanshukla.ca) |

## 🐱 Cats

| Project | What it does | Stack | Install |
|---|---|---|---|
| **[asher-cli](https://github.com/karanshukla/asher-cli)** | A terminal dashboard for a Litter-Robot (LR3 / LR4 / LR5) via the Whisker cloud API, with live status, fault alerts and animated ASCII cats. Named after the cat. | Python · TUI | [PyPI](https://pypi.org/project/asher-cli/) |
| **[sportsbook-meow](https://github.com/karanshukla/sportsbook-meow)** | Replaces sportsbook ads in sports video with cats, in real time, using a YOLOv8s model fine-tuned on broadcast footage. Works on local files and live streams. | Python · CUDA · YOLOv8 | source |

<img src="assets/divider.svg" width="100%" alt="">

## 📦 Where the packages live

| Registry | Packages |
|---|---|
| [PyPI](https://pypi.org/user/karanshukla/) | [vinowhisper](https://pypi.org/project/vinowhisper/) · [vinospeak](https://pypi.org/project/vinospeak/) · [asher-cli](https://pypi.org/project/asher-cli/) |
| [crates.io](https://crates.io/users/karanshukla) | [ovfetch](https://crates.io/crates/ovfetch) · [waydroid-tray](https://crates.io/crates/waydroid-tray) |
| [npm](https://www.npmjs.com/~karanshukla) | [openresto-cli](https://www.npmjs.com/package/openresto-cli) |
| [Packagist](https://packagist.org/users/karanshukla/) | [karanshukla/php-atproto-identity](https://packagist.org/packages/karanshukla/php-atproto-identity) |

## 📊 Numbers

<div align="center">

<a href="https://github.com/karanshukla?tab=repositories">
  <img src="https://github-readme-stats.vercel.app/api?username=karanshukla&show_icons=true&include_all_commits=true&hide_border=true&bg_color=0e0e10&title_color=56cc78&icon_color=56cc78&text_color=fafafa&ring_color=56cc78&hide_title=true" alt="GitHub stats" height="165">
</a>
<a href="https://github.com/karanshukla?tab=repositories">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=karanshukla&layout=compact&langs_count=8&hide_border=true&bg_color=0e0e10&title_color=56cc78&text_color=fafafa&hide=css,html,scss,shell" alt="Most used languages" height="165">
</a>

</div>

<img src="assets/divider.svg" width="100%" alt="">

## ✍️ Writing

Longer-form things go on [karanshukla.ca](https://karanshukla.ca): why Bluesky's single-region
AppView makes latency hard for anyone outside California, how [Anubis](https://anubis.techaro.lol)
keeps scrapers off a self-hosted box, and a fairly opinionated take on vibe coding.

<div align="center">
<sub>
Everything here is MIT unless the repo says otherwise.
If one of these runs on your machine and nothing leaves it, that was the point.
</sub>
</div>
