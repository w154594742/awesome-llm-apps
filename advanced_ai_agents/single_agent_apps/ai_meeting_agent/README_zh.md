## 📝 AI会议准备代理
这个Streamlit应用利用多个AI代理创建全面的会议准备材料。它使用OpenAI的GPT-4、Anthropic的Claude和Serper API进行网络搜索，生成上下文分析、行业洞察、会议策略和高管简报。

### 功能特性

- 用于彻底会议准备的多代理AI系统
- 利用OpenAI的GPT-4和Anthropic的Claude模型
- 使用Serper API的网络搜索功能
- 生成详细的上下文分析、行业洞察、会议策略和高管简报

### 如何开始？

1. 克隆GitHub仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd advanced_ai_agents/single_agent_apps/ai_meeting_agent
```
2. 安装所需依赖：

```bash
pip install -r requirements.txt
```
3. 获取您的Anthropic API密钥

- 注册[Anthropic账户](https://console.anthropic.com)（或您选择的LLM提供商）并获取您的API密钥。

4. 获取您的SerpAPI密钥

- 注册[Serper API账户](https://serper.dev/)并获取您的API密钥。

5. 运行Streamlit应用
```bash
streamlit run ai_meeting_agent.py
```

### 工作原理？

1. **会议信息输入**：用户提供会议详情、参与者和目标
2. **上下文研究**：AI代理搜索相关背景信息和行业趋势
3. **策略制定**：基于研究生成会议策略和讨论要点
4. **简报生成**：创建高管级别的会议简报和准备材料
5. **材料整合**：将所有信息整合成完整的会议准备包

### 主要功能

- **上下文分析**：深入分析会议背景和相关因素
- **行业洞察**：提供最新的行业趋势和市场信息
- **会议策略**：制定有效的会议策略和谈判要点
- **高管简报**：生成简洁的高管级别简报材料
- **网络研究**：实时搜索最新信息和数据

### 应用场景

- 商务会议准备
- 客户会议策划
- 投资者会议准备
- 合作伙伴谈判
- 董事会会议材料
- 销售演示准备

### 系统要求

- Python 3.8+
- Anthropic API密钥
- Serper API密钥
- 稳定的互联网连接
