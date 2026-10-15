# SKCHESSHUB – website

Static, mobile-responsive site (no build step). Deploys to Vercel as-is.

## Features
- Pixel-matched layout of the supplied design (header, hero, services, stats band, footer)
- **Play with AI** – Stockfish (Web Worker, 5 strength levels). Falls back to a built-in
  minimax engine if the Stockfish script can't be loaded.
- **Multiplayer** – peer-to-peer over WebRTC (PeerJS). Create a room, share the 5-letter
  code or invite link, play. No server needed.
- Pass & Play, **New Game**, **Reset Board**, move history navigation (⏮ ◀ ▶ ⏭), flip board,
  resign, clocks, promotion picker, drag-and-drop + tap-to-move, board themes, sound.
- **Solve Positions** – mate-in-one puzzles.
- Effects: scroll reveals, animated counters, hero parallax, floating king, golden dust,
  3D card tilt, button ripple, confetti on win. Respects `prefers-reduced-motion`.

## Deploy on Vercel
1. `npm i -g vercel` then run `vercel` in this folder (framework: **Other**, no build command,
   output directory: `.`), **or** push to GitHub and import the repo in Vercel.
2. Done – `vercel.json` already sets clean URLs and cache/security headers.

## Local preview
`npx serve .`  (or any static server). Open the page over http(s), not file://,
so the Stockfish worker can load.

## Self-hosting Stockfish (optional)
Put a copy of `stockfish.js` (v10 asm.js build) at `js/stockfish.js`; it is used automatically
if the CDN copies are blocked.

## Notes
- Libraries load from CDNs: chess.js (cdnjs), PeerJS (unpkg), piece images (jsDelivr), Google Fonts.
- Multiplayer uses PeerJS's free public broker; for production consider your own PeerServer.
- Login / Sign Up is a front-end demo form – connect your own auth backend.
