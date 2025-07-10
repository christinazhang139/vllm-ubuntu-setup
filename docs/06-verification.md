# ✅ 验证测试 / Verification

[← 上一步: vLLM安装](05-vllm-installation.md)

[← Previous: vLLM Installation](05-vllm-installation.md)

> 🎯 验证vLLM环境是否正确安装和配置。
> 
> 🎯 Verify that the vLLM environment is correctly installed and configured.

---

## ⚡ 环境验证 / Environment Verification

```bash
# 激活环境 / Activate environment
cd ~/vllm-learning
source vllm-env/bin/activate

# 一键验证所有组件 / One-command verification of all components
python -c "
import torch, vllm
print(f'✅ PyTorch: {torch.__version__} (CUDA: {torch.cuda.is_available()})')
print(f'✅ vLLM: {vllm.__version__}')
print(f'✅ GPU: {torch.cuda.get_device_name(0) if torch.cuda.is_available() else \"CPU only\"}')
print('🎉 vLLM environment setup complete!')
"
```

**期望输出 / Expected Output:**
```
✅ PyTorch: 2.1.0+cu121 (CUDA: True)
✅ vLLM: 0.2.7
✅ GPU: NVIDIA GeForce RTX 4090
🎉 vLLM environment setup complete!
```

---

## 🚀 开始使用 / Start Using

环境验证成功后，你可以 / After successful environment verification, you can:

- 🔬 **运行vLLM实验** / **Run vLLM experiments**
- 📚 **学习vLLM用法** / **Learn vLLM usage**
- 🎯 **加载和测试模型** / **Load and test models**

> 💡 **提醒**: 每次使用前记得激活环境：`source ~/vllm-learning/vllm-env/bin/activate`
> 
> 💡 **Reminder**: Remember to activate the environment before each use: `source ~/vllm-learning/vllm-env/bin/activate`
