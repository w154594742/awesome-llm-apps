## 📰 多代理AI新闻助手
这个Streamlit应用程序使用多个专业AI代理实现了一个复杂的新闻处理管道，用于搜索、综合和总结新闻文章。它通过Ollama利用Llama 3.2模型和DuckDuckGo搜索来提供全面的新闻分析。


### 功能特性
- 具有专业角色的多代理架构：
    - 新闻搜索器：查找最新新闻文章
    - 新闻综合器：分析和组合信息
    - 新闻摘要器：创建简洁、专业的摘要

- 使用DuckDuckGo进行实时新闻搜索
- AP/路透社风格的摘要生成
- 用户友好的Streamlit界面


### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/your-username/ai-news-processor.git
cd awesome-llm-apps/ai_agent_tutorials/local_news_agent_openai_swarm
```

2. 安装所需依赖：

```bash
pip install -r requirements.txt
```

3. 使用Ollama拉取并运行Llama 3.2：

```bash
# 拉取模型
ollama pull llama3.2

# 验证安装
ollama list

# 运行模型（可选测试）
ollama run llama3.2
```

4. 创建包含您配置的.env文件：
```bash
OPENAI_BASE_URL=http://localhost:11434/v1
OPENAI_API_KEY=fake-key 
```
5. 运行Streamlit应用
```bash
streamlit run news_agent.py
```
