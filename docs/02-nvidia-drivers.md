# 🎮 NVIDIA驱动安装 / NVIDIA Driver Installation

[← 上一步: 基础依赖](01-basic-dependencies.md) | [下一步: CUDA安装 →](03-cuda-installation.md)

[← Previous: Basic Dependencies](01-basic-dependencies.md) | [Next: CUDA Installation →](03-cuda-installation.md)

> 🎯 安装NVIDIA GPU驱动，这是运行vLLM的关键步骤。
> 
> 🎯 Install NVIDIA GPU drivers, which is a crucial step for running vLLM.

---

## 🔍 检查GPU / Check GPU

```bash
# 检查是否有NVIDIA GPU / Check if NVIDIA GPU exists
lspci | grep -i nvidia

# 查看推荐驱动 / Check recommended drivers
ubuntu-drivers devices
```

### 📊 GPU兼容性检查 / GPU Compatibility Check

```bash
# 检查GPU计算能力（安装驱动后）/ Check GPU compute capability (after driver installation)
nvidia-smi --query-gpu=name,compute_cap,memory.total --format=csv
```

**vLLM GPU要求 / vLLM GPU Requirements:**

| GPU系列 / GPU Series | 计算能力 / Compute Capability | vLLM兼容性 / vLLM Compatibility | 推荐CUDA / Recommended CUDA |
|---------------------|------------------------------|--------------------------------|------------------------------|
| **RTX 4090/4080** | 8.9 | ✅ 完美支持 / Perfect | CUDA 12.1/12.4 |
| **RTX 4070/4060** | 8.9 | ✅ 完美支持 / Perfect | CUDA 12.1/12.4 |
| **RTX 3090/3080** | 8.6 | ✅ 完美支持 / Perfect | CUDA 11.8/12.1 |
| **RTX 3070/3060** | 8.6 | ✅ 完美支持 / Perfect | CUDA 11.8 |
| **GTX 1080 Ti** | 6.1 | ❌ **不支持** / **Not Supported** | - |
| **GTX 1070/1060** | 6.1 | ❌ **不支持** / **Not Supported** | - |

> ⚠️ **重要**: vLLM要求GPU计算能力 ≥ 7.0 / **Important**: vLLM requires GPU compute capability ≥ 7.0

---

## ⚡ 自动安装（推荐）/ Automatic Installation (Recommended)

```bash
# 自动安装推荐驱动 / Auto-install recommended driver
sudo ubuntu-drivers autoinstall

# 重启系统 / Reboot system
sudo reboot
```

---

## ✅ 验证安装 / Verify Installation

```bash
# 检查驱动状态 / Check driver status
nvidia-smi

# 检查GPU详细信息 / Check detailed GPU information
nvidia-smi --query-gpu=name,driver_version,memory.total,compute_cap --format=csv
```

**期望输出 / Expected Output:**
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

> 💡 **检查兼容性**: 对照上面的GPU兼容性表格，确认你的GPU计算能力是否 ≥ 7.0
> 
> 💡 **Check Compatibility**: Refer to the GPU compatibility table above to confirm your GPU compute capability is ≥ 7.0

---

## 🚀 下一步 / Next Steps

### ✅ 如果GPU支持vLLM（计算能力≥7.0）/ If GPU supports vLLM (compute capability ≥7.0)
**[⚡ 安装CUDA工具包 / Install CUDA Toolkit →](03-cuda-installation.md)**

### ❌ 如果GPU不支持vLLM / If GPU doesn't support vLLM
考虑以下选项 / Consider these options:
- 🔄 **升级硬件** / **Upgrade Hardware**: 购买RTX 30/40系列GPU / Buy RTX 30/40 series GPU
- ☁️ **云服务** / **Cloud Services**: 使用Google Colab Pro, AWS, Azure等 / Use Google Colab Pro, AWS, Azure, etc.
- 📚 **学习模式** / **Learning Mode**: 继续学习环境配置，准备未来硬件升级 / Continue learning setup for future hardware upgrade
