# 🚀 AI产品发布情报代理

一个为Go-To-Market（GTM）和产品营销团队打造的**简化情报中心**。  
使用**Streamlit + Agno（GPT-4o）+ Firecrawl**构建，该应用将分散的公共网络数据转化为简洁、可操作的发布洞察。

## 3个协调团队中的专业代理

| 标签 | 您将获得什么 |
|-----|--------------|
| **竞争对手分析代理** | 基于证据的竞争对手最新发布分析 - 定位、差异化因素、定价线索和渠道组合 |
| **市场情绪代理** | 按🚀 *积极* / ⚠️ *消极*驱动因素分类的综合社交讨论和评论主题 |
| **发布指标代理** | 公开可用的KPI - 采用数据、媒体报道、定性"热度"信号 |

额外功能：

* 🔑 **侧边栏关键输入** - 安全输入OpenAI和Firecrawl密钥（type="password"）
* 🧠 **协调的多代理团队** - 三个专家代理协同工作以获得更丰富的洞察
  * 🔍 产品发布分析师（GTM策略师）
  * 💬 市场情绪专家（消费者感知专家）
  * 📈 发布指标专家（性能分析师）
* ⚡ **快速操作** - 按**J/K/L**键触发三种分析，无需触摸UI
* 📑 **自动格式化的Markdown报告** - 首先是要点摘要，然后是扩展的深度分析
* 🛠️ **来源部分** - 每个报告都以被爬取或搜索的URL结尾

## 🛠️ 技术栈

| 层级 | 详情 |
|-------|---------|
| 数据 | **Firecrawl**异步搜索 + 爬取API |
| 代理 | **Agno团队**（GPT-4o）配备FirecrawlTools |
| 前端 | **Streamlit**（快速原型和部署） |
| 部署 | 本地或云端（Streamlit Cloud、Heroku等） |

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/multi_agent_apps/product_launch_intelligence_agent
   
   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥**
   
   您需要以下API密钥：
   ```bash
   export OPENAI_API_KEY="your-openai-api-key"
   export FIRECRAWL_API_KEY="your-firecrawl-api-key"
   ```

3. **运行应用程序**
   ```bash
   streamlit run product_launch_intelligence_agent.py
   ```

4. **使用应用程序**
   - 在侧边栏中输入您的API密钥
   - 输入产品或公司名称进行分析
   - 选择分析类型或使用快捷键J/K/L
   - 查看详细的情报报告

## 工作原理

1. **数据收集**：Firecrawl搜索和爬取相关网络数据
2. **专业分析**：三个专业代理分别分析不同方面
3. **情报综合**：将分析结果整合成可操作的洞察
4. **报告生成**：创建格式化的Markdown报告
5. **来源追踪**：提供所有数据来源的透明度

## 主要功能

- **竞争对手情报**：深入分析竞争对手的产品发布策略
- **市场情绪监控**：跟踪公众对产品发布的反应
- **性能指标**：收集和分析发布成功的关键指标
- **快速洞察**：通过键盘快捷键快速获得分析
- **可操作报告**：生成可直接用于决策的报告

## 应用场景

- 产品发布前的竞争分析
- 市场情绪监控和分析
- 发布后的性能评估
- GTM策略制定
- 竞争对手监控
- 市场趋势分析

## 系统要求

- Python 3.8+
- OpenAI API密钥
- Firecrawl API密钥
- 稳定的互联网连接

## 注意事项

- 分析质量取决于可用的公共数据
- API使用可能产生费用
- 遵守数据来源的使用条款
- 定期更新以获取最新信息
