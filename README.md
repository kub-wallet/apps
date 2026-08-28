# KUB Wallet App Registry

Name, description, logo, screenshots, and URL for applications shown on KUB Wallet's app page.

Full submission guide: [Add New Apps to KUB Wallet](https://bitkub-blockchain.gitbook.io/kub-wallet/assets/add-new-apps-to-kub-wallet).
This README is the field reference.

## Layout

One directory per app, named with a stable lowercase kebab-case slug.

```
apps/
  example-app/
    app.json
    logo/
      logo.svg
    screenshot/
      1.png
      2.png
```

The slug is the app's identity and does not change, even if the app moves to a new domain. A submission adds exactly one directory. Pull requests touching more than one app will be asked to split.

## `app.json`

```json
{
  "name": "Example App",
  "description": "This is an app description.",
  "category": "defi",
  "url": "https://example.com",
  "logo": "logo/logo.svg",
  "screenshots": [
    "screenshot/1.png",
    "screenshot/2.png"
  ]
}
```

| Field | Type | Notes |
|---|---|---|
| `name` | string | Display name |
| `description` | string | 1–3 sentences on what the app does |
| `category` | string | One value from the list below |
| `url` | string | `https://` only |
| `logo` | string | Path to the logo, relative to this directory |
| `screenshots` | array | 2 to 4 paths, in display order |

All six fields are required. Any field not listed here will be rejected. If you think something is missing, open an issue rather than adding it to your entry.

### Category

Pick the **one** that best describes what your app primarily does. One category per app,
so the app page groups deterministically.

| | |
|---|---|
| `defi` | Swaps, AMMs, lending, staking, bridges, payments |
| `game` | Games, game economies, in-game assets |
| `marketplace` | NFT and collectible marketplaces, minting, tokenised real-world assets |
| `tools` | Explorers, dashboards, portfolio trackers, developer tools |
| `social` | Social, identity, community, content applications |

If nothing fits, open an issue rather than forcing your app into `tools`. A category that keeps getting misused is a category list that needs changing.

## Logo

Put it in `logo/logo.svg` or `logo/logo.png`.

- 1:1 square
- SVG preferred. Self-contained only.
- PNG accepted at 256×256 or larger
- Under 100 KB

A logo close to an already-listed app's logo will be rejected. So will a name close to an existing one.

## Screenshots

Put them in `screenshot/` as `1.png`, `2.png`, `3.png`, `4.png`.

- 2 to 4 images of the working application
- PNG, 16:9, under 500 KB each
- The `screenshots` array in `app.json` sets the display order

Filenames are ordinals so that reordering shows up as a rename in the diff. Any file in `screenshot/` that the array does not point at will be flagged.

## Submitting

1. Fork this repository
2. Create `apps/<slug>/` with your `app.json`, `logo/`, and `screenshot/`
3. Open a pull request

The GitHub web editor is enough, you do not need a local Git setup.

Put your contact in the pull request description, not in `app.json`.** This repository is public and permanent. We need a contact that reaches a human, including for security reports, and it is how we reach you if something goes wrong with your app addition later.