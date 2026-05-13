# Super-Resolution-of-Satellite-Images-using-Deep-Learning

Satellite-SR 🚀
ESPCN & Autoencoder Super-Resolution for Orbital Imagery

Satellite-SR is a PyTorch-based project for 4× satellite image super-resolution, focused on enhancing low-resolution orbital imagery using lightweight deep learning models.

The repository includes two architectures:

ESPCN — a fast and efficient sub-pixel convolution network
SR-Autoencoder — an encoder–decoder model for spatial detail reconstruction

Both models are trained through end-to-end Jupyter notebooks with:

📈 PSNR & SSIM evaluation
💾 Automatic checkpoint saving
🖼️ Bicubic baseline comparison
📊 Training curve visualization
🔁 Data augmentation support
📂 Repository Structure
├── espcn_v3.ipynb                     # ESPCN training & evaluation
├── autoencoder_sr_espcn_params.ipynb # SR-Autoencoder pipeline
├── checkpoints/
│   └── espcn_best.pth
└── checkpoints_ae_autoencoder/
    └── autoencoder_best.pth
⚙️ Models
ESPCN

Efficient super-resolution network using PixelShuffle for fast 4× upscaling.

Architecture

Conv(3→64, 5×5) + PReLU
Conv(64→32, 3×3) + PReLU
Conv(32→3×16, 3×3) + PixelShuffle(×4)
SR-Autoencoder

Encoder–decoder architecture that reconstructs high-resolution satellite images using transposed convolutions.

Architecture

Encoder: 3 → 64 → 128 → 256
Decoder: 256 → 128 → 64 → 3
🛠️ Installation
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
pip install numpy pillow matplotlib tqdm
📁 Dataset Format
dataset/
├── LR_new/   # Low-resolution images
└── hr/       # High-resolution ground truth

Update dataset paths inside the notebooks before training.

▶️ Run Training
jupyter notebook espcn_v3.ipynb

or

jupyter notebook autoencoder_sr_espcn_params.ipynb
📊 Training Setup
Parameter	Value
Scale Factor	×4
Batch Size	48
Epochs	50
Learning Rate	1e-4
Loss	MSE
Optimizer	Adam
📈 Evaluation

The notebooks automatically:

Load the best checkpoint
Compute PSNR & SSIM
Compare against bicubic interpolation
Save training curves
📋 Requirements
torch
torchvision
numpy
Pillow
matplotlib
tqdm
