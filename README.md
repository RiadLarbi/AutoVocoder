
# PAcodec: Prosody-Aware Codec for Speech Synthesis

**PAcodec** (Prosody-Aware Codec) is an enhanced, F0-guided fork of the original AutoVocoder, designed to improve the naturalness, clarity, and prosody of synthesized speech. This repository implements a **Fundamental Frequency (F0)-Guided Parallel Architecture** combined with **attention-enhanced residual blocks** to produce high-fidelity and pitch-aware speech output. It is built upon the original AutoVocoder architecture and incorporates new methods for handling spectral components and prosodic features.

---


##  Overview
![architecture_overview](https://github.com/user-attachments/assets/00da8497-7a43-4280-9b5e-ca757becbae8)
PAcodec enhances the AutoVocoder in the following key ways:

- **F0-Guided Parallel Encoding**:
  - Separates spectral processing into two parallel paths:
    - A general spectral encoder.
    - An F0-masked encoder focusing on frequency bands around the fundamental frequency.
- **CBAM-Enhanced Residual Blocks**:
  - Uses channel and spatial attention mechanisms to focus on the most relevant speech features.
- **Pitch-Aware Representation**:
  - Incorporates Gaussian masking based on F0 extracted via the pYIN algorithm for pitch-centric modeling.
- **Improved Decoder**:
  - Reconstructs phase and magnitude components via a unified decoder and synthesizes waveforms with inverse STFT in polar form.

---

##  Features
![f0 data flow](https://github.com/user-attachments/assets/2e2ac8d5-53e9-446d-ab94-b2afa57c9111)

- **Spectral Input**: Phase, magnitude, and power spectrograms.
- **F0 Integration**: Gaussian masking on frequency bins around the estimated F0.
- **Dual Encoder Paths**: Main path + F0-masked path with fusion at the feature level.
- **CBAM Attention**: Enhances feature maps with spatial and channel-wise relevance.
- **Robust Reconstruction**: Decoding into polar spectrograms and waveform synthesis.

---

##  Architecture

![Full Encoder](https://github.com/user-attachments/assets/0889f66a-f72e-4735-b051-f1f216650854)

## 🏁 Getting Started

### Prerequisites

- Python 3.8+
- PyTorch 1.10+
- `numpy`, `librosa`, `torchaudio`, `scipy`, `matplotlib`
- pYIN-compatible F0 extractor (via `librosa` or `pyin`)

### Installation

```bash
git clone https://github.com/your-username/PAcodec.git
cd PAcodec
pip install -r requirements.txt
```

---

## 🔧 Usage

### Training

```bash
python train.py --config configs
```

### Inference

```bash
python inference.py --input audio.wav 
```

---

## 📊 Evaluation

![VCTK_f0_comparison](https://github.com/user-attachments/assets/b181901f-63ef-4181-8195-f5e0f5764070)

![LJSpeech_f0_comparison](https://github.com/user-attachments/assets/77013917-346f-43c9-93bd-e80a9bc44651)




---

## 📝 Citation

If you use PAcodec in your research, please cite:

```bibtex
@mastersthesis{larbi2025pacodec,
  title={Enhancing AutoVocoder Performance through Data Processing, Architecture Optimization, and Robustness in Text-to-Speech Systems},
  author={Larbi, Riad},
  year={2025},
  school={Budapest University of Technology and Economics}
}
```

---

Contact

For questions or collaborations, please open an issue or reach out via email: **[larbiriad.lr@gmail.com]**
