# ccaim_card

Contact card and link page for [CCAiM](https://github.com/serbekun/CCAiM) — the cloud
classification model. Same terminal style as [serbekun.com](https://serbekun.com).

## What

A single-page project card. Model source, training log, validation results,
dataset stats, the hardware it was trained on, and links to the repo and
Hugging Face assets. No frameworks, no build step.

## Contents

- `index.html` — page markup (results, dataset, hardware, links)
- `style.css` — terminal theme (serbekun_card stylesheet + ccaim stat/spec blocks)
- `theme.js` — applies the saved theme before first paint, wires the toggle
- `404.html` / `404.css` — custom 404 page
- `favicon.svg` — cloud mark

## Usage

Open `index.html` in a browser. That's it.

## Hardware on the page

The hardware section is not decoration — it is the real training box:

- The home server, Arch Linux
- GPU NVIDIA Quadro P2200 — 5 GB GDDR5X (5120 MiB), Pascal (sm_61), 1280 CUDA cores, 75 W, driver 580.178.04, no tensor cores
- CPU Intel Core i7-7700K — 4 cores / 8 threads @ 4.2 (4.5) GHz, 8 MB cache, 91 W
- 16 GiB RAM, 256 GB NVMe + 2 x 1 TB HDD
- Python 3.14 + PyTorch 2.14 (cu126) + CUDA 12.6, `torch.cuda.is_available() = True`

The V0.0.5 / V0.0.6 metrics on the page were produced before the training host moved
to node3.

Numbers shown (50.34% / 42.95% / 35.57% / 27.52% val accuracy, macro-F1, 916 images)
come from the model card and dataset card on Hugging Face.

## Deploy

Static hosting. Drop the files on any server, CDN, or static host.
Cloudflare Pages works with zero config (`wrangler.jsonc` included).

## License

MIT
