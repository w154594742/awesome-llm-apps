# 🎙️ 客户支持语音代理

一个由OpenAI SDK驱动的客户支持代理应用程序，使用OpenAI的GPT-4o和TTS功能为您的知识库问题提供语音驱动的响应。该系统使用Firecrawl爬取文档网站，将内容处理成可搜索的知识库并存储在Qdrant中，为用户查询提供文本和语音响应。

## 功能特性

- 知识库创建

  - 使用Firecrawl爬取文档网站
  - 使用Qdrant向量数据库存储和索引内容
  - 使用FastEmbed生成嵌入以实现语义搜索功能
- **AI代理团队**
  - **文档处理器**：分析文档内容并为用户查询生成清晰、简洁的响应
  - **TTS代理**：将文本响应转换为具有适当节奏和重点的自然语音
  - **语音定制**：支持多种OpenAI TTS语音：
    - alloy、ash、ballad、coral、echo、fable、onyx、nova、sage、shimmer、verse

- **交互式界面**
  - 带侧边栏配置的清洁Streamlit UI
  - 实时文档搜索和响应生成
  - 内置音频播放器，支持下载功能
  - 系统初始化和查询处理的进度指示器

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd awesome-llm-apps/ai_agent_tutorials/ai_voice_agent_openaisdk
   
   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥**
   - 从[OpenAI平台](https://platform.openai.com)获取OpenAI API密钥
   - 从[Qdrant云](https://cloud.qdrant.io)获取Qdrant API密钥和URL
   - 获取Firecrawl API密钥用于文档爬取

3. **运行应用程序**
   ```bash
   streamlit run ai_voice_agent_docs.py
   ```

4. **使用界面**
   - 在侧边栏中输入API凭据
   - 输入您想要了解的文档URL
   - 从下拉菜单中选择您偏好的语音
   - 点击"初始化系统"处理文档
   - 提问并接收文本和语音响应

## 详细功能

- **知识库创建**
  - 从您的文档构建可搜索的知识库
  - 保留文档结构和元数据
  - 支持多页面爬取（默认配置限制为5页）

- **向量搜索**
  - 使用FastEmbed生成嵌入
  - 语义搜索功能查找相关内容
  - 使用Qdrant进行高效文档检索

- **语音生成**
  - 使用OpenAI的TTS模型生成高质量文本转语音
  - 多种语音选项可供定制
  - 具有适当节奏和重点的自然语音模式
