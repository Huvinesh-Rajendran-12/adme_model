# Multitask Deep Neural Network (MT-DNN) for ADME Property Prediction

This repository contains a PyTorch implementation of a multitask deep neural network (MT-DNN) model designed to predict multiple ADME (Absorption, Distribution, Metabolism, Excretion) properties of chemical compounds simultaneously from their SMILES representations.

## Table of Contents

- Introduction
- Model Architecture
- Dataset
- Installation
- Usage
- Training
- Evaluation
- Results (Optional)
- Contributing
- License

## Introduction

ADME properties are crucial for understanding a drug's behavior in the body and are essential in drug discovery and development. This project leverages machine learning, specifically a multitask deep neural network, to predict six ADME endpoints:

* **Absorption:**
    * Solubility
* **Distribution:**
    * Human Plasma Protein Binding (hPPB)
    * Rat Plasma Protein Binding (rPPB)
* **Metabolism:**
    * Human Liver Microsomes (HLM)
    * Rat Liver Microsomes (RLM)
* **Excretion/Transport:**
    * MDR1-MDCK ER (Multidrug Resistance Protein 1 Efflux Ratio)

## Model Architecture

The MT-DNN model consists of the following components:

* **SMILES Encoding:** Input SMILES strings are encoded into integer sequences.
* **Embedding Layer:** Learns a dense representation for each character in the SMILES vocabulary.
* **Shared LSTM Layers:** Two LSTM layers capture sequential dependencies in the SMILES strings to learn a shared representation of the molecule.
* **Task-Specific Heads:**  Six linear layers, each responsible for predicting one of the ADME endpoints.

## Dataset

* **Simulated ADME Data:** The project includes a script for generating synthetic ADME data with SMILES representations and corresponding ADME values.
* **Real-World Data:**  You can replace the simulated data with real-world datasets like Tox21, PubChem, or custom datasets from pharmaceutical companies.

## Installation

1. **Clone the repository:** `git clone [repository url]`
2. **Install dependencies:** `pip install -r requirements.txt` 

## Usage

1. **Data Preparation:**
   * Use `prepare_data.py` to preprocess and split your dataset into training and validation sets.
2. **Model Training:**
   * Run `train.py` to train the MT-DNN model. Adjust hyperparameters and training options as needed.
3. **Evaluation:**
   * Use `evaluate.py` to evaluate the trained model on the test set and compute metrics like MSE and R^2.

## Training

Refer to the comments in the `train.py` script for detailed instructions on training the model.

## Evaluation

Refer to the comments in the `evaluate.py` script for instructions on evaluating the model.

## Results (Optional)

Add a section to summarize your findings, including:

* Model performance on the test set (e.g., MSE, R^2 for each task).
* Any insights gained from feature importance analysis or model interpretation.
* Comparison with other baseline models (if applicable).

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests.

## License

This project is licensed under the [LICENSE NAME] License.
