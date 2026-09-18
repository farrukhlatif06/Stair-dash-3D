# Stair Dash 3D

A polished original HTML5/Three.js stair-building racing game inspired by the supplied gameplay references. It uses procedural geometry and original UI/characters; it does not copy proprietary source code or assets.

## Run
```bash
npm install
npm run dev
```
Then open the Vite URL. For production:
```bash
npm run build
npm run preview
```

## Controls
- Desktop: A/D or Left/Right arrows to steer.
- Mouse/touch: drag horizontally to steer.
- Space: pause/resume.
- Pause, settings, level select and garage are available from the UI.

## Architecture
- `src/Game.js` — central game loop, state transitions, camera, track, race logic.
- `src/Entities.js` — procedural characters, planks, palms.
- `src/LevelManager.js` — deterministic 20-level generator.
- `src/UIManager.js` — responsive menus/HUD/result screens.
- `src/SaveManager.js` — resilient localStorage persistence.
- `src/InputManager.js` — keyboard, mouse and touch/pointer input.
- `src/AudioManager.js` — Web Audio procedural feedback sounds.

## Save system
Uses `stairRaceSave` in localStorage with coins, level unlocks, skins, settings, wins and completed levels. Corrupt JSON falls back to defaults.

## Levels
20 deterministic levels are generated from a level-specific seed. Later levels vary gap locations, platform offsets, plank density, obstacles and rival count.

## Debug mode
Append `?debug=true` to the game URL to display state, level, player position/planks and rival progress.

## Notes
The game is intentionally asset-light and procedural so it can be run without copyrighted external textures/models. Three.js is the only runtime package dependency.
