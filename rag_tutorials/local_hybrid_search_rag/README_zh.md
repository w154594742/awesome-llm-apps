# 🖥️ 本地混合搜索RAG应用

一个强大的文档问答应用程序，利用混合搜索（RAG）和本地LLM提供全面答案。使用RAGLite进行强大的文档处理和检索，使用Streamlit提供直观的聊天界面，该系统结合文档特定知识和本地LLM功能，提供准确和上下文相关的响应。

## 演示：


https://github.com/user-attachments/assets/375da089-1ab9-4bf4-b6f3-733f44e47403


## 快速开始

对于即时测试，使用这些经过测试的模型配置：
```bash
# LLM模型
bartowski/Llama-3.2-3B-Instruct-GGUF/Llama-3.2-3B-Instruct-Q4_K_M.gguf@4096

# 嵌入器模型
lm-kit/bge-m3-gguf/bge-m3-Q4_K_M.gguf@1024
```
这些模型在性能和资源使用之间提供了良好的平衡，并且已经验证即使在配备8GB RAM的MacBook Air M2上也能很好地协同工作。

## 功能特性

- **本地LLM集成**：
  - 使用llama-cpp-python模型进行本地推理
  - 支持各种量化格式（推荐Q4_K_M）
  - 可配置的上下文窗口大小

- **文档处理**：
