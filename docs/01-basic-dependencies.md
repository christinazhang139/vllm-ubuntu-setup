# 📋 基础依赖安装 / Basic Dependencies Installation

[← 返回主页](../README_CN.md) | [下一步: NVIDIA驱动安装 →](02-nvidia-drivers.md)

[← Back to Home](../README_CN.md) | [Next: NVIDIA Driver Installation →](02-nvidia-drivers.md)

> 🎯 安装运行vLLM所需的基础系统包和工具。
> 
> 🎯 Install basic system packages and tools required for running vLLM.

---

## ⚡ 快速安装 / Quick Installation

```bash
# 更新系统包 / Update system packages
sudo apt update && sudo apt upgrade -y

# 安装必要的工具 / Install essential tools
sudo apt install -y \
    git \
    curl \
    wget \
    vim \
    htop \
    tree \
    build-essential
```

## ✅ 验证安装 / Verify Installation

```bash
# 检查关键组件 / Check key components
git --version
gcc --version
```

**期望输出 / Expected Output:**
```
git version 2.34.1
gcc (Ubuntu 11.4.0) 11.4.0
```

---

## 🚀 下一步 / Next Steps

根据你的情况选择 / Choose based on your situation:

- **[🎮 安装NVIDIA驱动](02-nvidia-drivers.md)** - 如果你有NVIDIA GPU（推荐）/ If you have NVIDIA GPU (recommended)
- **[🐍 配置Python环境](04-python-setup.md)** - 如果你已有GPU驱动，可直接配置Python / If you already have GPU drivers, go directly to Python setup
