# 👀 混合搜索RAG应用 

一个强大的文档问答应用程序，利用混合搜索（RAG）和Claude的高级语言能力提供全面的答案。使用RAGLite进行强大的文档处理和检索，使用Streamlit提供直观的聊天界面，该系统无缝结合文档特定知识和Claude的通用智能，提供准确和上下文相关的响应。

## 功能特性

- **混合搜索问答**
    - 基于RAG的文档特定查询答案
    - 对一般知识问题回退到Claude

- **文档处理**：
  - PDF文档上传和处理
  - 自动文本分块和嵌入
  - 结合语义和关键词匹配的混合搜索
  - 重新排序以获得更好的上下文选择

- **多模型集成**：
  - Claude用于文本生成 - 使用Claude 3 Opus测试
  - OpenAI用于嵌入 - 使用text-embedding-3-large测试
  - Cohere用于重新排序 - 使用Cohere 3.5重新排序器测试

## 系统要求

您需要以下API密钥和数据库设置：

1. **数据库**：在[Neon](https://neon.tech)创建免费的PostgreSQL数据库：
   - 在Neon注册/登录
   - 创建新项目
   - 复制连接字符串（格式如：`postgresql://user:pass@ep-xyz.region.aws.neon.tech/dbname`）
