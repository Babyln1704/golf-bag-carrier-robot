# Golf Bag Carrier Robot — Computer Vision Prototype

## Overview

The **Golf Bag Carrier Robot** project explores computer vision techniques that could help a golf bag carrier robot detect a person, analyse visual scenes, and generate software-level guidance decisions.

The project is inspired by the Stanford CS229 2018 report *Golf Bag Carrier Robot Computer Vision* by Akshay Gupta and Nicholas Gloria.

This repository contains two Jupyter notebooks demonstrating a baseline computer vision pipeline and an improved approach using person detection, temporal smoothing, and scene segmentation.

## Objectives

- Detect people in images and sampled video frames.
- Explore colour clustering and image segmentation.
- Investigate more stable person-following decisions across consecutive frames.
- Generate guidance states such as `FOLLOW`, `SEARCH`, `CAUTION`, and `STOP`.
- Compare a baseline demonstration with an improved software approach.

## Repository Contents

| File | Description |
|---|---|
| `01_Base_Paper_Reproduction_Demo.ipynb` | Demonstrates baseline object detection, K-Means colour clustering, and Felzenszwalb segmentation. |
| `02_Proposed_Improved_Method_Demo.ipynb` | Demonstrates person detection, temporal smoothing, scene segmentation, and rule-based guidance. |
| `README.md` | Project overview, setup instructions, methods, and limitations. |
| `requirements.txt` | Python package dependencies for running the notebooks. |
| `Golf_Bag_Carrier_Robot...` | Additional project files uploaded to the repository. |

The exact names of the additional project files are abbreviated in the repository listing shown during preparation.

## Technologies Used

- Python
- Jupyter Notebook
- PyTorch and TorchVision
- YOLOv8
- OpenCV
- NumPy and Pandas
- Scikit-learn
- Scikit-image
- Hugging Face Transformers
- SegFormer

## Notebook 1: Base Paper Reproduction-Inspired Demo

**File:** `01_Base_Paper_Reproduction_Demo.ipynb`

This notebook demonstrates:

- Pretrained SSD-MobileNetV3-Large object detection.
- K-Means colour clustering.
- Felzenszwalb image segmentation.
- Exporting processed images, CSV files, and summary outputs.

The notebook is a reproduction-inspired demonstration of selected computer vision techniques. It does not recreate the complete original terrain-classification CNN.

## Notebook 2: Proposed Improved Method Demo

**File:** `02_Proposed_Improved_Method_Demo.ipynb`

This notebook demonstrates:

- YOLOv8-based person detection.
- Temporal smoothing of detection results.
- Handling temporary person-detection loss.
- Generic scene segmentation using a pretrained SegFormer model.
- Rule-based guidance states, including `FOLLOW`, `SEARCH`, `CAUTION`, and `STOP`.
- Exporting images and structured results for analysis.

The guidance states are software-generated decisions. They are not verified physical robot-control commands.

## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/Babyln1704/golf-bag-carrier-robot.git
cd golf-bag-carrier-robot
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

On Linux or macOS:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

Some pretrained models may be downloaded automatically when the notebooks run for the first time. An internet connection may be required.

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open either notebook and execute its cells in order. Follow any dataset, video-input, or model-download instructions provided within the notebook.

## Results and Evaluation

The notebooks produce visual outputs and structured files for inspecting person detection, segmentation, and guidance behaviour.

Detection rates and processing times should be interpreted only in the context of their specific test runs. A frame detection rate is not equivalent to model accuracy.

Reliable evaluation of accuracy, precision, recall, and F1-score requires a labelled test dataset and comparison against ground-truth annotations.

## Limitations

- The project is a software-only computer vision prototype.
- Physical robot construction, motor control, and autonomous golf-course navigation have not been validated.
- Generic scene segmentation does not establish reliable detection of golf-course hazards.
- Person detection can be affected by distance, occlusion, lighting, and camera angle.
- Rule-based guidance states are experimental outputs rather than safety-certified decisions.
- Performance depends on the input data, hardware, pretrained models, and configuration.

## Future Work

- Integrate the software with a physical robot and conduct controlled safety tests.

## Reference

Gupta, Akshay, and Nicholas Gloria. *Golf Bag Carrier Robot Computer Vision*. Stanford CS229, 2018.

This project is inspired by the referenced work and uses its own implementation choices and pretrained models.

## Contributors

Baby L N & Shailaja P C

