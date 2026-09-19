# Akramium

Akramium is a web browser built on Chromium, without Google's services: it starts from
[ungoogled-chromium](https://github.com/ungoogled-software/ungoogled-chromium) and adds its own
parts, written mostly in Rust.

- **Ads and trackers blocked** by a built-in engine that reads uBlock Origin's and EasyList's
  lists, updated every day, including uBlock's YouTube fixes.
- **Tracking parameters removed** from links, and Global Privacy Control sent to every site.
- **Family filter** on by default (adult sites and pictures, safe search, YouTube restricted
  mode); a PIN protects turning it off.
- **Assistant** in the side panel, with the provider of your choice and your own key
  (DeepSeek, OpenAI, Anthropic, Gemini, Mistral, OpenRouter, or a local Ollama or LM Studio).
  The list of models is asked of the provider itself.
- Vertical tabs, reading mode, and the browser's own pages under `akramium://`.
- English, French and Arabic.

## Download

Every release has the same version for every system, on the same Chromium:

| System | File |
|---|---|
| Linux x64 | `akramium-<version>-linux-x64.tar.gz` |
| macOS, Apple silicon | `akramium-<version>-mac-arm64.zip` |

Each file has its `.sha256` next to it. Take the newest release from the
[Releases](https://github.com/Saidoua/akramium/releases) page. The macOS file joins its
release a few hours after the Linux one, the same night.

### Linux

```bash
mkdir -p ~/akramium && tar -xzf akramium-<version>-linux-x64.tar.gz -C ~/akramium --strip-components=1
~/akramium/chrome
```

At its first start Akramium adds itself to your applications menu, with its icon.

### macOS

Unzip, then move **Akramium** to **Applications** and open it. The app is signed with a
Developer ID and notarized by Apple, so macOS opens it like any other downloaded app.

## Updates

- **Linux:** Akramium updates itself in the background and switches to the new version at
  the next start. To look for one now: menu > Help > About Akramium > **Check for update**,
  then **Relaunch**. Updates are signed; Akramium checks the signature before installing.
- **macOS:** no updates from inside the browser yet. Download the new zip from the
  Releases page and replace the app.

Versions are Akramium's own (0.x for now) and follow Chromium's stable channel: when Chromium
ships a security fix, a new Akramium release follows.

## Check a download

```bash
sha256sum -c akramium-<version>-linux-x64.tar.gz.sha256
```

On macOS: `shasum -a 256 -c akramium-<version>-mac-arm64.zip.sha256`

## What this repository holds

Releases only: the packages, their checksums, and the version file
(`update.json` and its signature, also kept current in the `updates` release) that Akramium reads to update itself.
