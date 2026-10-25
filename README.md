# transmission-line-fault-classification
AI-based transmission line fault classification using an Artificial Neural Network (ANN), Python, and MATLAB/Simulink.
# AI-Based Transmission Line Fault Classification Using ANN

## Project Overview

This project focuses on detecting and classifying faults in a three-phase transmission line using an Artificial Neural Network (ANN). Voltage and current measurements are generated through MATLAB/Simulink simulations and processed in Python to classify different transmission-line operating conditions.

The project explores the application of Artificial Intelligence in electrical power systems.

## Objectives

- Simulate normal and fault conditions in a three-phase transmission line.
- Generate voltage and current datasets using MATLAB/Simulink.
- Preprocess electrical measurements using Python.
- Train an ANN model to classify transmission-line faults.
- Evaluate the model using accuracy, a confusion matrix, and a classification report.
- Investigate methods to improve classification performance.

## Fault Classes

The model classifies six operating conditions:

| Label | Description |
|---|---|
| Normal | Normal operating condition |
| LG | Single line-to-ground fault |
| LL | Line-to-line fault |
| LLG | Double line-to-ground fault |
| LLL | Three-phase short-circuit fault without ground |
| LLLG | Three-phase-to-ground fault |

## Tools and Technologies

- MATLAB/Simulink — Power-system modelling and fault simulation
- Python — Data processing and model development
- Pandas and NumPy — Dataset handling
- Scikit-learn — Data preprocessing, ANN training, and evaluation
- Matplotlib and Seaborn — Data visualization
- GitHub — Version control and documentation

## Dataset Description

The selected baseline dataset is `Transmission_Fault_Dataset_updated.csv`.

It contains 24,006 rows and eight columns, with 4,001 samples per class.

| Column | Description |
|---|---|
| `Time` | Simulation time |
| `Va`, `Vb`, `Vc` | Three-phase voltage measurements |
| `Ia`, `Ib`, `Ic` | Three-phase current measurements |
| `Fault` | Target fault class |

The dataset is generated using a simulated three-phase power system containing a source, transmission-line sections, voltage and current measurement blocks, a fault block, and a load.

## ANN Model

The baseline model uses a Multi-Layer Perceptron (MLP) classifier implemented with Scikit-learn.

| Parameter | Configuration |
|---|---|
| Model | MLPClassifier |
| Hidden layers | (32, 16) |
| Activation | ReLU |
| Solver | Adam |
| Maximum iterations | 300 |
| Early stopping | Enabled |
| Random state | 42 |
| Input features | Va, Vb, Vc, Ia, Ib, Ic |
| Train-test split | 80:20 |
| Feature scaling | StandardScaler |
| Stratification | Enabled |

The dataset is divided into training and testing sets using stratified sampling. StandardScaler is fitted on the training data and applied to both sets.

## Baseline Results

| Metric | Result |
|---|---:|
| Test accuracy | 53.83% |
| Training iterations | 99 |
| Training samples | 19,204 |
| Test samples | 4,802 |

The baseline results show that some fault classes are frequently misclassified. These results serve as the reference point for further investigation and model improvement.

## Current Challenges

- Distinguishing fault classes with similar voltage and current patterns.
- Investigating the influence of simulation settings on dataset quality.
- Improving feature representation for different fault types.
- Reducing misclassification between fault classes.
- Evaluating generalization on independently simulated scenarios.

## Planned Improvements

- Perform exploratory data analysis and visualize electrical measurements.
- Investigate RMS values and symmetrical components as additional features.
- Study the effects of fault location, fault resistance, and fault inception time.
- Compare ANN performance with other machine-learning classifiers.
- Test the model on independently generated simulation scenarios.
- Document experiments and compare them with the original baseline.


## Project Status

**Current stage:** Baseline ANN implementation completed; model improvement and validation are ongoing.

## Future Scope

Future work includes improved feature extraction, broader simulation scenarios, independent testing, and investigation of real-time fault-classification applications.

## Author

**Surya Shinde**  
Third-Year B.E. Electrical Engineering Student

GitHub: [Miss-suryashinde](https://github.com/Miss-suryashinde)

---

*This project is for academic and research purposes. The reported baseline accuracy reflects the current simulation dataset and does not represent validated performance on a real transmission network.*  
