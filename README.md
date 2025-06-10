
# Local Robustness Evaluation and Repair of Neural-Network–Based Intrusion Detection Systems via Adversarial Examples

## Introduction  
This repo contains code and data to reproduce our NeurIPS 2025 experiments on fine-tuning LSTM-based intrusion detection models for adversarial robustness.

## Run in Google Colab  
1. Open the notebook at  
   https://github.com/KeysGui-i/189G_final/blob/main/NIDS.ipynb  
2. Click “Open in Colab”  
3. Run the first cell (installs any missing packages), then execute the notebook top to bottom.

> **Note:** Executing all cells end-to-end in Colab (including full adversarial training, repair, and evaluations) can take **8–10 hours** on a free GPU runtime. You may wish to save intermediate model checkpoints or run only specific sections when iterating.

## (Optional) Local installation  
If you prefer to run locally, clone the repo and install dependencies:  
```bash
git clone https://github.com/KeysGui-i/189G_final.git
cd 189G_final
pip install jupyter numpy pandas tensorflow scikit-learn matplotlib
jupyter notebook NIDS.ipynb
```


## Data

`data/raw/*.txt` are straight from the NSL-KDD dataset (Tavallaee et al., 2009).  
They are ~23 MB total, well under GitHub’s 100 MB/file limit.  
Original source: <https://www.unb.ca/cic/datasets/nsl.html>

