# Neural Snake — Neuroevolution in the Browser

A self-contained Snake game where each snake is controlled by a neural network trained **live** with **population-based evolution** (no backprop). Switch between **feedforward**, **Elman RNN**, and **LSTM** brains, and between **genetic algorithm** (crossover + mutation) and **evolution strategy** (mutation around elites).

**Live demo:** enable GitHub Pages on this repo (see below) — site URL will be `https://pat749.github.io/Neural-Snake/`.

## Features

- **Architectures:** FFNN (24→16→4), Elman RNN (recurrent hidden state), LSTM (gated memory).
- **Training:** GA with crossover and Gaussian mutation, or (μ,λ) ES with elite parents and mutation-only offspring.
- **Sensors:** Raycasts (wall / body) in four directions, food bearing, heading, and auxiliary cues — all normalized (no raw grid memorization).
- **Fitness:** Strong reward for food (`score²`) plus shaping for survival and approaching food.
- **UI:** Generation stats, best/mean fitness chart, weight heatmap for the current champion, speed / turbo training, save & load champion JSON, human play mode to compare yourself to the best AI.

## Run locally

Open `index.html` in a modern browser, or serve the folder:

```bash
cd neural-snake
python3 -m http.server 8080
# visit http://localhost:8080
```

## Deploy on GitHub Pages

1. Create a repo (e.g. `neural-snake`) and push this project to the `main` branch.
2. In the repository: **Settings → Pages → Build and deployment → Source:** GitHub Actions.
3. The included workflow (`.github/workflows/pages.yml`) deploys the repository root on every push to `main`.

## Project layout

```
neural-snake/
├── index.html          # Single-file app (HTML + CSS + JS)
├── README.md
└── .github/workflows/
    └── pages.yml       # GitHub Pages deployment
```

## License

MIT — use freely for learning and portfolios.
