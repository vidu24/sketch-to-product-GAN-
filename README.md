# Sketch-to-Product: shoes Design Colorization using GANs

[](https://opensource.org/licenses/MIT)
[](https://www.python.org/downloads/)
[](https://pytorch.org/)

## 📝 Project Overview

This repository implements an end-to-end Deep Learning pipeline to transform hand-drawn shoe sketches into high-fidelity product renders. Utilizing **Conditional Generative Adversarial Networks (cGANs)**, the model learns to synthesize realistic textures, lighting, and reflections based on edge-only input sketches.


## 🧬 Architecture

The system utilizes a dual-network approach for image-to-image translation:

  * **Generator:** A U-Net based architecture with skip-connections to preserve spatial details from the input sketch.
  * **Discriminator:** A PatchGAN discriminator that penalizes structure at the scale of local image patches, ensuring high-frequency crispness in the output.
  * **Loss Functions:** A weighted combination of **Adversarial Loss** (to ensure realism) and **L1 Loss** (to ensure structural pixel-level consistency).

## 📁 Repository Structure

```text
├── models/               # Script definitions for Generator & Discriminator
├── data/                 # Sample input sketches and output pairs
├── notebooks/            # Training logs and Kaggle/Colab notebooks
├── requirements.txt      # Python dependencies
└── README.md             # Project documentation
```

## 🚀 Getting Started

### 1\. Installation

Clone the repository and install the required dependencies:

```bash
git clone https://github.com/vidu24/sketch-to-product-GAN-.git
cd sketch-to-product-GAN-
pip install -r requirements.txt
```

### 2\. Model Weights

The pre-trained `.pth` weights are excluded from the main Git history due to file size constraints (each file \> 200MB).

  * `gen1_final_polished.pth`
  * `gen2_final_polished.pth`

> **Note:** To run inference locally, ensure you place the weight files in the `models/` directory.

### 3\. Running Inference

To generate a product render from a custom sketch:

```bash
python inference.py --input sample_sketch.png --model models/gen1_final_polished.pth
```

## 📈 Training Progress

The model undergoes significant refinement across training epochs:

  * **Epoch 5:** Captures basic color blocking and car silhouettes.
  * **Epoch 10:** Improved adherence to sketch boundaries and initial shadow mapping.
  * **Final Polished:** High-resolution texture synthesis including realistic paint reflections and glass transparency.

## 🛠️ Tech Stack

  * **Language:** Python
  * **Deep Learning:** PyTorch, Torchvision
  * **Image Processing:** OpenCV, Pillow, Albumentations
  * **Development Env:** WSL (Ubuntu), Training performed on Kaggle/Google Colab GPUs

## 👤 Author

**Vidwath** \* 

  * [GitHub](https://www.google.com/search?q=https://github.com/vidu24)

-----
