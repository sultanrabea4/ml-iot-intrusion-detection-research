# Machine Learning & Deep Learning for IoT / IIoT Intrusion Detection: Research Review

A critical review of **10 recent research papers (2023–2024)** on ML/DL-based **malware and intrusion detection** for IoT, IIoT and IoMT. The team compared traditional ML, deep hybrid models, federated learning and **online contrastive learning (AOC-IDS)**, then ran the selected model in Google Colab.

> Deep Learning (DLI) group project (5 members, 2 papers each). This repository summarises **my two paper reviews**, **the AOC-IDS implementation and Gradio GUI that I built**, and the group's comparative analysis.

---

## My Paper Reviews

### 1. *A novel approach detection for IIoT attacks via artificial intelligence* (Karacayılmaz & Artuner, 2024)
- **Goal:** detect **MitM, DDoS and Start-Stop** attacks against **PLCs** in critical infrastructure
- **Method:** a real PLC testbed (Modbus / MQTT), traffic captured through port mirroring, and a hybrid rule-based plus AI expert system
- **Result:** reported **>98% accuracy** with low latency
- **My critique:** high practical value (real hardware rather than synthetic data), but manual rules limit scalability and coverage of new attacks

### 2. *An Improved Intrusion Detection Method for IIoT Using Attention Mechanisms, BiGRU and Inception-CNN* (Yang et al., 2024)
- **Goal:** solve poor detectability, redundant high-dimensional features and **class imbalance**
- **Method:** the **NIDS-BAI** architecture: BiGRU for temporal features, attention for feature weighting, and Inception-CNN for multi-scale spatial features
- **Result:** outperformed baselines on three datasets, especially for minority classes
- **My critique:** a strong architecture, but heavy for resource-constrained edge devices, gives no latency figures, and is only tested on benchmark datasets

## Group Findings
- Most models are **offline** and depend on labelled data, which makes them vulnerable to **concept drift** and **zero-day** attacks
- Deep hybrids (CNN-LSTM, transformers) improve accuracy at a high compute cost
- Federated learning improves privacy but adds complexity
- **AOC-IDS** (Autonomous Online Contrastive Learning) was chosen as the most deployable option: it **adapts continuously**, needs fewer labels and handles evasion and zero-day attacks better

## Implementation (my work)
I ran the official **AOC-IDS** repository in **Google Colab** and built a **Gradio GUI** wrapper around it:
- Mounts Google Drive for persistent storage, clones the official repository and installs its dependencies
- A GUI for choosing the dataset and training parameters
- Builds the command and runs the original `online_training.py` through `subprocess`, streaming the console output in real time
- Leaves the original model code unchanged so results stay reproducible

## Skills Demonstrated
Research-paper critical analysis · ML/DL for cybersecurity · IIoT/ICS security · deep-learning architectures (BiGRU, attention, CNN) · Python, Google Colab and Gradio

## Author
**Sultan Mohammed Rabea** · [LinkedIn](https://www.linkedin.com/in/sultan-rabea/) · [GitHub](https://github.com/sultanrabea4)
