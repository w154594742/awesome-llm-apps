# 📠 带数据库路由的RAG代理

一个Streamlit应用程序，演示了带有智能查询路由的RAG代理的高级实现。该系统结合多个专业数据库和智能回退机制，确保对用户查询提供可靠和准确的响应。

## 功能特性

- **文档上传**：用户可以上传与特定公司相关的多个PDF文档。这些文档被处理并存储在三个数据库之一：产品信息、客户支持和FAQ，或财务信息。
  
- **自然语言查询**：用户可以用自然语言提问。系统使用agno代理作为路由器自动将查询路由到最相关的数据库。

- **RAG编排**：利用Langchain编排检索增强生成过程，确保检索和呈现给用户最相关的信息。

- **回退机制**：如果在数据库中找不到相关文档，则使用带有DuckDuckGo搜索工具的LangGraph代理执行网络研究并提供答案。

## 如何运行？

1. **克隆仓库**：
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd rag_tutorials/rag_database_routing
   ```

2. **安装依赖**：
   ```bash
   pip install -r requirements.txt
   ```

3. **运行应用程序**：
   ```bash
   streamlit run rag_database_routing.py
