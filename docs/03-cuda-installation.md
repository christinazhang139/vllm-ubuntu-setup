# ⚡ CUDA Toolkit Installation

[← Previous: NVIDIA Drivers](02-nvidia-drivers.md) | [Next: Python Environment Setup →](04-python-setup.md)

> 🎯 Install CUDA development toolkit to provide GPU compute support for PyTorch and vLLM.

---

## 🔍 Choose CUDA Version

Choose appropriate CUDA version based on your GPU:

| GPU Series | Recommended CUDA | PyTorch Support | Notes |
|------------|------------------|-----------------|-------|
| **RTX 4090/4080** | **CUDA 12.1** | ✅ cu121 | Best balance |
| **RTX 4070/4060** | **CUDA 12.1** | ✅ cu121 | Stable support |
| **RTX 3090/3080** | **CUDA 11.8** | ✅ cu118 | Wide compatibility |
| **RTX 3070/3060** | **CUDA 11.8** | ✅ cu118 | Recommended |

> ⚠️ **Important**: Not recommended to use latest versions (like CUDA 12.9+) as PyTorch and vLLM may not support them yet.

> 💡 **Selection Principle**: Compatibility > Latest version. Ensure PyTorch has corresponding cu version support.

---

## ⚡ Install CUDA 12.1 (Recommended for RTX 40 series)

```bash
# Download CUDA 12.1 installer
wget https://developer.download.nvidia.com/compute/cuda/12.1.0/local_installers/cuda_12.1.0_530.30.02_linux.run

# Run installer
sudo sh cuda_12.1.0_530.30.02_linux.run

# In the installation interface:
# - Uncheck Driver (already installed)
# - Keep CUDA Toolkit checked
# - Continue installation
```

## ⚡ Install CUDA 11.8 (Recommended for RTX 30 series)

```bash
# Download CUDA 11.8 installer
wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda_11.8.0_520.61.05_linux.run

# Run installer
sudo sh cuda_11.8.0_520.61.05_linux.run

# In the installation interface:
# - Uncheck Driver (already installed)
# - Keep CUDA Toolkit checked
# - Continue installation
```

---

## ✅ Verify Installation

```bash
# Check CUDA version
nvcc --version

# Check CUDA compiler path
which nvcc

# Verify GPU and CUDA
nvidia-smi
```

### 🔧 If nvcc command is not available

```bash
# Only set environment variables if nvcc is not available
echo 'export PATH=/usr/local/cuda/bin:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc

# Reload configuration
source ~/.bashrc

# Verify again
nvcc --version
```

**Expected Output:**
```bash
# nvcc --version output example
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2023 NVIDIA Corporation
Built on Mon_Apr__3_17:16:06_PDT_2023
Cuda compilation tools, release 12.1, V12.1.105

# nvidia-smi should show CUDA Version
CUDA Version: 12.1
```

---

## 🚀 Next Steps

After CUDA installation is complete:

**[🐍 Configure Python Environment →](04-python-setup.md)**

> 💡 **Note**: The next step will check Python version to ensure it meets vLLM requirements.
