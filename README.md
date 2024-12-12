# Application of Data-driven Feature Tracking for Event Cameras in "Low Light Space Object Tracking"

This project is a continuation of the work presented in the paper: [Application of Data-driven Feature Tracking for Event Cameras](https://arxiv.org/pdf/2211.12826). The foundational code and pre-trained models have been taken from the original implementation accompanying the paper.

---

## Introduction

The project aims to explore the potential of data-driven feature tracking techniques for event cameras, with a specific focus on low-light conditions for space object tracking. We began by setting up the provided code and replicating the experiments described in the original work. 

### Setup and Replication
1. **Install Required Packages**: 
   - Follow the dependency requirements in the original repository to install all necessary Python packages. Make sure to use the appropriate Python version as recommended.
   - Example: `pip install -r requirements.txt`

2. **Directory Setup**:
   - Clone the original repository and create the necessary directory structure. Ensure that paths to `ec_subseq` and `eds_subseq` are correctly configured.

3. **Download the Original Data**:
   - Retrieve the datasets (both `ec_subseq` and `eds_subseq`) from the links provided in the paper's repository. These datasets include events, pose data, and other supplementary files for evaluation.

4. **Run the Pre-trained Models**:
   - Use the pre-trained models provided in the original repository to evaluate feature tracking on `ec_subseq` and `eds_subseq` datasets. 
   - Example:
     ```bash
     python evaluate_real.py --config-path configs/ --config-name eval_ec_subseq
     ```

![Placeholder for GIF showing model output on the original datasets]

---

## New Space Data Experimentation

### Data Preparation
In this work, we extended the evaluation by introducing a new type of dataset: **simulated space events data**. The dataset was generated using the following steps:
1. **AI Video Generator**: Real space images were transformed into dynamic sequences using an AI-based video generator.
2. **Event Data Extraction**: The generated video was processed using the **V2E converter**, which extracts events from video frames and outputs them in the required format.

The event data was structured following the directory setup of `ec_subseq`, including `event_stacks`, `time_surfaces`, and pose files.

### Challenges and Future Work
Initial evaluations of the model on the new space data did not yield satisfactory results. The primary reason is that the pre-trained networks are not optimized for this new type of simulated data. To achieve better performance, the model needs to be re-trained or fine-tuned on this specific dataset.

Future work involves:
- Training the model on the simulated space data to adapt it to these unique conditions.
- Exploring improvements to the data simulation pipeline for better alignment with real-world scenarios.
- Investigating novel feature extraction techniques to enhance tracking performance in low-light and noisy conditions.

---

This repository serves as an exploration of applying state-of-the-art event camera tracking methods to the challenging domain of space object tracking. We welcome further contributions and discussions to advance this work.
