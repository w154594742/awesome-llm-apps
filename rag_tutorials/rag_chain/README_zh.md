# PharmaQuery

## 概述
PharmaQuery是一个先进的制药洞察检索系统，旨在帮助用户从制药领域的研究论文和文档中获得有意义的洞察。

## 演示
https://github.com/user-attachments/assets/c12ee305-86fe-4f71-9219-57c7f438f291

## 功能特性
- **自然语言查询**：询问关于制药行业的复杂问题并获得简洁、准确的答案。
- **自定义数据库**：上传您自己的研究文档以增强检索系统的知识库。
- **相似性搜索**：使用AI嵌入为您的查询检索最相关的文档。
- **Streamlit界面**：用于查询和文档上传的用户友好界面。

## 使用的技术
- **编程语言**: [Python 3.10+](https://www.python.org/downloads/release/python-31011/)
- **框架**: [LangChain](https://www.langchain.com/)
- **数据库**: [ChromaDB](https://www.trychroma.com/)
- **模型**:
  - 嵌入: [Google Gemini API (embedding-001)](https://ai.google.dev/gemini-api/docs/embeddings)
  - 聊天: [Google Gemini API (gemini-1.5-pro)](https://ai.google.dev/gemini-api/docs/models/gemini#gemini-1.5-pro)
- **PDF处理**: [PyPDFLoader](https://python.langchain.com/docs/integrations/document_loaders/pypdfloader/)
- **文档分割器**: [SentenceTransformersTokenTextSplitter](https://python.langchain.com/api_reference/text_splitters/sentence_transformers/langchain_text_splitters.sentence_transformers.SentenceTransformersTokenTextSplitter.html)

## 系统要求
1. **安装依赖**:
   ```bash
   pip install -r requirements.txt
   ```
