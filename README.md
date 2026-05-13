# Super-Resolution-of-Satellite-Images-using-Deep-Learning

🛰️ Satellite-SR
Deep Learning Super-Resolution for Satellite Imagery

Satellite-SR is a lightweight PyTorch project for enhancing low-resolution orbital imagery using deep learning–based 4× super-resolution techniques.

The project implements two efficient architectures designed for satellite image reconstruction:

- 🚀 ESPCN — fast sub-pixel convolution network optimized for efficient upscaling
- 🧠 SR-Autoencoder — encoder–decoder architecture for spatial detail recovery

Both models are trained and evaluated through fully reproducible Jupyter notebooks with automatic checkpointing and image quality evaluation.

✨ Key Features
- 🔬 4× Satellite Image Super-Resolution
- ⚡ Lightweight & Efficient Architectures
- 📈 PSNR / SSIM Evaluation
- 💾 Automatic Best Checkpoint Saving
- 🖼️ Bicubic Baseline Comparison
- 📊 Training Curve Visualization
- 🔁 Data Augmentation Pipeline


📂 Repository Structure
├── espcn_v3.ipynb
├── autoencoder_sr_espcn_params.ipynb
│
├── checkpoints/
│   └── espcn_best.pth
│
└── checkpoints_ae_autoencoder/
    └── autoencoder_best.pth


🧠 Models
- 🚀 ESPCN

Efficient sub-pixel convolutional network using PixelShuffle for fast 4× upscaling.

Conv(3→64, 5×5) + PReLU
Conv(64→32, 3×3) + PReLU
Conv(32→3×16, 3×3) + PixelShuffle(×4)


- 🧠 SR-Autoencoder

Encoder–decoder network for reconstructing high-resolution satellite imagery.

Encoder: 3 → 64 → 128 → 256
Decoder: 256 → 128 → 64 → 3


⚙️ Training Configuration
Parameter	Value:
Scale Factor	×4
Batch Size	48
Epochs	50
Learning Rate	1e-4
Optimizer	Adam
Loss Function	MSE



📁 Dataset Format
dataset/
├── LR_new/   # Low-resolution images
└── hr/       # High-resolution ground truth


📊 Evaluation
The notebooks automatically:
- Compute PSNR & SSIM
- Compare against bicubic interpolation
- Save the best model checkpoints
- Generate training curve visualizations


🛠️ Requirements:
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip install numpy pillow matplotlib tqdm
