## 🎯 AI潜在客户生成代理 - 由Firecrawl的提取端点驱动

AI潜在客户生成代理自动化从Quora查找和筛选潜在客户的过程。它使用Firecrawl的搜索和新的提取端点来识别相关用户档案，提取有价值的信息，并将其组织成Google Sheets中的结构化格式。此代理帮助销售和营销团队高效构建目标客户列表，同时节省数小时的手动研究时间。

### 功能特性
- **目标搜索**：使用Firecrawl的搜索端点根据您的搜索条件查找相关的Quora URL
- **智能提取**：利用Firecrawl的新提取端点从Quora档案中提取用户信息
- **自动化处理**：将提取的用户信息格式化为清洁、结构化的格式
- **Google Sheets集成**：自动创建并填充包含潜在客户信息的Google Sheets
- **可定制条件**：允许您定义特定的搜索参数，为您的细分市场找到理想的潜在客户

### 如何开始
1. **克隆仓库**：
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/single_agent_apps/ai_lead_generation_agent
   ```
3. **安装所需包**：
   ```bash
   pip install -r requirements.txt
   ```
4. **在composio中要做的重要事情**：
    - 在终端中运行此命令：`composio add googlesheets`
    - 在您的composio仪表板中，创建新的google sheet集成，并确保它在活动集成/连接选项卡中处于活动状态

5. **设置您的API密钥**：
   - 从[Firecrawl网站](https://www.firecrawl.dev/app/api-keys)获取您的Firecrawl API密钥
   - 从[Composio网站](https://composio.ai)获取您的Composio API密钥
   - 从[OpenAI网站](https://platform.openai.com/api-keys)获取您的OpenAI API密钥

6. **运行应用程序**：
   ```bash
   streamlit run ai_lead_generation_agent.py
   ```

### 工作原理

1. **搜索阶段**：在Quora上搜索与您的目标市场相关的内容
2. **提取阶段**：从找到的用户档案中提取关键信息
3. **处理阶段**：清理和结构化提取的数据
4. **存储阶段**：将潜在客户信息自动保存到Google Sheets
5. **分析阶段**：提供潜在客户质量和相关性的洞察

### 主要功能

- **自动化潜在客户发现**：无需手动搜索和筛选
- **数据提取**：从用户档案中提取关键信息
- **质量筛选**：基于预定义条件筛选高质量潜在客户
- **数据组织**：结构化存储潜在客户信息
- **可扩展性**：处理大量潜在客户数据

### 应用场景

- B2B销售潜在客户生成
- 市场研究和客户分析
- 竞争对手分析
- 影响者识别
- 客户细分研究

### 系统要求

- Python 3.8+
- Firecrawl API密钥
- Composio API密钥
- OpenAI API密钥
- Google账户（用于Sheets集成）
