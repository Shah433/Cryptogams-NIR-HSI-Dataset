# Cryptogams-NIR-HSI-Dataset
This repository provides demonstration code for loading, visualising, and analysing the **Cryptogams Near-Infrared Hyperspectral Imaging (NIR-HSI) Dataset**. The dataset contains proximal NIR-HSI hypercubes acquired from naturally occurring cryptogamic communities, including **chlorolichen, cyanolichen, bryophyte (moss), and bark substrate** classes. The hypercubes were acquired using a **Specim FX17e pushbroom hyperspectral camera** covering the **900–1700 nm near-infrared spectral range with 224 spectral bands**. The dataset was collected and maintained by the **Waikato Instrumentation and Measurement Research (WAI2M), Hyperspectral Imaging Research Group, University of Waikato, New Zealand**.

Research Group Website: https://hsi.eng.waikato.ac.nz/homehsi/

The dataset was used in the conference paper:

**"Near-Infrared Hyperspectral Imaging and Deep Learning for Semantic Segmentation of Cryptogams With Sparse Annotations"**  
**Paper ID: 1571310702**  
Accepted for presentation at the **IEEE 12th International Conference on Smart Instrumentation, Measurement and Applications (ICSIMA 2026)**.

---

## Dataset Access

The complete dataset is available from the following repository:

**Dataset DOI:**  


The dataset file:

```
Cryptogams_NIR_HSI_Dataset.h5
```

should be downloaded separately before running the demonstration notebook.

---

## Dataset Structure

The dataset is provided as a single HDF5 (`.h5`) file containing hyperspectral cubes, semantic masks, and wavelength information.

```
Cryptogams_NIR_HSI_Dataset.h5

├── RAW_Cubes
│   └── Shape: (39, 370, 520, 224)
│
├── SNV_Cubes
│   └── Shape: (39, 370, 520, 224)
│
├── FinalMasks
│   └── Shape: (39, 370, 520)
│
└── wavelength
    └── Shape: (224,)
```

### Dataset Variables

| Variable | Description | Dimensions |
|---|---|---|
| `RAW_Cubes` | White- and dark-reference corrected hyperspectral cubes | `(39, 370, 520, 224)` |
| `SNV_Cubes` | SNV-normalised hyperspectral cubes | `(39, 370, 520, 224)` |
| `FinalMasks` | Pixel-level semantic segmentation masks | `(39, 370, 520)` |
| `wavelength` | Wavelength vector ( 900-1700 nm) | `(224,)` |

---

## Semantic Label Definition

The pixel-level semantic masks use the following label scheme:

| Label | Class |
|---|---|
| 0 | Background |
| 1 | Chlorolichen |
| 2 | Cyanolichen |
| 3 | Bryophyte |
| 4 | Bark |
| 255 | Unknown / Unlabelled (Ignore) |

The ignore label (`255`) represents specimen pixels that could not be confidently assigned during annotation and should be excluded from supervised learning loss calculations.

---

## Repository Contents

```
Cryptogams-NIR-HSI-Dataset/

├── Cryptogams_NIR_HSI_Dataset_Demo.ipynb
├── README.md
├── requirements.txt
└── LICENSE
```

---

## Installation

Install the required Python packages:

```bash
pip install -r requirements.txt
```

The notebook requires:

```
numpy
matplotlib
h5py
jupyter
```

---

## Running the Demonstration Notebook

The notebook demonstrates:

1. Loading the HDF5 dataset
2. Inspecting dataset structure
3. Visualising hyperspectral samples and semantic masks
4. Computing dataset statistics
5. Analysing class distribution

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```
Cryptogams_NIR_HSI_Dataset_Demo.ipynb
```

---

## Dataset Path Configuration

After downloading:

```
Cryptogams_NIR_HSI_Dataset.h5
```

update the dataset path in the notebook:

```python
# ============================================================
# Dataset Path
# ============================================================

# Update H5_PATH to the location where you downloaded
# 'Cryptogams_NIR_HSI_Dataset.h5' on your computer.

H5_PATH = r"/path/to/Cryptogams_NIR_HSI_Dataset.h5"
```

Replace the path with the actual location of the downloaded dataset.

Example (Windows):

```python
H5_PATH = r"C:\Users\YourName\Downloads\Cryptogams_NIR_HSI_Dataset.h5"
```

Example (Linux/Mac):

```python
H5_PATH = "/home/user/data/Cryptogams_NIR_HSI_Dataset.h5"
```

---

## Dataset Summary

- Number of hyperspectral images: **39**
- Spatial dimension: **370 × 520 pixels**
- Spectral bands: **224**
- Spectral range: **900–1700 nm**
- Annotated images: **29**
- Unannotated images: **10**

---

## Associated Publication

The dataset preparation, annotation strategy, and segmentation methodology are described in:

**Faisal, S. et al.**  
*"Near-Infrared Hyperspectral Imaging and Deep Learning for Semantic Segmentation of Cryptogams With Sparse Annotations."*  
IEEE 12th International Conference on Smart Instrumentation, Measurement and Applications (ICSIMA 2026).  
Paper ID: 1571310702.

---

## Citation

If you use this dataset in your research, please cite the dataset and associated publication.

### Dataset Citation

```

```

### Paper Citation

```
Faisal, S. et al.
Near-Infrared Hyperspectral Imaging and Deep Learning for Semantic Segmentation
of Cryptogams With Sparse Annotations.
IEEE ICSIMA 2026.
```

---

## License

This dataset and associated code are released under:

```

```
