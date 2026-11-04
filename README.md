# heloX
A simple open source unblocked gaming site thats self hosted and has a custom made fully frontend media system.


## Features
- **Proxy** — browse any site through the built-in fully frontend Ultraviolet proxy
- **Apps** — quick links to popular sites, opened through the built-in proxy
- **Games** — curated game library + add your own or submit for review to be added
- **Media** — search and watch movies & TV shows via TMDB and CinemaOS

## Add apps
Open `public/apps.html` and add an entry to the `apps` list in its script. Each entry needs a display name and a full website URL:

```js
{ name: "Example", url: "https://example.com" }
```

The Apps page automatically creates a searchable shortcut for every entry and opens it through Ultraviolet.

## Add games
Add a game object to `public/games/games-list.json`. Use `file` for a game hosted in this repo, or `url` for a hosted game. Add a thumbnail under `public/games/thumbs/` and point `thumbnail` to its public path.

```json
{
	"id": "example-game",
	"title": "Example Game",
	"thumbnail": "/games/thumbs/example-game.jpg",
	"file": "/games/files/example-game/index.html"
}
```

For a locally hosted game, put its files in `public/games/files/example-game/` and set `file` to its entry page. For a hosted game, replace `file` with a `url` field, for example `"url": "https://example.com/game"`. Use `remoteHtml` for a standalone HTML file fetched when opened; the host must allow cross-origin requests. Keep each `id` unique and verify the referenced file, URL, and thumbnail.

## Keep the site online
Codespaces are for development and stop when they are shut down. To keep the site available, deploy this repository to Vercel using the included `vercel.json` configuration and connect the repository for automatic production deployments. Once deployed, the site is served by Vercel, while the Selenite games and cover art load from the pinned Selenite repository revision via raw.githack.com; neither depends on an active Codespace. The Vercel project must be enabled in its dashboard before it can serve traffic.

## Credits
- [Ultraviolet](https://github.com/titaniumnetwork-dev/Ultraviolet) - proxy code + uv setup
- [55gms](https://github.com/55GMS/55gms) - bunch of games
- [truffled](https://truffled.lol) - games
- [Selenite](https://github.com/scvjn9z4db-ops/selenite-old) - additional games and cover art

creds to grant made with po labs and formaly po.games
