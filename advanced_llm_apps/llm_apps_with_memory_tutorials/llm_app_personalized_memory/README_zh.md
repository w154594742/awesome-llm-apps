## 🧠 带记忆的LLM应用
这个Streamlit应用是一个AI驱动的聊天机器人，使用OpenAI的GPT-4o模型和持久记忆功能。它允许用户与AI进行对话，同时在多次交互中保持上下文。

### 功能特性

- 利用OpenAI的GPT-4o模型生成响应
- 使用Mem0和Qdrant向量存储实现持久记忆
- 允许用户查看他们的对话历史
- 使用Streamlit提供用户友好的界面


### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/llm_apps_with_memory_tutorials/llm_app_personalized_memory
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

4. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)并获取您的API密钥。

5. 运行Streamlit应用
```bash
streamlit run llm_app_personalized_memory.py
```
