# 📦 vLLM安装 / vLLM Installation

[← 上一步: Python环境配置](04-python-setup.md) | [下一步: 验证测试 →](06-verification.md)

[← Previous: Python Environment Setup](04-python-setup.md) | [Next: Verification →](06-verification.md)

> 🎯 创建虚拟环境，安装PyTorch和vLLM，完成整个vLLM环境配置。
> 
> 🎯 Create virtual environment, install PyTorch and vLLM, complete the entire vLLM setup.

---

## 🔍 版本选择 / Version Selection

### 💡 CUDA和PyTorch的关系 / CUDA and PyTorch Relationship

PyTorch需要与你的CUDA版本匹配才能正确使用GPU / PyTorch needs to match your CUDA version to properly use GPU:

- **🔗 版本绑定** / **Version Binding**: PyTorch编译时绑定特定CUDA版本
- **❌ 不匹配后果** / **Mismatch Consequences**: GPU不可用或运行错误
- **✅ 匹配好处** / **Matching Benefits**: 最佳性能和稳定性

### 📋 版本对应表 / Version Correspondence Table

根据你的CUDA版本选择对应的PyTorch / Choose PyTorch version based on your CUDA version:

| CUDA版本 / CUDA Version | PyTorch版本 / PyTorch Version | 适用GPU / Compatible GPU |
|-------------------------|------------------------------|-------------------------|
| **CUDA 12.1** | **cu121** | RTX 4090, RTX 4080, RTX 4070 |
| **CUDA 11.8** | **cu118** | RTX 3090, RTX 3080, RTX 3070, RTX 3060 |

> 💡 **检查CUDA版本**: 运行 `nvidia-smi` 查看右上角的"CUDA Version"
> 
> 💡 **Check CUDA version**: Run `nvidia-smi` and look at "CUDA Version" in the top right

> ⚠️ **重要**: 必须安装与你的CUDA版本匹配的PyTorch，否则vLLM无法使用GPU加速
> 
> ⚠️ **Important**: You must install PyTorch matching your CUDA version, otherwise vLLM cannot use GPU acceleration

---

## 🏠 创建虚拟环境 / Create Virtual Environment

```bash
# 创建项目目录 / Create project directory
mkdir -p ~/vllm-learning
cd ~/vllm-learning

# 创建虚拟环境 / Create virtual environment
python3 -m venv vllm-env

# 激活虚拟环境 / Activate virtual environment
source vllm-env/bin/activate

# 升级pip / Upgrade pip
pip install --upgrade pip
```

---

## 🔥 安装PyTorch / Install PyTorch

### 🚀 CUDA 12.1用户 / CUDA 12.1 Users
```bash
# 安装PyTorch (CUDA 12.1) / Install PyTorch (CUDA 12.1)
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```

### 🚀 CUDA 11.8用户 / CUDA 11.8 Users
```bash
# 安装PyTorch (CUDA 11.8) / Install PyTorch (CUDA 11.8)
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

## 📦 安装vLLM / Install vLLM

```bash
# 安装vLLM和必要依赖 / Install vLLM and necessary dependencies
pip install vllm transformers accelerate
```

---

## ✅ 验证安装 / Verify Installation

```bash
# 验证PyTorch / Verify PyTorch
python -c "import torch; print(f'PyTorch version: {torch.__version__}'); print(f'CUDA available: {torch.cuda.is_available()}')"

# 验证vLLM / Verify vLLM
python -c "import vllm; print(f'vLLM version: {vllm.__version__}')"
```

**期望输出 / Expected Output:**
```
PyTorch version: 2.1.0+cu121
CUDA available: True
vLLM version: 0.2.7
```

---

## 🔄 环境管理 / Environment Management

```bash
# 每次使用前激活环境 / Activate environment before each use
cd ~/vllm-learning
source vllm-env/bin/activate

# 退出虚拟环境 / Deactivate virtual environment
deactivate
```

---

## 🚀 下一步 / Next Steps

vLLM安装完成后 / After vLLM installation is complete:

**[✅ 验证测试 / Verification →](06-verification.md)**

> 💡 **提醒**: 每次使用时都需要激活虚拟环境：`source ~/vllm-learning/vllm-env/bin/activate`
> 
> 💡 **Reminder**: You need to activate the virtual environment every time: `source ~/vllm-learning/vllm-env/bin/activate`
