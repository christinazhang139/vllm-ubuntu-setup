# 🎮 NVIDIA Driver Installation

[← Previous: Basic Dependencies](01-basic-dependencies.md) | [Next: CUDA Installation →](03-cuda-installation.md)

> 🎯 Install NVIDIA GPU drivers, which is a crucial step for running vLLM.

---

## 🔍 Check GPU

```bash
# Check if NVIDIA GPU exists
lspci | grep -i nvidia

# Check recommended drivers
ubuntu-drivers devices
```

### 📊 GPU Compatibility Check

```bash
# Check GPU compute capability (after driver installation)
nvidia-smi --query-gpu=name,compute_cap,memory.total --format=csv
```

**vLLM GPU Requirements:**

| GPU Series | Compute Capability | vLLM Compatibility | Recommended CUDA |
|------------|-------------------|-------------------|------------------|
| **RTX 4090/4080** | 8.9 | ✅ Perfect Support | CUDA 12.1 |
| **RTX 4070/4060** | 8.9 | ✅ Perfect Support | CUDA 12.1 |
| **RTX 3090/3080** | 8.6 | ✅ Perfect Support | CUDA 11.8 |
| **RTX 3070/3060** | 8.6 | ✅ Perfect Support | CUDA 11.8 |
| **GTX 1080 Ti** | 6.1 | ❌ **Not Supported** | - |
| **GTX 1070/1060** | 6.1 | ❌ **Not Supported** | - |

> ⚠️ **Important**: vLLM requires GPU compute capability ≥ 7.0

---

## ⚡ Automatic Installation (Recommended)

```bash
# Auto-install recommended driver
sudo ubuntu-drivers autoinstall

# Reboot system
sudo reboot
```

---

## ✅ Verify Installation

```bash
# Check driver status
nvidia-smi

# Check detailed GPU information
nvidia-smi --query-gpu=name,driver_version,memory.total,compute_cap --format=csv
```

**Expected Output:**
```
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 535.129.03             Driver Version: 535.129.03   CUDA Version: 12.2     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  NVIDIA GeForce ...  Off  | 00000000:01:00.0  On |                  N/A |
| 30%   45C    P8    25W / 450W |   1024MiB / 24564MiB |      0%      Default |
+-------------------------------+----------------------+----------------------+
```

> 💡 **Check Compatibility**: Refer to the GPU compatibility table above to confirm your GPU compute capability is ≥ 7.0

---

## 🚀 Next Steps

### ✅ If GPU supports vLLM (compute capability ≥7.0)
**[⚡ Install CUDA Toolkit →](03-cuda-installation.md)**

### ❌ If GPU doesn't support vLLM
Consider these options:
- 🔄 **Upgrade Hardware**: Buy RTX 30/40 series GPU
- ☁️ **Cloud Services**: Use Google Colab Pro, AWS, Azure, etc.
- 📚 **Learning Mode**: Continue learning setup for future hardware upgrade
