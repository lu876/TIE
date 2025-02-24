# Mitigating Spurious Correlations in Zero-Shot Multimodal Models

## Installation

### Requirements
- open_clip_torch
- requirements (in requirements.txt)

### Installing
1. Install required packages: `pip install -r requirements.txt`
2. Install open_clip_torch: `pip install open_clip_torch`

## Dataset Preparation

1. **CelebA Dataset**
    - Download from: https://mmlab.ie.cuhk.edu.hk/projects/CelebA.html
    - Place in the directory above the repository root

2. **Waterbirds Dataset**
    - Download from: https://github.com/p-lambda/wilds
    - Place in the directory above the repository root

3. **ISIC Dataset**
    - Run the provided code snippet to download and extract
```
import os
import gdown
import zipfile

data_root = '..'  # Set your ROOT directory
os.makedirs(data_root, exist_ok=True)
output = 'isic.zip'
url = 'https://drive.google.com/uc?id=1Os34EapIAJM34DrwZMw2rRRJij3HAUDV'

if not os.path.exists(os.path.join(data_root, 'isic')):
    gdown.download(url, os.path.join(data_root, output), quiet=False)
    with zipfile.ZipFile(os.path.join(data_root, output), 'r') as zip_ref:
        zip_ref.extractall(data_root)
```

4. **COVID-19 Dataset**
    - Download from: https://github.com/ieee8023/covid-chestxray-dataset
    - Place in the directory above the repository root

## Reproducing Experiments

1. Activate your conda environment
2. Run `Table1-WB.ipynb` to reproduce TIE for Waterbirds
3. Run `Table2-CelebA` to reproduce TIE for CelebA  
4. Run `Table3-ISIC.ipynb` to reproduce TIE for ISIC
5. Run `Table3-Covid.ipynb` to reproduce TIE for COVID-19
