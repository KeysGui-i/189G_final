
# Rapid Local Repair for Adversarially Robust LSTM Intrusion Detection

## Team Member
Jennifer Liu

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

## Selective Execution Overview

| Section Header                                    | Purpose                                                   | Approx. Runtime   |
| ------------------------------------------------- | --------------------------------------------------------- | ----------------- |
| 1. Environment Setup                              | install/import libraries                                  | < 1 min           |
| 2. Load & Inspect Data                            | read NSL-KDD CSVs & quick EDA                             | < 1 min           |
| 4. Data Preprocessing                             | feature extraction & train/test split                     | < 1 min           |
| 5. Model Architecture & Training                  | define LSTM & train clean baseline                        | ~ 8 min          |
| 6. Baseline Performance                           | evaluate baseline on test set                             | < 1 min           |
| 7. Adversarial Attack Evaluation                  | test baseline under FGSM (ε=0.01/0.02/0.05/0.10)           | ~ 2–3 min         |
| 8. Full Adversarial Retraining (skip to save time) | FGSM retraining (very heavy)                              | ~ 8 hrs total     |
| 9. Local Repair                                   | fine-tune & summarize repair metrics          | ~ 30 min        |
| 10. Robustness Plots                              | flip-ε routines & plot per-sample/aggregate robustness curves | ~ 15 min         |

### Viewing Local Repair Results Only

To jump straight to the local‐repair metrics (≈ 30 min), execute these sections in `NIDS.ipynb` in order:

1. **Environment Setup**  
2. **Load & Inspect Data**  
3. **Data Preprocessing**  
4. **Model Architecture & Training** (clean baseline)  
5. **Adversarial Attack Evaluation** (baseline FGSM evaluation)  
6. **Local Repair** (fine-tune final layers & summary)

> *Optional:* **Robustness Plots** (flip-ε analysis & aggregated curves)  

## Data

`data/raw/*.txt` are straight from the NSL-KDD dataset (Tavallaee et al., 2009).  
They are ~23 MB total, well under GitHub’s 100 MB/file limit.  
Original source: <https://www.unb.ca/cic/datasets/nsl.html>

## Acknowledgements

Model architecture and data preprocessing adapted from the Kaggle notebook “[lionsai/lstm-nsl-kdd-2022](https://www.kaggle.com/code/lionsai/lstm-nsl-kdd-2022)”.

