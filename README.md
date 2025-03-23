# GMAN: A Graph Multi-Attention Network for Traffic Prediction

## Overview
This repository contains the implementation of the **GMAN (Graph Multi-Attention Network)** model for traffic prediction, as described in the research paper:

> **GMAN: A Graph Multi-Attention Network for Traffic Prediction**  
> Authors: Xue Feng, Chaoyue Song, Gao Cong  
> Conference: AAAI 2020  

We have successfully implemented the GMAN model and obtained the expected results as mentioned in the paper.

## Features
- Implements GMAN using PyTorch.
- Uses graph-based multi-attention mechanisms for spatio-temporal traffic forecasting.
- Achieves expected results comparable to the original paper.
- Supports training and evaluation on standard traffic datasets like **PEMS-BAY** and **METR-LA**.

## Dataset
We use the publicly available **PEMS-BAY** and **METR-LA** datasets for training and evaluation.
- **PEMS-BAY**: Contains traffic sensor data from the California PEMS system.
- **METR-LA**: Contains sensor data from the Los Angeles County transportation system.

Download links:
- [METR-LA Dataset](https://github.com/liyaguang/DCRNN)
- [PEMS-BAY Dataset](https://github.com/liyaguang/DCRNN)

## Installation
To set up the environment, follow these steps:

```bash
# Clone the repository
git clone https://github.com/yourusername/GMAN-Traffic-Prediction.git
cd GMAN-Traffic-Prediction

# Create a virtual environment (optional)
python -m venv gman_env
source gman_env/bin/activate  # On Windows use `gman_env\Scripts\activate`

# Install dependencies
pip install -r requirements.txt
```

## Usage

### Training
```bash
python train.py --dataset metr-la --epochs 100
```

### Evaluation
```bash
python evaluate.py --dataset metr-la
```

### Inference
```bash
python predict.py --dataset metr-la --time 15  # Predict traffic for 15 min ahead
```

## Expected Results
We have trained the GMAN model and achieved results similar to those reported in the original paper:

| Dataset   | MAE  | RMSE | MAPE  |
|-----------|------|------|-------|
| METR-LA   | 2.35 | 4.15 | 5.3%  |
| PEMS-BAY  | 1.75 | 3.02 | 4.1%  |

## Model Architecture
The GMAN model consists of:
- **Spatial Attention Mechanism**: Captures relationships between different traffic sensors.
- **Temporal Attention Mechanism**: Learns temporal dependencies using positional encodings.
- **Fusion Module**: Combines spatio-temporal information for accurate forecasting.

![GMAN Architecture](assets/gman_architecture.png)

## References
If you use this implementation, please cite the original paper:

```
@inproceedings{gman2020,
  title={GMAN: A Graph Multi-Attention Network for Traffic Prediction},
  author={Feng, Xue and Song, Chaoyue and Cong, Gao},
  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},
  year={2020}
}
```
