# A-robust-fetal-ECG-detection-method-for-abdominal-recordings

Python pipeline for robust fetal ECG (FECG) detection from non-invasive maternal abdominal ECG (AECG) signals. It extracts fetal heart activity from signals containing both maternal ECG (MECG) and fetal ECG, detects fetal QRS complexes, and estimates the Fetal Heart Rate (FHR).

# The paper
I implemented the pipeline proposed in the paper "_A Robust Fetal ECG Detection Method for Abdominal Recordings_" by Suzanna M. M. Martens, Chiara Rabotti, Massimo Mischi, and Rob J. Sluijter.

The pipeline is composed by several steps and starts by cleaning the signals, removing baseline drift with a high-pass FIR filter and eliminating power-line interference at 50 Hz. The signals are then upsampled to improve temporal resolution. Maternal QRS complexes are detected using PCA and cross-correlation, and the maternal ECG is subtracted to isolate the fetal signal. Fetal QRS complexes are subsequently identified, allowing the estimation of fetal heart rate. The pipeline also visualizes the average fetal ECG per channel and evaluates performance using metrics such as SNR, SIR, sensitivity, PPV, F1-score, and accuracy.

# The dataset
The set of data I use is the Set-A from https://physionet.org/content/challenge-2013/1.0.0/ and the code is specific for the signal _a14_ of the dataset. 

# The libraries
In my code I use the following libraries:
- numpy
- scipy.signal
- matplotlib.pyplot
- pandas
- and from scipy.signal I import resample, correlate, butter, filtfilt

# The repository
This repository contains the notebook with the code, two audio files generated from the S1 and S5 signals, a PowerPoint presentation of the project, and an Excel file (.xlsx) summarizing the mean performance metrics across all items in the dataset.
