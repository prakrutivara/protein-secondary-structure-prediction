# Protein Secondary Structure Prediction

A deep learning project for predicting protein secondary structure using **ESM-2** protein language model embeddings and a **BiLSTM** classifier.

## Overview

Protein secondary structure prediction assigns each amino acid to one of three structural classes:

- **H** — Alpha helix
- **E** — Beta strand
- **C** — Coil

This project uses the pretrained **ESM-2 (`facebook/esm2_t12_35M_UR50D`)** model to obtain contextual protein representations, followed by a BiLSTM-based sequence classifier for Q3 secondary structure prediction.

## Model Architecture

```text
Protein Sequence
       ↓
      ESM-2
       ↓
     BiLSTM
       ↓
Linear Classifier
       ↓
Q3 Secondary Structure
   (H / E / C)
```

ESM-2 provides contextual representations for each amino acid, while the BiLSTM captures sequential dependencies along the protein sequence.

## Dataset

The project uses the **NetSurfP-2.0** dataset:

- Training: Train_HHblits
- Validation: CB513
- Test: TS115

The HHblits-derived input data is used for sequence and secondary-structure labels.

## Evaluation

The trained model is evaluated on the independent CB513 and TS115 benchmark
