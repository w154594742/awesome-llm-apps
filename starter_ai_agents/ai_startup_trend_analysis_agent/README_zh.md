## 📈 AI创业趋势分析代理 
AI创业趋势分析代理是为新兴企业家提供的工具，通过识别新兴趋势、潜在市场空白和特定行业的增长机会来生成可操作的洞察。企业家可以使用这些数据驱动的洞察来验证想法、发现市场机会，并就他们的创业企业做出明智的决策。它结合了Newspaper4k和DuckDuckGo来扫描和分析专注于创业的文章和市场数据。使用Claude 3.5 Sonnet，它处理这些信息以提取新兴模式，使企业家能够识别有前景的创业机会。


### 功能特性
- **用户提示**：企业家可以输入感兴趣的特定创业行业或技术进行研究。
- **新闻收集**：该代理使用DuckDuckGo收集最近的创业新闻、融资轮次和市场分析。
- **摘要生成**：使用Newspaper4k生成经过验证信息的简洁摘要。
- **趋势分析**：系统识别分析故事中创业融资、技术采用和市场机会的新兴模式。
- **Streamlit UI**：应用程序具有使用Streamlit构建的用户友好界面，便于交互。

### 如何开始
1. **克隆仓库**：
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git 
   cd awesome-llm-apps/ai_agent_tutorials/ai_startup_trend_analysis_agent
   ```

2. **创建并激活虚拟环境**：
   ```bash
   # 对于macOS/Linux
   python -m venv venv
   source venv/bin/activate

   # 对于Windows
   python -m venv venv
   .\venv\Scripts\activate
   ```

3. **安装所需包**：
   ```bash
   pip install -r requirements.txt
   ```

4. **运行应用程序**：
   ```bash
   streamlit run startup_trends_agent.py
   ```
### 重要说明
- 系统专门使用Claude的API进行高级语言处理。您可以从[Anthropic网站](https://www.anthropic.com/api)获取您的Anthropic API密钥。
