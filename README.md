# Neural Snake — Research Lab (Evolution + RL)

A self-contained Snake game in one `index.html`: **neuroevolution** (GA, ES, adaptive ES) and **reinforcement learning** (REINFORCE, A2C, DQN, PPO-style) in the browser. Organic snake rendering, human solo play, and a split-screen **Human vs champion** mode.

**Live demo (after Pages is enabled):** [https://pat749.github.io/Neural-Snake/](https://pat749.github.io/Neural-Snake/)

## Features

- **Evolution:** Genetic algorithm, evolution strategy, **adaptive ES** (1/5-style σ).
- **RL:** REINFORCE + baseline, **Advantage Actor–Critic (A2C)**, **DQN** (replay + target net), **PPO-style** clipped updates.
- **Architectures (evolution):** FFNN (24→16→4), Elman RNN, LSTM. **RL** uses a shared MLP **24→32→4**.
- **Sensors:** Raycasts to wall/body, food bearing, heading — normalized (no raw grid).
- **UI:** Training curve, weight view, turbo / speed, save/load (genome or RL weights), play modes.

## Run locally

Open `index.html` in a browser, or:

```bash
cd neural-snake
python3 -m http.server 8080
# http://localhost:8080
```

## Deploy on GitHub Pages

1. Push to the `main` branch.
2. **Once per repo:** **Settings → Pages → Build and deployment → Source:** **GitHub Actions**. If this is not set, `actions/configure-pages` can fail with **Get Pages site failed / Not Found**.
3. In **Actions**, confirm **Deploy to GitHub Pages** succeeds (or re-run the workflow).

### Deploy still failing?

- **Pages → Source** must be **GitHub Actions**.
- Workflow must run on **`main`** (see `.github/workflows/pages.yml`).
- Private repos: see [GitHub Pages + Actions](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages).

## Project layout

```
├── index.html
├── README.md
└── .github/workflows/pages.yml
```

## License

MIT — use freely for learning and portfolios.
