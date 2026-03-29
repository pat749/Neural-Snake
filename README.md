# Neural Snake — Neuroevolution in the Browser

A self-contained Snake game where each snake is controlled by a neural network trained **live** with **population-based evolution** (no backprop). Switch between **feedforward**, **Elman RNN**, and **LSTM** brains, and between **genetic algorithm** (crossover + mutation) and **evolution strategy** (mutation around elites).

**Live demo:** after you enable Pages (below), the site is typically `https://<username>.github.io/<repo-name>/` (for example `https://pat749.github.io/Neural-Snake/`).

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

1. Push this project to the `main` branch of your GitHub repository.
2. **Required once per repo:** open **Settings → Pages**. Under **Build and deployment**, set **Source** to **GitHub Actions** (not “Deploy from a branch”). Until this is saved, `actions/configure-pages` fails with **“Get Pages site failed” / Not Found** because GitHub has not created a Pages site for the repository yet.
3. Go to **Actions**, open the failed **Deploy to GitHub Pages** run, and click **Re-run all jobs** (or push an empty commit). The workflow in `.github/workflows/pages.yml` uploads the repo root on every push to `main`.

### If the deploy job still fails

- Confirm **Settings → Pages → Source** is **GitHub Actions**.
- Confirm the workflow ran on **`main`** (branch name matches `on.push.branches` in `pages.yml`).
- For a **private** repository, check [GitHub Docs](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages) for extra permission requirements.

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
