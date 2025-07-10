# 📦 vLLM Installation

[← Previous: Python Environment Setup](04-python-setup.md) | [Next: Verification →](06-verification.md)

> 🎯 Create virtual environment, install PyTorch and vLLM, complete the entire vLLM setup.

---

## 🔍 Version Selection

### 💡 CUDA and PyTorch Relationship

PyTorch needs to match your CUDA version to properly use GPU:

- **🔗 Version Binding**: PyTorch is compiled with specific CUDA versions
- **❌ Mismatch Consequences**: GPU unavailable or runtime errors
- **✅ Matching Benefits**: Optimal performance and stability

### 📋 Version Correspondence Table

Choose PyTorch version based on your CUDA version:

| CUDA Version | PyTorch Version | Compatible GPU |
|--------------|----------------|----------------|
| **CUDA 12.1** | **cu121** | RTX 4090, RTX 4080, RTX 4070 |
| **CUDA 11.8** | **cu118** | RTX 3090, RTX 3080, RTX 3070, RTX 3060 |

> 💡 **Check CUDA version**: Run `nvidia-smi` and look at "CUDA Version" in the top right

> ⚠️ **Important**: You must install PyTorch matching your CUDA version, otherwise vLLM cannot use GPU acceleration

---

## 🏠 Create Virtual Environment

```bash
# Create project directory
mkdir -p ~/vllm-learning
cd ~/vllm-learning

# Create virtual environment
python3 -m venv vllm-env

# Activate virtual environment
source vllm-env/bin/activate

# Upgrade pip
pip install --upgrade pip
```

---

## 🔥 Install PyTorch

### 🚀 CUDA 12.1 Users
```bash
# Install PyTorch (CUDA 12.1)
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```

### 🚀 CUDA 11.8 Users
```bash
# Install PyTorch (CUDA 11.8)
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

## 📦 Install vLLM

```bash
# Install vLLM and necessary dependencies
pip install vllm transformers accelerate
```

---

## ✅ Verify Installation

```bash
# Verify PyTorch
python -c "import torch; print(f'PyTorch version: {torch.__version__}'); print(f'CUDA available: {torch.cuda.is_available()}')"

# Verify vLLM
python -c "import vllm; print(f'vLLM version: {vllm.__version__}')"
```

**Expected Output:**
```
PyTorch version: 2.1.0+cu121
CUDA available: True
vLLM version: 0.2.7
```

---

## 🔄 Environment Management

```bash
# Activate environment before each use
cd ~/vllm-learning
source vllm-env/bin/activate

# Deactivate virtual environment
deactivate
```

---

## 🚀 Next Steps

After vLLM installation is complete:

**[✅ Verification →](06-verification.md)**

> 💡 **Reminder**: You need to activate the virtual environment every time: `source ~/vllm-learning/vllm-env/bin/activate`
