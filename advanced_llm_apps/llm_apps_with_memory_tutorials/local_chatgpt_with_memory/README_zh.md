## 🧠 使用Llama 3.1的本地ChatGPT，带个人记忆
这个Streamlit应用实现了一个完全本地的类ChatGPT体验，使用Llama 3.1，为每个用户提供个性化记忆存储。所有组件，包括语言模型、嵌入和向量存储，都在本地运行，无需外部API密钥。

### 功能特性
- 完全本地实现，无外部API依赖
- 通过Ollama由Llama 3.1驱动
- 每个用户的个人记忆空间
- 使用Nomic Embed进行本地嵌入生成
- 使用Qdrant进行向量存储

### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/llm_apps_with_memory_tutorials/local_chatgpt_with_memory
```

2. 安装所需依赖：

```bash
cd awesome-llm-apps/rag_tutorials/local_rag_agent
pip install -r requirements.txt
```

3. 本地安装并启动[Qdrant](https://qdrant.tech/documentation/guides/installation/)向量数据库

```bash
docker pull qdrant/qdrant
docker run -p 6333:6333 qdrant/qdrant
```

4. 安装并启动Ollama

- 从[Ollama官网](https://ollama.ai/)下载并安装Ollama
- 拉取Llama 3.1模型：
```bash
ollama pull llama3.1
```

5. 运行Streamlit应用
```bash
streamlit run local_chatgpt_with_memory.py
```
