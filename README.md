# CinePilot

**CinePilot** is the product umbrella for **natural-language camera control** on **single 3D assets** (e.g. 3D Gaussian Splatting): intent → camera path → novel-view frames → optional I2V → MP4.

This repository is **independent** from [MelodyCanvas](https://github.com/melodic-lab/MelodyCanvas) (music-driven pipeline). MelodyCanvas may consume similar ideas, but **CinePilot** owns the SceneCam-style roadmap and releases here.

## Repository layout

| Path | Role |
|------|------|
| **`lens-agent/`** | Git submodule → [`melodic-lab/lens-agent`](https://github.com/melodic-lab/lens-agent). Core library: schemas, planner, adapters, `scenecam` CLI. |

Future sibling folders (e.g. `web/`, `workers/`, `apps/`) can be added under this monorepo **without** coupling to MelodyCanvas.

## Clone (with submodule)

```bash
git clone --recursive https://github.com/melodic-lab/CinePilot.git
cd CinePilot
```

If you already cloned without submodules:

```bash
git submodule update --init --recursive
```

## Develop inside `lens-agent`

```bash
cd lens-agent
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -e .
scenecam --text "slow dolly in, 10 seconds" --work-dir ../runs/demo1
```

## License

Apache-2.0 for content in this repo root; submodule `lens-agent` follows its own `LICENSE` if present or inherits project policy.
