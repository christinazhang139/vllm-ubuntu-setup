# 🚀 vLLM Ubuntu Installation Guide

![Ubuntu](https://img.shields.io/badge/Ubuntu-20.04+-orange.svg)
![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![CUDA](https://img.shields.io/badge/CUDA-11.8+-green.svg)
![vLLM](https://img.shields.io/badge/vLLM-latest-purple.svg)

[English](README.md) | [中文](README_CN.md)

> 🎯 This is a modular vLLM installation guide. Choose the appropriate installation steps based on your specific situation.

---

## 📚 Table of Contents

### 🔍 Preparation Phase
- **[📋 Hardware Requirements](#-hardware-requirements-must-meet)** - Check if your hardware meets the requirements
- **[📋 Recommended Software Combinations](#-recommended-software-combinations)** - Choose suitable version combinations
- **[🛣️ Installation Path Selection](#️-installation-path-selection)** - Choose installation method based on your situation
  - [Situation 1: Fresh System (Recommended for beginners)](#-situation-1-fresh-system-recommended-for-beginners)
  - [Situation 2: Existing CUDA Environment](#-situation-2-existing-cuda-environment)
  - [Situation 3: Existing PyTorch Environment](#-situation-3-existing-pytorch-environment)

### 📖 Detailed Installation Guide
- **[📋 Basic Dependencies Installation](docs/01-basic-dependencies.md)** - System packages and tools
- **[🎮 NVIDIA Driver Installation](docs/02-nvidia-drivers.md)** - GPU driver configuration
- **[⚡ CUDA Toolkit Installation](docs/03-cuda-installation.md)** - CUDA development environment
- **[🐍 Python Environment Setup](docs/04-python-setup.md)** - Python version check
- **[📦 vLLM Installation](docs/05-vllm-installation.md)** - Complete installation of virtual environment, PyTorch and vLLM
- **[✅ Verification Testing](docs/06-verification.md)** - Installation verification


---

## 📋 Hardware Requirements (Must Meet)

### **Basic Requirements:**
- **CPU**: At least 4 cores, 8+ cores recommended
- **Memory**: At least 16GB, 32GB+ recommended
- **Storage**: 
  - **System Disk**: At least 50GB available space
  - **Model Storage**: 200GB-2TB (depends on model size)
    - 7B models: ~15GB
    - 13B models: ~25GB  
    - 70B models: ~140GB
    - Multiple models or fine-tuning: 500GB+
- **Network**: Stable internet connection (required for initial model downloads)

### **GPU Requirements (Critical):**
- **Required**: NVIDIA GPU (AMD GPU support limited)
- **Compute Capability**: 7.0 or higher
- **VRAM Requirements**:
  - Small model testing (125M-1B parameters): 4-6GB VRAM
  - Medium models (1B-7B parameters): 8-16GB VRAM
  - Large models (7B-13B parameters): 16-24GB VRAM
  - Extra large models (30B-70B parameters): 48GB+ VRAM or multi-GPU

### **Supported GPU Models:**
- ✅ RTX 4090 (24GB) - Recommended, can run 13B models
- ✅ RTX 4080 (16GB) - Suitable for 7B-13B models
- ✅ RTX 3090/3090Ti (24GB) - Good support for 13B models
- ✅ RTX 3080/3080Ti (10-12GB) - Recommended for 7B models
- ✅ RTX 3060 Ti/3070 (8-10GB) - Small models and experiments
- ✅ Tesla V100/A100/H100 - Server-grade
- ⚠️ RTX 2060/2070 (6-8GB) - Small models only
- ❌ GTX 1050/1050 Ti (4GB) - Insufficient compute capability

---

## 📋 Recommended Software Combinations

To ensure optimal compatibility and performance, use the following version combinations:

### 🥇 **Combination 1 (Latest Stable)**
| Component | Recommended Version | Notes |
|-----------|-------------------|-------|
| **Ubuntu** | 22.04 LTS | Latest LTS, best support |
| **Python** | 3.11.x | Best performance, good compatibility |
| **NVIDIA Driver** | 535.x+ | Supports latest GPU and CUDA |
| **CUDA** | 12.1 | Latest stable version |
| **PyTorch** | 2.1.x+ | Supports CUDA 12.1 |
| **vLLM** | Latest | Latest features and fixes |

### 🥈 **Combination 2 (Conservative Stable)**
| Component | Recommended Version | Notes |
|-----------|-------------------|-------|
| **Ubuntu** | 20.04 LTS | Best stability |
| **Python** | 3.10.x | Long-term support version |
| **NVIDIA Driver** | 470.x+ | Stable driver version |
| **CUDA** | 11.8 | Widely supported version |
| **PyTorch** | 2.0.x | Stable PyTorch version |
| **vLLM** | 0.2.7+ | Verified version |

### 🎯 **RTX 4090 Users Special Recommendation**
| Component | Recommended Version | Notes |
|-----------|-------------------|-------|
| **Ubuntu** | 22.04 LTS | Supports latest hardware |
| **Python** | 3.11.x | Best performance |
| **NVIDIA Driver** | 535.129.03+ | Optimal driver for RTX 4090 |
| **CUDA** | 12.1 | Full utilization of RTX 4090 |
| **PyTorch** | 2.1.0+cu121 | Compiled specifically for CUDA 12.1 |
| **vLLM** | Latest | Best RTX 4090 support |

### ⚠️ **Version Compatibility Notes**
- CUDA version must match PyTorch version
- Driver version must support selected CUDA version
- Python 3.12 not yet fully supported by all ML libraries
- Avoid using development versions (dev/nightly) in production

---

## 🛣️ Installation Path Selection

Choose the most suitable installation path based on your system status:

### 🆕 Situation 1: Fresh System (Recommended for beginners)
Your system is freshly installed with nothing configured:

1. **[📋 Basic Dependencies Installation](docs/01-basic-dependencies.md)** - Install necessary system packages
2. **[🎮 NVIDIA Driver Installation](docs/02-nvidia-drivers.md)** - Install GPU drivers
3. **[⚡ CUDA Toolkit Installation](docs/03-cuda-installation.md)** - Install CUDA development environment
4. **[🐍 Python Environment Setup](docs/04-python-setup.md)** - Check Python version
5. **[📦 vLLM Installation](docs/05-vllm-installation.md)** - Complete installation of virtual environment, PyTorch and vLLM
6. **[✅ Verification Testing](docs/06-verification.md)** - Verify successful installation

### 🔧 Situation 2: Existing CUDA Environment
You already have NVIDIA drivers and CUDA installed:

1. **[🐍 Python Environment Setup](docs/04-python-setup.md)**
2. **[📦 vLLM Installation](docs/05-vllm-installation.md)** - Complete installation of virtual environment, PyTorch and vLLM
3. **[✅ Verification Testing](docs/06-verification.md)**

### 🚀 Situation 3: Existing PyTorch Environment
You already have a PyTorch environment:

1. **[📦 vLLM Installation](docs/05-vllm-installation.md)** - Install vLLM only
2. **[✅ Verification Testing](docs/06-verification.md)**

---


**[🔍 Complete Environment Verification Script](docs/06-verification.md)** - One-time check of all components for correct installation

This verification script checks:
- ✅ System information and hardware compatibility
- ✅ Python environment and virtual environment
- ✅ NVIDIA drivers and GPU status
- ✅ CUDA toolkit and version compatibility
- ✅ PyTorch installation and GPU support
- ✅ vLLM installation and functionality testing
- ✅ System resources and performance evaluation

### ⚡ Quick Verification Command

```bash
# Activate virtual environment
cd ~/vllm-learning
source vllm-env/bin/activate

# Basic functionality test
python -c "
import torch
import vllm
print(f'✅ PyTorch version: {torch.__version__}')
print(f'✅ CUDA available: {torch.cuda.is_available()}')
print(f'✅ GPU count: {torch.cuda.device_count()}')
if torch.cuda.is_available():
    print(f'✅ GPU model: {torch.cuda.get_device_name(0)}')
    print(f'✅ VRAM: {torch.cuda.get_device_properties(0).total_memory // 1024**3}GB')
print(f'✅ vLLM version: {vllm.__version__}')
print('🎉 Environment setup complete!')
"
```

If all checks pass, your vLLM environment is perfectly configured!

---

## 🤝 Contributing Guidelines

Welcome to submit improvement suggestions! Please ensure:

1. 🔍 Test your modifications
2. 📝 Update relevant documentation
3. 📋 Submit detailed PR description

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

<div align="center">

**🌟 If this project helps you, please give it a Star! 🌟**

**📚 Choose your installation path and start your vLLM learning journey!**

Made with ❤️ by [Christina](https://github.com/christinazhang139)

</div>
