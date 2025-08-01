## 🧳 带记忆的AI旅行代理
这个Streamlit应用实现了一个AI驱动的旅行助手，能够记住用户偏好和过往交互。它利用OpenAI的GPT-4o生成响应，使用Mem0和Qdrant维护对话历史。

### 功能特性
- 与AI旅行助手交互的基于聊天的界面
- 持久记忆用户偏好和过往对话
- 利用OpenAI的GPT-4o模型提供智能响应
- 使用Mem0和Qdrant实现记忆存储和检索
- 用户特定的对话历史和记忆查看

### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/llm_apps_with_memory_tutorials/ai_travel_agent_memory
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
streamlit run ai_travel_agent_memory.py
```
