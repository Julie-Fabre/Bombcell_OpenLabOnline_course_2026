# Bombcell workshop – Open Lab Online, October 2026

Material for the Bombcell session of the Open Lab Online series *Neural Data Analysis with Open-Source Tools*.

**Tuesday 20 October 2026, 15:00–17:00 CEST / 09:00–11:00 EDT**

In this hands-on session we'll use [Bombcell](https://github.com/Julie-Fabre/bombcell) to curate spike-sorted Neuropixels data:

1. Overview of quality control and quality metrics 
2. **Run Bombcell** on a Kilosort output folder
3. **Look at the output files**: quality metrics, unit labels, and what Phy sees
4. **Look at units in the GUI**: why is each unit classified as good, multi-unit (MUA), noise or non-somatic?
5. **Fine-tune the classification**: thresholds are a choice, not a truth
6. **Quality metrics vs. stimulus responses**: what do we lose by curating?

## Data

One session from the [chronic Neuropixels 2.0 dataset](https://doi.org/10.5522/04/24411841.v2)
(Lebedeva, Okun, Krumin & Carandini; [Steinmetz et al., *Science* 2021](https://doi.org/10.1126/science.abf4588); CC BY-NC-SA 4.0):
mouse visual cortex, spike-sorted with pyKilosort, while the mouse viewed 112 natural images, 5 times each.

The notebook downloads it for you (`AL031_2019-12-13_noRawData.tar`, ~1.7 GB).

## Setup

Choose **one** of the two options below, and please do it **before the workshop**.

### Option A – Google Colab (no installation)

You only need a Google account and a web browser.

1. Open the notebook in Colab:
   [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Julie-Fabre/Bombcell_OpenLabOnline_course_2026/blob/main/notebooks/bombcell_workshop.ipynb)
2. Click **File → Save a copy in Drive** so you can edit and keep your own version.
3. Run the first three code cells (click a cell, then Shift+Enter). They install Bombcell and download the dataset, which takes a few minutes.
   The third cell should end by printing `kilosort folder: ...`. If it does, you're ready.

Colab resets after being idle for a while and deletes downloaded files, so on the day you may need to run these three cells again, including the download.

### Option B – Run locally (recommended if you want to use Bombcell on your own data afterwards)

The setup is the same as for Monday's SpikeInterface session.

1. [Install uv](https://docs.astral.sh/uv/getting-started/installation/), if you haven't already.
2. In a terminal, clone this repository and go to its `notebooks` folder:

   ```shell
   git clone https://github.com/Julie-Fabre/Bombcell_OpenLabOnline_course_2026.git
   cd Bombcell_OpenLabOnline_course_2026/notebooks/
   ```

3. Open Jupyter Lab (uv installs Bombcell and everything else it needs the first time):

   ```shell
   uv run jupyter lab
   ```

   Or, if you prefer VS Code:

   ```shell
   uv run code .
   ```

4. Open `bombcell_workshop.ipynb` and run the first three code cells. The dataset is downloaded into a `data/` folder next to `notebooks/`.
   The third cell should end by printing `kilosort folder: ...`. If it does, you're ready.

If you'd rather not use uv: create an environment with Python 3.11–3.13 and run `pip install bombcell==0.92 jupyterlab ipywidgets`.

## Prerequisites

Basic Python and Jupyter. Attending Monday's SpikeInterface session helps but isn't required.

## Troubleshooting

- **The download fails or is very slow:** download `AL031_2019-12-13_noRawData.tar` by hand from the [dataset page](https://doi.org/10.5522/04/24411841.v2), extract it into the `data/` folder (Option B) or upload it to Colab (Option A), then re-run the cell.
- **The GUI doesn't appear in Colab:** make sure you ran the cell above it that enables custom widgets, then re-run the GUI cell.
- Anything else: ask in the chat during the workshop, or open an issue on the [Bombcell repository](https://github.com/Julie-Fabre/bombcell/issues).

## Links

- Bombcell: https://github.com/Julie-Fabre/bombcell
- Bombcell wiki (how to read the summary plots, parameters, FAQ): https://github.com/Julie-Fabre/bombcell/wiki
