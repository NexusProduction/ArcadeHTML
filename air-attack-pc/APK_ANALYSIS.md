# Static analysis — Air Attack (Ads) XAPK

## Verified package metadata

- Uploaded file: `air-attack-ad.xapk`
- Name in XAPK manifest: `Air Attack (Ads)`
- Package ID: `dk.logisoft.airattack`
- Version name: `4.69`
- Version code: `254`
- Minimum SDK: `32`
- Target SDK: `36`
- Split packages: base APK, `config.en.apk`, `config.hdpi.apk`, and `config.arm64_v8a.apk`
- Base APK size: approximately 18.1 MB
- The base APK includes three DEX files with game classes under `dk.logisoft.airattack`

## Class-name evidence

Strings visible in the DEX files include:

- `AirAttackActivity`, `AirAttackView`, `AirAttackApplication`
- `game.Game`, `game.GameStateController`, `game.Game$Difficulty`, `game.XorShiftRandom`
- `ui.GameUiController`
- `objects.weapons.RocketLauncher` and `objects.weapons.RocketLauncher$RocketUpgrade`

These names suggest a native game/view loop, game-state controller, difficulty profiles, deterministic/pseudorandom generation, UI controller, and a rocket upgrade system.

## Resource-name evidence

The base APK's Android drawable and raw-resource tables include named resources for aircraft, bullets, bombs, terrain, buildings, vegetation, soldiers/paratroopers, supply planes/crates and sound effects. Examples include `bomberplane.png`, `supplyplane.png`, `clusterbomb.png`, `rocketlauncher.png`, `groundtexture.png`, `soldier*.png`, and multiple `res/raw/*.ogg` files.

These are static-inspection observations. This summary does not redistribute the resources.

## Porting conclusion

The XAPK is the correct game package. It is compiled Android output, not the original source project. Rebuilding for PC/browser requires reimplementing rendering, input, simulation, enemy behaviors, collisions, weapons, ground interactions, progression/save systems and audio in browser-compatible code or an engine.

The included web game independently recreates broad arcade flight-combat ideas using original Canvas drawing. It does **not** patch the APK, strip its advertising, reuse its assets/audio, or claim an exact match. This is not a full decompilation or a dynamic runtime trace. Use proprietary source/assets only when you have the rights or permission.
