# 🤔 使用Gemini Flash Thinking的代理式RAG

一个使用新的Gemini 2.0 Flash Thinking模型和gemini-exp-1206、Qdrant进行向量存储，以及Agno（之前的phidata）进行代理编排构建的RAG代理系统。该应用程序具有智能查询重写、文档处理和网络搜索回退功能，提供全面的AI驱动响应。

## 功能特性

- **文档处理**
  - PDF文档上传和处理
  - 网页内容提取
  - 自动文本分块和嵌入
  - 在Qdrant云中进行向量存储

- **智能查询**
  - 查询重写以获得更好的检索
  - 基于RAG的文档检索
  - 带阈值过滤的相似性搜索
  - 自动回退到网络搜索
  - 答案的来源归属

- **高级功能**
  - Exa AI网络搜索集成
  - 网络搜索的自定义域过滤
  - 上下文感知响应生成
  - 聊天历史管理
  - 查询重新表述代理

- **模型特定功能**
  - Gemini Thinking 2.0 Flash用于聊天和推理
  - Gemini嵌入模型用于向量嵌入
  - Agno代理框架用于编排
  - 基于Streamlit的交互式界面

## 系统要求

### 1. Google API密钥
1. 访问[Google AI Studio](https://aistudio.google.com/apikey)
2. 注册或登录您的账户
3. 创建新的API密钥

### 2. Qdrant云设置
