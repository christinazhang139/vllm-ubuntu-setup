# 🐍 Python环境配置 / Python Environment Setup

[← 上一步: CUDA安装](03-cuda-installation.md) | [下一步: PyTorch安装 →](05-pytorch-installation.md)

[← Previous: CUDA Installation](03-cuda-installation.md) | [Next: PyTorch Installation →](05-pytorch-installation.md)

> 🎯 检查和安装vLLM所需的Python版本。
> 
> 🎯 Check and install the Python version required for vLLM.

---

## 🔍 Python版本要求 / Python Version Requirements

| 组件 / Component | 最低版本 / Minimum | 推荐版本 / Recommended | 状态 / Status |
|------------------|-------------------|----------------------|---------------|
| **Python** | 3.8+ | 3.11.x | 🟢 最佳性能 / Best performance |
| **pip** | 20.0+ | 最新版 / Latest | 🟢 自动包含 / Auto included |

---

## ✅ 检查当前Python版本 / Check Current Python Version

```bash
# 检查Python版本 / Check Python version
python3 --version

# 检查pip版本 / Check pip version  
pip3 --version
```

**期望输出 / Expected Output:**
```bash
Python 3.11.x (推荐) / Python 3.11.x (recommended)
# 或 or
Python 3.10.x (可用) / Python 3.10.x (usable)
# 或 or  
Python 3.9.x (可用) / Python 3.9.x (usable)
```

---

## 🔧 版本检查结果 / Version Check Results

### ✅ 版本满足要求（Python 3.8+）/ Version meets requirements (Python 3.8+)
```bash
# 如果版本 >= 3.8，可以继续安装 / If version >= 3.8, you can proceed
echo "✅ Python版本满足要求，可以继续下一步 / Python version meets requirements, proceed to next step"
```

---

## 🚀 下一步 / Next Steps

Python环境确认完成后 / After Python environment confirmation is complete:

**[🔥 安装PyTorch / Install PyTorch →](05-pytorch-installation.md)**

> 💡 **提醒**: 下一步将创建虚拟环境并安装PyTorch，确保选择与你的CUDA版本匹配的PyTorch版本。
> 
> 💡 **Reminder**: The next step will create a virtual environment and install PyTorch. Make sure to choose a PyTorch version matching your CUDA version.
