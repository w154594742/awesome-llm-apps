## 📈 AI投资代理
这个Streamlit应用是一个使用Agno的AI代理框架构建的AI驱动投资代理，比较两只股票的表现并生成详细报告。通过使用GPT-4o和Yahoo Finance数据，此应用提供有价值的洞察，帮助您做出明智的投资决策。

### 功能特性
- 比较两只股票的表现
- 检索全面的公司信息
- 获取最新的公司新闻和分析师建议

### 如何开始？

1. 克隆GitHub仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd advanced_ai_agents/single_agent_apps/ai_investment_agent
```
2. 安装所需依赖：

```bash
pip install -r requirements.txt
```
3. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)（或您选择的LLM提供商）并获取您的API密钥。

4. 运行Streamlit应用
```bash
streamlit run investment_agent.py
```

### 工作原理？

1. **股票选择**：用户输入两只股票的代码进行比较
2. **数据收集**：应用从Yahoo Finance获取实时股票数据
3. **分析处理**：AI代理分析财务指标、价格趋势和公司信息
4. **报告生成**：生成详细的比较报告，包括投资建议
5. **洞察展示**：以用户友好的格式呈现分析结果

### 主要功能

- **股票比较**：并排比较两只股票的关键指标
- **财务分析**：深入分析财务健康状况和表现
- **新闻集成**：获取影响股价的最新新闻
- **分析师观点**：包含专业分析师的建议和评级
- **投资建议**：基于数据驱动的投资建议
