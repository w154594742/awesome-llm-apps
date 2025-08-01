## 🗞️ AI记者代理 
这个Streamlit应用是一个使用OpenAI GPT-4o生成高质量文章的AI驱动记者代理。它自动化了研究、写作和编辑文章的过程，让您能够轻松地在任何主题上创建引人入胜的内容。

### 功能特性
- 搜索网络获取给定主题的相关信息
- 撰写结构良好、信息丰富且引人入胜的文章
- 编辑和完善生成的内容，以达到《纽约时报》的高标准

### 如何开始？

1. 克隆GitHub仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd advanced_ai_agents/single_agent_apps/ai_journalist_agent
```
2. 安装所需依赖：

```bash
pip install -r requirements.txt
```
3. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)（或您选择的LLM提供商）并获取您的API密钥。

4. 获取您的SerpAPI密钥

- 注册[SerpAPI账户](https://serpapi.com/)并获取您的API密钥。

5. 运行Streamlit应用
```bash
streamlit run ai_journalist_agent.py
```

### 工作原理？

1. **主题输入**：用户提供要撰写文章的主题
2. **研究阶段**：AI代理使用SerpAPI搜索相关信息和资源
3. **写作阶段**：基于研究结果生成结构化的文章草稿
4. **编辑阶段**：AI编辑器完善文章，确保质量和可读性
5. **输出交付**：呈现最终的高质量文章

### 主要功能

- **自动研究**：智能搜索和收集相关信息
- **专业写作**：生成符合新闻标准的文章
- **质量编辑**：自动编辑和改进内容质量
- **多主题支持**：能够处理各种主题和领域
- **实时生成**：快速生成高质量的新闻文章

### 应用场景

- 新闻文章撰写
- 博客内容创作
- 研究报告生成
- 内容营销文章
- 学术写作辅助
