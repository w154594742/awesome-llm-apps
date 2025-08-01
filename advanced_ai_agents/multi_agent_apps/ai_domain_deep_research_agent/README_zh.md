# 🔍 AI领域深度研究代理

一个使用Agno代理框架、Together AI的Qwen模型和Composio工具构建的高级AI研究代理。此代理通过生成研究问题、通过多个搜索引擎查找答案，并编译带有Google Docs集成的专业报告，帮助用户对任何主题进行全面研究。

## 功能特性

- 🧠 **智能问题生成**：

  - 自动生成关于您主题的5个具体研究问题
  - 根据您指定的领域定制问题
  - 专注于创建是/否问题以获得清晰的研究结果
- 🔎 **多源研究**：

  - 使用Tavily搜索获得全面的网络结果
  - 利用Perplexity AI进行更深入的分析
  - 结合多个来源进行彻底研究
- 📊 **专业报告生成**：

  - 将研究发现编译成麦肯锡风格的报告
  - 使用执行摘要、分析和结论构建内容
  - 创建包含完整报告的Google文档
- 🖥️ **用户友好界面**：

  - 具有直观工作流程的清洁Streamlit UI
  - 实时进度跟踪
  - 可展开部分以查看详细结果

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/multi_agent_apps/ai_domain_deep_research_agent
   
   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥和集成**
   
   您需要以下API密钥：
   ```bash
   export TOGETHER_API_KEY="your-together-api-key"
   export TAVILY_API_KEY="your-tavily-api-key"
   export PERPLEXITY_API_KEY="your-perplexity-api-key"
   export COMPOSIO_API_KEY="your-composio-api-key"
   ```

3. **设置Google Docs集成**
   ```bash
   # 设置Composio Google Docs集成
   composio add googledocs
   ```

4. **运行应用程序**
   ```bash
   streamlit run ai_domain_deep_research_agent.py
   ```

5. **使用应用程序**
   - 输入您想要研究的主题
   - 指定研究领域或上下文
   - 让AI代理生成研究问题并进行深度分析
   - 查看在Google Docs中生成的专业研究报告

## 工作原理

1. **主题分析**：代理分析研究主题并生成相关问题
2. **多源搜索**：使用多个搜索引擎收集信息
3. **深度分析**：对收集的信息进行深入分析和验证
4. **报告编译**：将发现整理成结构化的专业报告
5. **文档创建**：在Google Docs中生成最终报告

## 主要功能

- **自动化研究**：无需手动搜索和整理信息
- **多角度分析**：从不同角度探索研究主题
- **专业报告**：生成高质量的研究报告
- **云端协作**：通过Google Docs实现团队协作
- **实时跟踪**：监控研究进度和状态

## 应用场景

- 学术研究项目
- 市场调研分析
- 竞争对手研究
- 行业趋势分析
- 政策研究
- 技术评估

## 系统要求

- Python 3.8+
- Together AI API密钥
- Tavily API密钥
- Perplexity API密钥
- Composio API密钥
- Google账户（用于Docs集成）

## 注意事项

- 确保所有API密钥都有效且有足够的配额
- Google Docs集成需要适当的权限设置
- 研究质量取决于可用的网络资源
- 大型研究项目可能需要更长时间处理
