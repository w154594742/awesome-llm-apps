## 💻 本地Llama-3.1与RAG
Streamlit应用程序，允许您使用本地Llama-3.1和检索增强生成（RAG）与任何网页聊天。该应用程序完全在您的计算机上运行，使其100%免费且无需互联网连接。


### 功能特性
- 输入网页URL
- 询问关于网页内容的问题
- 使用RAG和在您计算机上本地运行的Llama-3.1模型获得准确答案

### 如何开始？

1. 克隆GitHub仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/rag_tutorials/llama3.1_local_rag
```
2. 安装所需依赖：

```bash
pip install -r requirements.txt
```
3. 运行Streamlit应用
```bash
streamlit run llama3.1_local_rag.py
```

### 工作原理？

- 应用程序使用WebBaseLoader加载网页数据，并使用RecursiveCharacterTextSplitter将其分割成块。
