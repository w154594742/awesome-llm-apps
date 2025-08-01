# 🔄 纠错RAG代理
一个复杂的检索增强生成（RAG）系统，使用LangGraph实现纠错多阶段工作流。该系统结合文档检索、相关性评分、查询转换和网络搜索，提供全面准确的响应。

## 功能特性

- **智能文档检索**：使用Qdrant向量存储进行高效文档检索
- **文档相关性评分**：使用Claude 3.5 sonnet评估文档相关性
- **查询转换**：在需要时通过优化查询来改善搜索结果
- **网络搜索回退**：当本地文档不足时使用Tavily API进行网络搜索
- **多模型方法**：结合OpenAI嵌入和Claude 3.5 sonnet处理不同任务
- **交互式UI**：使用Streamlit构建，便于文档上传和查询

## 如何运行？

1. **克隆仓库**：
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd rag_tutorials/corrective_rag
   ```

2. **安装依赖**：
   ```bash
   pip install -r requirements.txt
   ```

3. **设置API密钥**：
   您需要获取以下API密钥：
   - [OpenAI API密钥](https://platform.openai.com/api-keys)（用于嵌入）
   - [Anthropic API密钥](https://console.anthropic.com/settings/keys)（用于Claude 3.5 sonnet作为LLM）
   - [Tavily API密钥](https://app.tavily.com/home)（用于网络搜索）
   - Qdrant云设置
      1. 访问[Qdrant云](https://cloud.qdrant.io/)
      2. 创建账户或登录
      3. 创建新集群
      4. 获取您的凭据：
         - Qdrant API密钥：在API密钥部分找到
         - Qdrant URL：您的集群URL（格式：`https://xxx-xxx.aws.cloud.qdrant.io`）

4. **运行应用程序**：
   ```bash
