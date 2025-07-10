# 📋 Basic Dependencies Installation

[← Back to Home](../README.md) | [Next: NVIDIA Driver Installation →](02-nvidia-drivers.md)

> 🎯 Install basic system packages and tools required for running vLLM.

---

## ⚡ Quick Installation

```bash
# Update system packages
sudo apt update && sudo apt upgrade -y

# Install essential tools
sudo apt install -y \
    git \
    curl \
    wget \
    vim \
    htop \
    tree \
    build-essential
```

## ✅ Verify Installation

```bash
# Check key components
git --version
gcc --version
```

**Expected Output:**
```
git version 2.34.1
gcc (Ubuntu 11.4.0) 11.4.0
```

---

## 🚀 Next Steps

Choose based on your situation:

- **[🎮 Install NVIDIA Drivers](02-nvidia-drivers.md)** - If you have NVIDIA GPU (recommended)
- **[🐍 Configure Python Environment](04-python-setup.md)** - If you already have GPU drivers, go directly to Python setup
