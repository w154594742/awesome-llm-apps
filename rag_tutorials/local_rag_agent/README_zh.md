## 🦙 使用Llama 3.2的本地RAG代理
该应用程序通过Ollama使用Llama 3.2实现检索增强生成（RAG）系统，使用Qdrant作为向量数据库。


### 功能特性
- 完全本地的RAG实现
- 通过Ollama由Llama 3.2驱动
- 使用Qdrant进行向量搜索
- 交互式游乐场界面
- 无外部API依赖

### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
```

2. 安装所需依赖：

```bash
cd awesome-llm-apps/rag_tutorials/local_rag_agent
pip install -r requirements.txt
```

3. 本地安装并启动[Qdrant](https://qdrant.tech/)向量数据库

```bash
docker pull qdrant/qdrant
docker run -p 6333:6333 qdrant/qdrant
