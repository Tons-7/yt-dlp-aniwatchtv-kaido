# yt-dlp-aniwatchtv-kaido

A [yt-dlp](https://github.com/yt-dlp/yt-dlp) extractor plugin for [aniwatchtv.to](https://aniwatchtv.to) and [kaido.to](https://kaido.to).

Based on [yt-dlp-hianime](https://github.com/pratikpatel8982/yt-dlp-hianime) by pratikpatel8982.

---

## Installation

### Option A — pip (Python yt-dlp)

```
pip install -U https://github.com/Tons-7/yt-dlp-aniwatchtv-kaido/archive/master.zip
```

### Option B — Standalone yt-dlp `.exe` (manual)

1. Download this repo as a ZIP and extract it
2. Create this folder if it doesn't exist:
   ```
   %APPDATA%\yt-dlp\plugins\aniwatch-kaido\yt_dlp_plugins\extractor\
   ```
3. Copy `aniwatch.py`, `kaido.py`, and `megacloud.py` into that folder

The final structure should look like:
```
%APPDATA%\yt-dlp\plugins\aniwatch\yt_dlp_plugins\extractor\aniwatch.py
%APPDATA%\yt-dlp\plugins\aniwatch\yt_dlp_plugins\extractor\kaido.py
%APPDATA%\yt-dlp\plugins\aniwatch\yt_dlp_plugins\extractor\megacloud.py
```

---

## Usage

Once installed, yt-dlp will automatically use this plugin for any `aniwatchtv.to` or `kaido.to` URL — no extra flags needed:

```
yt-dlp "https://aniwatchtv.to/watch/one-piece-100?ep=2142"
```

---

## Extractor Arguments

### `title_lang` — Anime title language

Controls the language of the `series` metadata field. Useful for file naming or player titles.

Value -> Language

`en` -> English (default)

`jp-romaji` -> Romanized Japanese

`jp` -> Japanese kanji/kana

For aniwatchtv.to, use the `aniwatch` key:
```
yt-dlp --extractor-args "aniwatch:title_lang=jp-romaji" "https://aniwatchtv.to/watch/one-piece-100?ep=2142"
```

For kaido.to, use the `kaido` key:
```
yt-dlp --extractor-args "kaido:title_lang=jp-romaji" "https://kaido.to/watch/one-piece-100?ep=2142"
```

## Requirements

- [yt-dlp](https://github.com/yt-dlp/yt-dlp) latest
- Python `requests` library (`pip install requests`)
