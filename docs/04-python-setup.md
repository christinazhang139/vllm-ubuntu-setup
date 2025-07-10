# 🐍 Python Environment Setup

[← Previous: CUDA Installation](03-cuda-installation.md) | [Next: vLLM Installation →](05-vllm-installation.md)

> 🎯 Check and install the Python version required for vLLM.

---

## 🔍 Python Version Requirements

| Component | Minimum | Recommended | Status |
|-----------|---------|-------------|--------|
| **Python** | 3.8+ | 3.11.x | 🟢 Best performance |
| **pip** | 20.0+ | Latest | 🟢 Auto included |

---

## ✅ Check Current Python Version

```bash
# Check Python version
python3 --version

# Check pip version
pip3 --version
```

**Expected Output:**
```bash
Python 3.11.x (recommended)
# or
Python 3.10.x (usable)
# or  
Python 3.9.x (usable)
```

---

## 🔧 Version Check Results

### ✅ Version meets requirements (Python 3.8+)
```bash
# If version >= 3.8, you can proceed
echo "✅ Python version meets requirements, proceed to next step"
```

---

## 🚀 Next Steps

After Python environment confirmation is complete:

**[📦 vLLM Installation →](05-vllm-installation.md)**

> 💡 **Reminder**: The next step will create a virtual environment and install PyTorch and vLLM. Make sure to choose a PyTorch version matching your CUDA version.
