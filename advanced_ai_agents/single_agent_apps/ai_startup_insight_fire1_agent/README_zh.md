# 🔥 使用Firecrawl FIRE-1代理的AI创业洞察

一个使用Firecrawl的FIRE-1代理 + extract v1端点和Agno代理框架构建的高级网络提取和分析工具，可以即时获取新创业公司的详细信息！此应用程序自动从创业公司网站提取结构化数据并提供AI驱动的商业分析，使得无需手动研究即可轻松收集公司洞察。

## 功能特性

- 🌐 **智能网络提取**：

  - 从任何公司网站提取结构化数据
  - 自动识别公司信息、使命和产品功能
  - 按顺序处理多个网站
- 🔍 **高级网络导航**：

  - 与按钮、链接和动态元素交互
  - 处理分页和多步骤流程
  - 访问多个页面的信息
- 🧠 **AI商业分析**：

  - 生成提取的公司数据的深刻摘要
  - 识别独特的价值主张和市场机会
  - 提供可操作的商业智能
- 📊 **结构化数据输出**：

  - 以一致的JSON模式组织信息
  - 提取公司名称、描述、使命和产品功能
  - 标准化输出以供进一步处理
- 🎯 **交互式UI**：

  - 用户友好的Streamlit界面
  - 并行处理多个URL

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/single_agent_apps/ai_startup_insight_fire1_agent
   
   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥**
   
   您需要以下API密钥：
   ```bash
   export FIRECRAWL_API_KEY="your-firecrawl-api-key"
   export OPENAI_API_KEY="your-openai-api-key"
   ```

3. **运行应用程序**
   ```bash
   streamlit run ai_startup_insight_fire1_agent.py
   ```

4. **使用应用程序**
   - 输入创业公司的网站URL
   - 让FIRE-1代理提取和分析数据
   - 查看结构化的公司洞察和分析

## 工作原理

1. **URL输入**：用户提供创业公司网站URL
2. **智能提取**：FIRE-1代理导航网站并提取关键信息
3. **数据结构化**：将提取的信息组织成标准化格式
4. **AI分析**：生成商业洞察和市场分析
5. **结果展示**：以用户友好的格式呈现分析结果

## 主要功能

- **自动化数据提取**：无需手动浏览网站
- **智能内容识别**：自动识别关键商业信息
- **结构化输出**：一致的数据格式便于分析
- **商业洞察**：AI驱动的市场和竞争分析
- **批量处理**：同时分析多个创业公司

## 应用场景

- 投资者尽职调查
- 竞争对手分析
- 市场研究
- 创业公司发现
- 商业智能收集
- 投资机会评估

## 系统要求

- Python 3.8+
- Firecrawl API密钥
- OpenAI API密钥
- 稳定的互联网连接

## 注意事项

- 提取质量取决于网站结构和内容
- 某些网站可能有反爬虫保护
- API使用可能产生费用
- 遵守网站的使用条款和robots.txt
