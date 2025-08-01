## 💲 具有网络访问的AI金融代理团队
此脚本演示了如何仅用20行Python代码构建一个作为金融分析师协同工作的AI代理团队，使用GPT-4o。该系统结合网络搜索功能和金融数据分析工具，提供全面的金融洞察。

### 功能特性
- 具有专业角色的多代理系统：
    - 网络代理用于一般互联网研究
    - 金融代理用于详细金融分析
    - 团队代理用于协调代理之间的工作
- 通过YFinance实时访问金融数据
- 使用DuckDuckGo的网络搜索功能
- 使用SQLite持久存储代理交互

### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd advanced_ai_agents/multi_agent_apps/agent_teams/ai_finance_agent_team
```

2. 安装所需依赖：

```bash
pip install -r requirements.txt
```

3. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)（或您选择的LLM提供商）并获取您的API密钥。
- 将您的OpenAI API密钥设置为环境变量：
```bash
export OPENAI_API_KEY='your-api-key-here'
```

4. 运行AI金融代理团队
```bash
python ai_finance_agent_team.py
```

5. 打开您的网络浏览器并导航到控制台输出中提供的URL，通过游乐场界面与金融代理团队交互。

### 工作原理？

1. **团队初始化**：创建具有不同专业的多个AI代理
2. **任务分配**：团队代理将复杂的金融查询分解为子任务
3. **专业分析**：
   - 网络代理搜索相关的市场新闻和趋势
   - 金融代理分析股票数据、财务指标和市场表现
4. **协作**：代理共享发现并构建全面的分析
5. **报告生成**：团队提供详细的金融洞察和建议
