# 🧲 AI竞争对手情报代理团队

AI竞争对手情报代理团队是一个强大的竞争对手分析工具，由Firecrawl和Agno的AI代理框架驱动。此应用帮助企业通过从竞争对手网站提取结构化数据并使用AI生成可操作的洞察来分析他们的竞争对手。

## 功能特性

- **多代理系统**
    - **Firecrawl代理**：专门爬取和总结竞争对手网站
    - **分析代理**：生成详细的竞争分析报告
    - **比较代理**：创建竞争对手之间的结构化比较

- **竞争对手发现**：
  - 使用Exa AI的URL匹配查找相似公司
  - 基于业务描述发现竞争对手
  - 自动提取相关竞争对手URL

- **全面分析**：
  - 提供结构化分析报告，包括：
    - 市场空白和机会
    - 竞争对手弱点
    - 推荐功能
    - 定价策略
    - 增长机会
    - 可操作的建议

- **交互式分析**：用户可以输入公司URL或描述进行分析

## 系统要求

应用程序需要以下Python库：

```bash
pip install -r requirements.txt
```

## API密钥设置

您需要以下API密钥：

1. **OpenAI API密钥**：从[OpenAI平台](https://platform.openai.com/)获取
2. **Firecrawl API密钥**：从[Firecrawl](https://firecrawl.dev/)获取
3. **Exa API密钥**：从[Exa AI](https://exa.ai/)获取

## 如何运行

1. **克隆仓库**：
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/multi_agent_apps/agent_teams/ai_competitor_intelligence_agent_team
   ```

2. **安装依赖**：
   ```bash
   pip install -r requirements.txt
   ```

3. **运行应用程序**：
   ```bash
   streamlit run ai_competitor_intelligence_agent_team.py
   ```

4. **使用应用程序**：
   - 在侧边栏中输入您的API密钥
   - 输入您的公司URL或业务描述
   - 点击"分析竞争对手"
   - 查看详细的竞争分析报告

## 工作原理

1. **输入处理**：应用程序接受公司URL或业务描述
2. **竞争对手发现**：使用Exa AI查找相似的竞争对手
3. **数据提取**：Firecrawl代理爬取竞争对手网站
4. **分析生成**：分析代理创建详细的竞争报告
5. **比较创建**：比较代理生成结构化比较
6. **洞察交付**：向用户呈现可操作的建议
