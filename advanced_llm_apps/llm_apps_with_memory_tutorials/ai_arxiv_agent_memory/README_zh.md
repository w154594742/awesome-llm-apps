## 📚 带记忆的AI研究代理
这个Streamlit应用实现了一个AI驱动的研究助手，帮助用户在arXiv上搜索学术论文，同时保持对用户兴趣和过往交互的记忆。它利用OpenAI的GPT-4o-mini模型处理搜索结果，使用MultiOn进行网页浏览，使用Mem0和Qdrant维护用户上下文。

### 功能特性

- 查询arXiv论文的搜索界面
- AI驱动的搜索结果处理，提高可读性
- 持久记忆用户兴趣和过往搜索
- 利用OpenAI的GPT-4o-mini模型进行智能处理
- 使用Mem0和Qdrant实现记忆存储和检索

### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/llm_apps_with_memory_tutorials/ai_arxiv_agent_memory
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
streamlit run ai_arxiv_agent_memory.py
```
