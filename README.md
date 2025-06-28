## ✅ `README.md` (Deepfake Audio Detector – Forensics Project)

```markdown
# 🎧 Multi‑module Deepfake Audio Detector

> A modular deepfake audio detection pipeline for digital forensics — blending classical ML and deep learning models to validate audio authenticity.

---

## 📘 Project Summary

This repository implements a **multi-module deepfake audio detection system** developed as a part of a **Digital Forensics course research project**. The tool is designed to detect synthetic or tampered voice recordings using an ensemble of acoustic feature-based models and deep learning classifiers.

---

## 🔍 Why Deepfake Detection Matters in Forensics

In the digital forensics field, **voice recordings often serve as critical evidence**. With the rise of deepfake technology, it has become alarmingly easy to synthesize realistic fake audio. This threatens:

-  **Integrity of court-admissible evidence**
-  **Impersonation in fraud and social engineering attacks**
-  **Public trust in media and audio surveillance systems**

By equipping forensic analysts with robust deepfake detectors, we help preserve truth and accountability in investigative processes.

---

##  Techniques Used

| Module        | Description                                  |
|---------------|----------------------------------------------|
| Entropy-Based | Logistic Regression on entropy-based features|
| MFCC-Based    | Random Forest using Mel-Frequency Cepstral Coefficients |
| MelCNN        | CNN trained on mel-spectrograms              |
| RawWaveformCNN| CNN trained directly on waveform inputs      |

Each model is evaluated individually, then combined using ensemble decision strategies for better generalization and detection reliability.

---

## 📈 Experimental Results

After training and evaluating on the ASVspoof 2019 dataset (subset of 5,000 samples):

- **Entropy Classifier (Logistic Regression)**
  - Validation Accuracy: ~**81.2%**
  - Test Accuracy: ~**80.5%**

- **MFCC Classifier (Random Forest)**
  - Validation Accuracy: ~**91.6%**
  - Test Accuracy: ~**90.7%**

- **MelCNN**
  - Validation Accuracy: ~**90.3%**
  - Test Accuracy: ~**89.5%**

- **RawCNN**
  - Validation Accuracy: ~**88.1%**
  - Test Accuracy: ~**87.4%**

---

## 📂 File Structure

```

├── Multi\_module\_Deepfake\_Audio\_Detector.ipynb   # Main notebook
├── features\_entropy.py                          # Entropy feature extractor
├── features\_mfcc.py                             # MFCC extractor
├── features\_melcnn.py                           # MelCNN model + extractor
├── features\_rawcnn.py                           # Raw waveform CNN
└── utils, models, configs (recommended to add)

````

---

##  Dataset

- Dataset used: **ASVspoof 2019 LA** (Logical Access subset)
- Format: FLAC audio files
- Labels: `bonafide` (real), `spoof` (deepfake)

📌 Dataset must be pre-downloaded and path configured in `main()` function.

---

## ⚙️ Requirements

- Python 3.7+
- Jupyter Notebook
- `torch`, `torchaudio`, `librosa`, `scikit-learn`, `numpy`, `matplotlib`, `seaborn`

Install dependencies:

```bash
pip install -r requirements.txt
````

---

## Running the Project

1. Download the ASVspoof 2019 LA dataset.
2. Clone this repository.
3. Launch the notebook:

```bash
jupyter notebook Multi_module_Deepfake_Audio_Detector.ipynb
```

4. Run each cell step-by-step:

   * Load data
   * Extract features
   * Train models
   * Evaluate & analyze results

---

## 🎓 Academic Context

This project was completed as part of the **Digital Forensics course** within the Master’s in Cybersecurity program. It explores the integration of machine learning and deep learning methods in combating audio deepfakes—an emerging threat in digital forensics.

