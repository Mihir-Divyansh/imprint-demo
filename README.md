# Imprint: static demo replay (GitHub Pages)

A fixed replay of the live demo (`python -m imprint demo`): every audio file, plot and the system diagram were
produced by real demo runs and saved by `scripts/capture_static_demo.py`. Nothing runs in the browser.

Contents:
- `index.html`: the page (plain HTML/CSS/JS, no build step).
- `data/manifest.js`: what each run contains (versions, measurement table, diagram, steps), loaded by the page.
- `data/<voice>/`: the recording, the guide (when published), every version, step audio and plots.

Voices: CMU ARCTIC speakers (free licence, attribution in the footer) and the author's own demo session, published
with the author's permission (the guide in that session is the author's voice too).

## Preview locally

Open `index.html` in a browser (it works from `file://`), or `python3 -m http.server -d pages 8000`.

## Publish on GitHub Pages

1. Create a public repository (e.g. `imprint-demo`) and copy the *contents* of this folder to its root.
2. Commit and push. In the repository: Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/`.
3. The page appears at `https://<username>.github.io/imprint-demo/`.

## Re-capture

With the demo running: `PYTHONPATH=src:scripts .venv/bin/python scripts/capture_static_demo.py` (CMU voices, about
5 min each with fine-tuning), then `... capture_static_demo.py session <demo session dir> <id> "<description>"` for a
saved session.
