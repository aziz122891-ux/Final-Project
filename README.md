# Scene Type and the Detectability of Diffusion-Generated Satellite Imagery

This repository contains the code used for my MSc Data Science dissertation at the University of Bristol.

The project investigates whether the detectability of diffusion-generated satellite images changes depending on the visual scene type. The main experiments use the RSFAKE-1M dataset, with an additional validation experiment using EuroSAT.

## Files

### `RSFAKE.ipynb`

This is the main notebook used for the RSFAKE-1M experiments.

It includes:

- Loading real and diffusion-generated satellite images
- Loading RemoteCLIP scene labels
- Grouping images into five scene types:
  - Water
  - Agriculture
  - Urban
  - Transport
  - Industrial
- Balanced sampling across scene types
- Train/test splitting by source location
- ResNet-50 training and evaluation
- Bootstrap confidence intervals
- Per-scene error analysis
- Leave-one-generator-out evaluation
- ViT-B/16 comparison
- FFT frequency analysis
- Grad-CAM visualisation

A fixed random seed of 42 is used for reproducibility.

### `EuroSAT.ipynb`

This notebook contains the external validation experiment using EuroSAT.

The images are grouped into four broader scene categories:

- Water
- Agriculture
- Vegetation
- Built

The notebook downloads the required EuroSAT real and generated datasets automatically.

It then performs:

- Balanced sampling
- Train/test splitting
- ResNet-50 training
- Overall and per-scene evaluation
- Bootstrap confidence intervals

## RSFAKE Data

The RSFAKE notebook requires three additional data files because they are too large to store directly in this GitHub repository.

Required files:

- `real_images_final.zip`
- `fake_new_backup.zip`
- `remoteclip_labels_10gen.csv`

The files can be accessed from the following Google Drive folder:

https://drive.google.com/drive/folders/1VIkwMXMMkT4VDiZh9BWZ8FBk6a0jdAtC?usp=sharing

To run `RSFAKE.ipynb`:

1. Download the three files from the Google Drive link, or add the shared folder to your own Google Drive.
2. Open `RSFAKE.ipynb` in Google Colab.
3. Mount Google Drive when requested.
4. Change the `DRIVE` variable in the notebook so that it points to the folder containing the three data files.

For example, if the shared folder is added to My Drive as `Final-Project-Data`:

```python
DRIVE = '/content/drive/MyDrive/Final-Project-Data'
