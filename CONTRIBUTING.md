# Contributing to Aether

Thanks for helping out! This is a small, single-file project, so contributing is easy.

## Getting set up
```bash
git clone https://github.com/<your-username>/aether-gesture-music.git
cd aether-gesture-music
python3 -m http.server 8000
```
Open http://localhost:8000 and edit `index.html`. Refresh the page to see changes.

## Making a change
1. Fork the repo and create a branch: `git checkout -b feature/my-idea`
2. Make your changes and test them with a real camera and in mouse mode.
3. Commit with a clear message: `git commit -m "Add minor blues scale option"`
4. Push and open a Pull Request describing what you changed and why.

## Good first ideas
- Add more scales (major, blues, Dorian) with a selector
- Add new gestures (chord changes, volume, reverb amount)
- Improve gesture detection thresholds
- Add loop recording or MIDI output
- Bundle MediaPipe files for offline use

## Guidelines
- Keep it dependency-free and runnable from a static server.
- Keep the mouse fallback working.
- Test in Chrome or Edge, and mention your browser and OS in the PR.

## Reporting bugs
Open an issue with: what you did, what you expected, what happened, your browser and OS, and any console errors (press F12 → Console).
