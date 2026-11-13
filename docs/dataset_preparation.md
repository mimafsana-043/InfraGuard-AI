# Dataset Preparation — InfraGuard AI

## 1. Dataset Information

**Dataset:** Cracks in the Foundation (CiF)  
**Source:** https://huggingface.co/datasets/ibm-research/cif-dataset

InfraGuard AI uses infrastructure inspection images and instance-level annotations to develop a multi-class defect segmentation system.

## 2. Defect Categories

The project targets six defect categories:

1. Algae
2. Crack
3. Net-Crack
4. Crack with Precipitation
5. Rust
6. Spalling

## 3. Dataset Preparation

For initial development, the project targets the following subsets:

| Split | Target Images |
|---|---:|
| Training | 500 |
| Validation | 100 |
| Testing | 100 |
| Total | 700 |

The subsets are sampled separately from the official CiF training, validation, and testing configurations.

## 4. Preprocessing Pipeline

The dataset preparation pipeline includes:

- Streaming dataset access using Hugging Face Datasets
- Reproducible bounded-buffer shuffling with seed 42
- RGB image conversion
- Image and annotation extraction
- COCO-compatible JSON generation
- Bounding-box and polygon validation
- Dataset integrity checks

## 5. Reproducibility

The dataset preparation code is maintained in:

`notebooks/02_dataset_preparation.ipynb`

The bounded-buffer sampling method provides an approximately randomized subset rather than an exactly uniform sample of each entire split.

## 6. Data Availability

The original dataset images are not redistributed through this GitHub repository.

Users should obtain the dataset from the official source and follow its licensing conditions.

## 7. Project Status

Milestone 02: Dataset preparation and validation.

The prepared subsets are intended for initial pipeline development. Larger-scale evaluation will be required for research conclusions.
