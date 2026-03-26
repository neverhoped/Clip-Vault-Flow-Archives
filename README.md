# ClipVault — Flow Archives

A visual clip library for anime editing communities. Browse, search, and organize sakuga clips with a clean glassmorphism interface — no backend required.

**[Live Demo](https://neverhoped.github.io/Clip-Vault-Flow-Archives/)** · **[Discord](https://discord.gg/6qNtYym7dD)** · **[Support](https://buymeacoffee.com/xayvis)**

---

## Overview

ClipVault is a static site built for my Discord Flow Archives that collect and share anime clips. Instead of clips getting lost in chat, they're organized in a browsable library with thumbnails, tags, and direct links.

All clip data lives in a single `data.json` file. Sakugabooru is used for the clips.

## Features

**Browsing & Discovery**
- Folder navigation: Anime → Scene Type → Character → Clips
- Full-text search across names, anime, characters, and tags
- Tag filter bar with the most-used tags shown on the homepage
- Random clip button for quick discovery
- Video preview on hover for `.mp4` links (sakugabooru, direct video URLs)
- One-click copy URL for editors who need the direct link

**Clip Management**
- Add, edit, and delete clips through the UI
- Quick Mode — keeps anime/character/tags filled when adding multiple clips from the same series
- Bulk JSON paste for importing many clips at once
- Export/Import `data.json` for backups and updates

**Design**
- Glassmorphism UI with frosted glass cards, mesh gradient background, and particle animation
- Dark and light mode with saved preference
- Smooth page transitions between folders
- Folder cards show thumbnail previews from their clips
- Fully responsive on mobile

## Setup

1. **Fork or clone this repository**

2. **Enable GitHub Pages**
   - Go to Settings → Pages
   - Set source to `main` branch, root folder
   - Your site will be live at `https://yourusername.github.io/Clip-Vault-Flow-Archives/`

3. **Add your clips**
   - Open the site and click **Manage**
   - Add clips through the form or use **Bulk Paste** with a JSON array
   - Click **Export** to download your `data.json`
   - Commit the updated `data.json` to your repo

## Data Format

Clips are stored in `data.json` as an array of objects:

```json
[
  {
    "id": "c_1774270580522_7727",
    "anime": "Fire Force",
    "sceneType": "Action",
    "character": "Shinra",
    "name": "Shinra shoots gun",
    "thumbnail": "https://i.imgur.com/example.jpg",
    "discordLink": "https://www.sakugabooru.com/data/example.mp4",
    "tags": ["Gun", "Shooting"],
    "addedAt": "2026-03-23"
  }
]
```

| Field | Required | Description |
|-------|----------|-------------|
| `id` | Yes | Unique identifier (auto-generated) |
| `anime` | Yes | Series name |
| `sceneType` | Yes | Category (Action, Sad, Funny, etc.) |
| `character` | Yes | Character featured |
| `name` | Yes | Short description of the clip |
| `thumbnail` | No | Direct image URL for the preview card |
| `discordLink` | Yes | URL to the clip (video link or Discord message) |
| `tags` | No | Array of searchable tags |
| `addedAt` | No | Date added (YYYY-MM-DD) |

## Thumbnails

For reliable thumbnails, use permanent hosting. Discord CDN links expire after a few hours.

**Recommended options:**
- [Imgur](https://imgur.com) — upload the screenshot, use the direct `https://i.imgur.com/...` link
- GitHub — store images in an `images/` folder in this repo and reference them with `https://github.com/yourusername/repo/blob/main/images/filename.png?raw=true`

## Project Structure

```
├── index.html      # The entire application (single file)
├── data.json       # Clip database
├── favicon-32.png  # Browser tab icon
└── README.md
```

## Tech Stack

- Vanilla HTML, CSS, JavaScript — no frameworks or build tools
- GitHub Pages for hosting
- `data.json` fetched at runtime — no build step needed to update clips

## Contributing

This project is maintained for the Flow Archives community. If you'd like to contribute clips or suggest features, join the [Discord server](https://discord.gg/6qNtYym7dD).

## License

This project is provided as-is for community use.

---

Built by [xay.vis](https://buymeacoffee.com/xayvis)
