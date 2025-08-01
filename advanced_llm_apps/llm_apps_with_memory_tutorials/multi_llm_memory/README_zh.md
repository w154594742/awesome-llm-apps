## 🧠 带共享记忆的多LLM应用
这个Streamlit应用演示了一个带有共享记忆层的多LLM系统，允许用户与不同的语言模型交互，同时在会话间保持对话历史和上下文。

### 功能特性

- 支持多种LLM：
    - OpenAI的GPT-4o
    - Anthropic的Claude 3.5 Sonnet

- 使用Qdrant向量存储的持久记忆
- 用户特定的对话历史
- 用于上下文响应的记忆检索
- 带LLM选择的用户友好界面

### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/llm_apps_with_memory_tutorials/multi_llm_memory
```

2. 安装所需依赖：

```bash
pip install -r requirements.txt
```

3. 确保Qdrant正在运行：
应用期望Qdrant在localhost:6333上运行。如果您的设置不同，请调整代码中的配置。

```bash
docker pull qdrant/qdrant
docker run -p 6333:6333 qdrant/qdrant
```

4. 获取您的API密钥

- 获取[OpenAI API密钥](https://platform.openai.com/)
- 获取[Anthropic API密钥](https://console.anthropic.com/)

5. 运行Streamlit应用
```bash
streamlit run multi_llm_memory.py
```
