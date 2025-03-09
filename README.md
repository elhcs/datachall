
# ECG Heartbeat Classification RAMP Challenge

## Build Status

(Anas i was unable to add the badge from the template if someone knows please add it )

## Introduction

This challenge focuses on **ECG heartbeat classification** using the **MIT-BIH Arrhythmia Database**. The goal is to categorize each heartbeat into one of the classes defined by the **Association for the Advancement of Medical Instrumentation (AAMI)**.

### Why does it matter?

Accurate classification of ECG heartbeats is crucial for **early detection of arrhythmias**, assisting in **diagnosis and treatment of heart conditions**. Automated classification can enhance **efficiency in clinical practice** and support **real-time monitoring systems**.

## Getting Started

### Install

To run a submission and the notebook, install the dependencies listed in `requirements.txt` using:

```sh
pip install -U -r requirements.txt
```

If you are using `conda`, you can use `environment.yml` to set up the environment.

## Challenge Description

### Data Preprocessing

The first step is to **extract individual heartbeats** from the raw ECG recordings using a **temporal window around the R-peak**. The annotations from the MIT-BIH database are **mapped to the five main AAMI classes**:

- **N**: Normal
- **S**: Supraventricular
- **V**: Ventricular
- **F**: Fusion
- **Q**: Unclassifiable

The preprocessed data, including heartbeat segments, AAMI labels, and record identifiers, are stored. A **distribution analysis of AAMI classes** is performed to understand class imbalances.

A **patient-based split** is used for training and testing, ensuring heartbeats from the same patient do not appear in both sets. A **70%-30% split** is used with a fixed random seed for reproducibility.

### Exploratory Data Analysis (EDA)

EDA helps in understanding the characteristics of heartbeats in the dataset. Key steps include:

- **Visualizing the label distribution** to detect class imbalances.
- **Displaying heartbeat samples** for each label to observe morphological differences.
- **Applying PCA** to visualize data separation in lower dimensions.
- **Computing statistical measures** (mean, std, min, max, median) for each class.
- **Analyzing correlations** between average heartbeats of different classes.
- **Creating 2D histograms** to observe ECG signal variations over time.

### Feature Extraction

To enhance classification, feature extraction methods are used. A **neural network autoencoder** is considered to learn a **compressed latent representation** of heartbeat signals, which serves as input features for classification models.

## Test a Submission

The submissions must be placed in the `submissions` folder. For example, if your submission is named `my_submission`, its path should be:

```sh
submissions/my_submission
```

To test a specific submission, use:

```sh
ramp-test --submission my_submission
```

For more options, check:

```sh
ramp-test --help
```

## To Go Further

For more details about **ramp-workflow**, refer to the [official documentation](https://paris-saclay-cds.github.io/ramp-workflow/).

