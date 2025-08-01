## 🗃️ 具有网络访问的AI RAG代理 
该脚本演示了如何仅用15行Python代码使用GPT-4o构建具有网络访问功能的检索增强生成（RAG）代理。该代理使用PDF知识库，并具有使用DuckDuckGo搜索网络的能力。

### 功能特性

- 使用GPT-4o创建RAG代理
- 集成基于PDF的知识库
- 使用LanceDB作为向量数据库进行高效相似性搜索
- 通过DuckDuckGo包含网络搜索功能
- 提供游乐场界面便于交互

### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/rag_tutorials/agentic_rag
```

2. 安装所需依赖：

```bash
pip install -r requirements.txt
```

3. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)（或您选择的LLM提供商）并获取您的API密钥。
- 将您的OpenAI API密钥设置为环境变量：
```bash
export OPENAI_API_KEY='your-api-key-here'
```

4. 运行AI RAG代理 
```bash
python3 rag_agent.py
```
5. 打开您的网络浏览器并导航到控制台输出中提供的URL，通过游乐场界面与RAG代理交互。

### 工作原理？

1. **知识库创建：** 脚本从在线托管的PDF文件创建知识库。
2. **向量数据库设置：** LanceDB用作向量数据库，在知识库内进行高效相似性搜索。
3. **代理配置：** 使用GPT-4o作为底层模型创建AI代理，配备PDF知识库和DuckDuckGo搜索工具。
4. **游乐场设置：** 设置游乐场界面以便与RAG代理轻松交互。
