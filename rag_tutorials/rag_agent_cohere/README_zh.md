# 使用Cohere ⌘R的RAG代理 

一个使用Cohere的新模型Command-r7b-12-2024、Qdrant进行向量存储、Langchain进行RAG和LangGraph进行编排构建的RAG代理系统。该应用程序允许用户上传文档、询问相关问题，并在需要时通过回退到网络搜索获得AI驱动的响应。

## 功能特性

- **文档处理**
  - PDF文档上传和处理
  - 自动文本分块和嵌入
  - 在Qdrant云中进行向量存储

- **智能查询**
  - 基于RAG的文档检索
  - 带阈值过滤的相似性搜索
  - 当找不到相关文档时自动回退到网络搜索
  - 答案的来源归属

- **高级功能**
  - DuckDuckGo网络搜索集成
  - 用于网络研究的LangGraph代理
  - 上下文感知响应生成
  - 长答案摘要

- **模型特定功能**
  - Command-r7b-12-2024模型用于聊天和RAG
  - cohere embed-english-v3.0模型用于嵌入
  - 来自langgraph的create_react_agent函数
  - DuckDuckGoSearchRun工具用于网络搜索

## 系统要求
