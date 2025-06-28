# 🎧 Multi‑module Deepfake Audio Detector

**📝 Project Type:** Research project  
**📚 Course:** Digital Forensics

---

## Project Overview

This repository contains a **Jupyter Notebook** implementation of a **multi-module deepfake audio detection system**. The detector analyzes audio samples to identify manipulated (deepfake) content using a combination of feature extraction, machine learning models, and decision fusion techniques.

---

## 🎯 Motivation & Forensics Impact

Deepfake audio—synthetic or manipulated voice recordings—pose a growing threat in the forensics domain:

- **Trusted Evidence at Risk:** Audio recordings often serve as key evidence in investigations. Undetected deepfakes can mislead courts or investigations.
- **Privacy & Security Threats:** Malicious actors may impersonate individuals to deceive victims or manipulate public opinion.
- **Forensic Integrity:** Robust detection tools are critical to maintain trust in audio-based evidence and uphold justice in legal systems.

---
## 🛠️ Techniques Used

| Module        | Description                                  |
|---------------|----------------------------------------------|
| **Entropy-Based** | Logistic Regression on entropy-based features|
| **MFCC-Based**    | Random Forest using Mel-Frequency Cepstral Coefficients |
| **MelCNN**        | CNN trained on mel-spectrograms              |
| **RawWaveformCNN**| CNN trained directly on waveform inputs      |

Each model is evaluated individually, then combined using ensemble decision strategies for better generalization and detection reliability.

---

## 📈 Experimental Results

After training and evaluating on the ASVspoof 2019 dataset:

- **Entropy Classifier (Logistic Regression)**
  - Validation Accuracy: ~**81.2%**
  - Test Accuracy: ~**80.5%**

- **MFCC Classifier (Random Forest)**
  - Validation Accuracy: ~**92.6%**
  - Test Accuracy: ~**90.7%**

- **MelCNN**
  - Validation Accuracy: ~**90.3%**
  - Test Accuracy: ~**89.5%**

- **RawCNN**
  - Validation Accuracy: ~**91.1%**
  - Test Accuracy: ~**89.4%**

---

## 🧪 Dataset

- Dataset used: **ASVspoof 2019 LA** (Logical Access subset)
- Format: FLAC audio files
- Labels: `bonafide` (real), `spoof` (deepfake)

📌 Dataset must be pre-downloaded and path configured in `main()` function.

---
## 🧩 System Architecture

This multi-module approach enhances detection accuracy and robustness:

1. **Feature Extraction**  
   - Extract acoustic and spectral features such as MFCCs, pitch, and spectral centroid.

2. **Model Ensemble**  
   - Train multiple detectors (e.g., SVM, Random Forest, CNN) on the extracted features.

3. **Decision Fusion**  
   - Combine model outputs using voting or weighted averaging to reach a final classification (genuine vs. deepfake).

---

## 🛠️ Usage Instructions

1. **Ensure required libraries are installed:**  
  ```bash
   pip install -r requirements.txt
````
 
2. **Launch the notebook:**

   ```bash
   jupyter notebook Multi_module_Deepfake_Audio_Detector.ipynb
   ````

3. **Follow these steps within the notebook:**

   * Load your audio dataset (genuine vs. deepfake)
   * Run feature extraction
   * Train and evaluate individual models
   * Apply decision fusion to combine model predictions
   * Analyze results: accuracy, precision, recall, ROC curves

---

## 📂 File Structure

```

├── Multi\_module\_Deepfake\_Audio\_Detector.ipynb   # Main notebook
├── features\_entropy.py                          # Entropy feature extractor
├── features\_mfcc.py                             # MFCC extractor
├── features\_melcnn.py                           # MelCNN model + extractor
├── features\_rawcnn.py                           # Raw waveform CNN
└── utils, models, configs 

````

---

##  Requirements

* Python 3.7+
* Jupyter Notebook
* Key libraries:

  ```
  numpy, pandas, librosa, scikit-learn, tensorflow (or torch), matplotlib, seaborn
  ```

---

##  Forensic Use & Relevance

This tool provides digital forensic analysts with a **practical, modular detection pipeline** to verify audio authenticity. It underlines the importance of:

* **Reliable validation** of audio-based evidence
* **Scientific rigour** through multi-model ensemble techniques
* **Transparency**, enabling traceability of detection steps—crucial in legal contexts

---

## 🎓 Academic Context

This project was completed for the **Digital Forensics course** as part of the BSc Cybersecurity program. It aims to explore the applicability of machine learning to deepfake detection in modern forensics.



