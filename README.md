# 🎶 Aether — Hand Gesture Music

Play a synth and a drum beat with nothing but your hands. Aether runs entirely in your browser using your webcam, [MediaPipe Hands](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker) for hand tracking, and the Web Audio API for sound. No install, no build step, no backend.

## Features
- Two-hand control: one hand plays the melody, the other drives the rhythm
- Notes are locked to an A minor pentatonic scale, so it always sounds musical
- Live synth with filter control, drone pad and delay effect
- Synthesized kick and hi-hat beat with adjustable tempo
- Mouse mode fallback when no camera is available
- Single `index.html` file, no dependencies to install

## Gestures

| Hand | Gesture | Effect |
|------|---------|--------|
| Melody (right half of screen) | Move left / right | Choose the note |
| Melody | Move up / down | Filter brightness (higher = brighter) |
| Melody | Pinch thumb + index finger | Play the note; release to fade out |
| Rhythm (left half of screen) | Open palm | Start the beat |
| Rhythm | Fist | Stop the beat |
| Rhythm | Raise / lower hand | Tempo, 60 to 160 BPM |

The camera view is mirrored, so your right hand appears on the right.

## Quick start

Camera access only works on `localhost` or HTTPS, so run it through a local server rather than double-clicking the file.

```bash
git clone https://github.com/<your-username>/aether-gesture-music.git
cd aether-gesture-music
python3 -m http.server 8000
```

Open **http://localhost:8000** in Chrome or Edge, click **Start**, and allow camera access.

Alternative: `npx serve` or the VS Code **Live Server** extension.

## Deploy with GitHub Pages
1. Push the project to GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then Save.
4. After about a minute the app is live at `https://<your-username>.github.io/aether-gesture-music/`.

## Tips
- Use a well-lit room and keep both hands in view of the camera.
- Click **Start** before anything else; browsers block audio until you interact with the page.
- The first load needs internet because the hand-tracking model loads from the jsDelivr CDN.
- Works best in Chrome and Edge. Safari and Firefox may behave differently.

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Camera doesn't start | Use `localhost` or HTTPS, and allow camera in the browser and in your OS privacy settings |
| "Tracker unavailable" message | Check your internet connection or disable blockers for cdn.jsdelivr.net; mouse mode takes over |
| No sound | Click Start first, check your volume, and make sure the tab isn't muted |
| Notes feel jumpy | Improve lighting and move more slowly |
| Beat starts or stops by accident | Hold the rhythm hand fully open or fully closed |

## How it works
1. `getUserMedia` streams webcam video.
2. MediaPipe Hands returns 21 landmarks per hand each frame.
3. Hand position and finger distances (pinch, fist) are converted into note, filter, gate and tempo values.
4. Web Audio oscillators, a filter, and a delay produce the sound; the beat is scheduled with simple timers.

## Roadmap
- [ ] Selectable scales and instruments
- [ ] Chord and key-change gestures
- [ ] Loop recording
- [ ] MIDI output
- [ ] Offline mode with bundled MediaPipe files

## Contributing
Ideas and pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

## License
[MIT](LICENSE)
