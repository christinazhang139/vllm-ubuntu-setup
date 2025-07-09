# ⚡ CUDA工具包安装 / CUDA Toolkit Installation

[← 上一步: NVIDIA驱动](02-nvidia-drivers.md) | [下一步: Python环境配置 →](04-python-setup.md)

[← Previous: NVIDIA Drivers](02-nvidia-drivers.md) | [Next: Python Environment Setup →](04-python-setup.md)

> 🎯 安装CUDA开发工具包，为PyTorch和vLLM提供GPU计算支持。
> 
> 🎯 Install CUDA development toolkit to provide GPU compute support for PyTorch and vLLM.

---

## 🔍 选择CUDA版本 / Choose CUDA Version

根据你的GPU选择合适的CUDA版本 / Choose appropriate CUDA version based on your GPU:

| GPU系列 / GPU Series | 推荐CUDA / Recommended CUDA | PyTorch支持 / PyTorch Support | 说明 / Notes |
|---------------------|------------------------------|-------------------------------|--------------|
| **RTX 4090/4080** | **CUDA 12.1** | ✅ cu121 | 最佳平衡 / Best balance |
| **RTX 4070/4060** | **CUDA 12.1** | ✅ cu121 | 稳定支持 / Stable support |
| **RTX 3090/3080** | **CUDA 11.8** | ✅ cu118 | 广泛兼容 / Wide compatibility |
| **RTX 3070/3060** | **CUDA 11.8** | ✅ cu118 | 推荐版本 / Recommended |

> ⚠️ **重要**: 不推荐使用最新版本（如CUDA 12.9+），因为PyTorch和vLLM可能还不支持。
> 
> ⚠️ **Important**: Not recommended to use latest versions (like CUDA 12.9+) as PyTorch and vLLM may not support them yet.

> 💡 **选择原则**: 兼容性 > 最新版本。确保PyTorch有对应的cu版本支持。
> 
> 💡 **Selection Principle**: Compatibility > Latest version. Ensure PyTorch has corresponding cu version support.

---

## ⚡ 安装CUDA 12.1（RTX 40系列推荐）/ Install CUDA 12.1 (Recommended for RTX 40 series)

```bash
# 下载CUDA 12.1安装包 / Download CUDA 12.1 installer
wget https://developer.download.nvidia.com/compute/cuda/12.1.0/local_installers/cuda_12.1.0_530.30.02_linux.run

# 运行安装程序 / Run installer
sudo sh cuda_12.1.0_530.30.02_linux.run

# 在安装界面中：/ In the installation interface:
# - 取消勾选Driver（已安装）/ Uncheck Driver (already installed)
# - 保持勾选CUDA Toolkit / Keep CUDA Toolkit checked
# - Continue安装 / Continue installation
```

## ⚡ 安装CUDA 11.8（RTX 30系列推荐）/ Install CUDA 11.8 (Recommended for RTX 30 series)

```bash
# 下载CUDA 11.8安装包 / Download CUDA 11.8 installer
wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda_11.8.0_520.61.05_linux.run

# 运行安装程序 / Run installer
sudo sh cuda_11.8.0_520.61.05_linux.run

# 在安装界面中：/ In the installation interface:
# - 取消勾选Driver（已安装）/ Uncheck Driver (already installed)  
# - 保持勾选CUDA Toolkit / Keep CUDA Toolkit checked
# - Continue安装 / Continue installation
```

---

## ✅ 验证安装 / Verify Installation

```bash
# 检查CUDA版本 / Check CUDA version
nvcc --version

# 检查CUDA编译器路径 / Check CUDA compiler path
which nvcc

# 验证GPU和CUDA / Verify GPU and CUDA
nvidia-smi
```

### 🔧 如果nvcc命令不可用 / If nvcc command is not available

```bash
# 只有在nvcc不可用时才需要设置环境变量 / Only set environment variables if nvcc is not available
echo 'export PATH=/usr/local/cuda/bin:$PATH' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc

# 重新加载配置 / Reload configuration
source ~/.bashrc

# 再次验证 / Verify again
nvcc --version
```

**期望输出 / Expected Output:**
```bash
# nvcc --version 输出示例 / nvcc --version output example
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2023 NVIDIA Corporation
Built on Mon_Apr__3_17:16:06_PDT_2023
Cuda compilation tools, release 12.1, V12.1.105

# nvidia-smi 应显示CUDA Version / nvidia-smi should show CUDA Version
CUDA Version: 12.1
```

---

## 🚀 下一步 / Next Steps

CUDA安装完成后 / After CUDA installation is complete:

**[🐍 配置Python环境 / Configure Python Environment →](04-python-setup.md)**

> 💡 **注意**: 下一步将创建Python虚拟环境并安装PyTorch，确保选择与你的CUDA版本匹配的PyTorch版本。
> 
> 💡 **Note**: The next step will create a Python virtual environment and install PyTorch. Make sure to choose a PyTorch version that matches your CUDA version.
