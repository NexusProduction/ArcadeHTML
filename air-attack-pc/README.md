# Skyfront: Island Defender — PC browser port prototype

This folder contains a standalone, ad-free-by-default browser shooter based on broad arcade flight-combat mechanics observed in the supplied **Air Attack (Ads)** APK. It is a clean-room implementation with original Canvas graphics; it does not ship the APK's sprites, soundtrack, or compiled code.

## Play and controls

Open `index.html` in a modern browser, or run `python -m http.server 8000` in this folder and visit `http://localhost:8000`.

- **WASD / arrow keys:** move
- **Hold Space:** fire
- **X:** heavy bomb (clears on-screen aircraft, ground targets, and hostile fire)
- **P / Esc:** pause or resume
- **Click and drag:** steer and fire
- **Fullscreen:** use the button below the game

## Implemented systems

- Three difficulty profiles
- Scrolling procedural ocean and island environment
- Scout, bomber, and gunship enemy classes
- Ground installations: turrets, bunkers, radar posts, depots
- Enemy projectiles, collisions, damage feedback, explosions and screen shake
- Heavy bombs, repair drops, extra bombs, spread fire, weapon upgrades
- Score, locally saved best score, lives, pause/restart, sound toggle and fullscreen
- No backend, install step, external runtime dependency, or ad code enabled by default

This is a playable prototype, **not an exact or complete 1:1 port**. It does not implement the original game's exact physics, maps, AI, levels, art, music, progression, Android features, or multiplayer.

## Publish through your existing GitHub repository

This file was added at `air-attack-pc/index.html` in [NexusProduction/ArcadeHTML](https://github.com/NexusProduction/ArcadeHTML).

If GitHub Pages is already enabled for that repository and publishing from the `main` branch root, the intended URL is:

`https://nexusproduction.github.io/ArcadeHTML/air-attack-pc/`

I could commit the files to the repository, but I could not verify or change the repository's Pages setting through the available connection. To enable it manually:

1. Open the repository's **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/(root)`, then save.
4. Wait for GitHub Pages to report the deployment as successful and open the URL above.

If the repo already uses a custom deployment workflow, keep its existing settings and verify that it publishes the new `air-attack-pc/` folder along with the rest of the site.

## Add Adsterra Popunder ads

There is a marked placeholder near the top of `index.html` inside `<head>`. It is intentionally empty so no unauthorized, made-up, or borrowed ad code runs.

1. In your Adsterra publisher dashboard, submit your actual website URL/domain and select the **Popunder** ad unit (or choose a less disruptive format).
2. Wait until the website/ad unit is approved and active.
3. Open **Get code** in the publisher dashboard and copy the exact script generated for your own website/account.
4. Paste that snippet into the marked placeholder in `index.html`, immediately before `</head>`.
5. Commit the updated file, let the site redeploy, then test the real HTTPS URL in a browser.

Official instructions: [Adsterra's Popunder setup guide](https://adsterra.com/blog/popunder-traffic-monetization/) and [GitHub Pages setup](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).

Important: GitHub Pages is static hosting, and monetization/site approval is not guaranteed. If Adsterra does not approve the GitHub Pages host, use a domain and host that its publisher requirements accept. Keep the game as the site's primary content, follow GitHub's [Acceptable Use Policies](https://docs.github.com/en/site-policy/acceptable-use-policies/github-acceptable-use-policies), and test with popup blocking/anti-tracking enabled as well as disabled. Do not copy another publisher's script or invent zone IDs. Ads may not fire in every browser or on every interaction.

## Provenance

The uploaded XAPK identifies itself as **Air Attack (Ads)**, package `dk.logisoft.airattack`, version `4.69`, version code `254`. See [APK_ANALYSIS.md](APK_ANALYSIS.md) for the static-inspection notes. Only use the original game's code/assets if you own them or have permission to reuse them.
