## 🦙 用30行Python代码微调Llama 3.2

这个脚本演示了如何使用[Unsloth](https://unsloth.ai/)库微调Llama 3.2模型，使过程变得简单快速。您可以运行此示例在Google Colab中免费微调Llama 3.1 1B和3B模型。

### 功能特性

- 使用Unsloth库微调Llama 3.2模型
- 实现低秩适应（LoRA）以进行高效微调
- 使用FineTome-100k数据集进行训练
- 可配置不同的模型大小（1B和3B）

### 安装

1. 克隆仓库：

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/llm_finetuning_tutorials/llama3.2_finetuning
```

2. 安装所需依赖：

```bash
pip install -r requirements.txt
```

## 使用方法

1. 在Google Colab或您偏好的Python环境中打开脚本。

2. 运行微调脚本：

```bash
python llama3.2_finetuning.py
```

3. 脚本将：
   - 加载预训练的Llama 3.2模型
   - 应用LoRA适配器进行高效微调
   - 在FineTome-100k数据集上训练模型
   - 保存微调后的模型

### 配置选项

您可以修改脚本中的以下参数：

- **模型大小**：选择1B或3B版本
- **训练步数**：调整训练迭代次数
- **学习率**：优化训练性能
- **LoRA参数**：自定义适配器配置

### 系统要求

- Python 3.8+
- CUDA兼容的GPU（推荐）
- 至少8GB RAM
- Google Colab（免费选项）

### 注意事项

- 此脚本针对教育和实验目的进行了优化
- 对于生产使用，请考虑更大的数据集和更长的训练时间
- 确保您有足够的计算资源用于所选的模型大小
