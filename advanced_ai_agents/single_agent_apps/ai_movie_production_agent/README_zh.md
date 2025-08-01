## 🎬 AI电影制作代理
这个Streamlit应用是一个AI驱动的电影制作助手，使用Claude 3.5 Sonnet模型帮助将您的电影创意变为现实。它自动化了剧本写作和选角的过程，让您能够轻松创建引人入胜的电影概念。

### 功能特性
- 基于您的电影创意、类型和目标受众生成剧本大纲
- 为主要角色推荐合适的演员，考虑他们的过往表演和当前可用性
- 提供简洁的电影概念概述

### 如何开始？

1. 克隆GitHub仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd advanced_ai_agents/single_agent_apps/ai_movie_production_agent
```
2. 安装所需依赖：

```bash
pip install -r requirements.txt
```
3. 获取您的Anthropic API密钥

- 注册[Anthropic账户](https://console.anthropic.com)（或您选择的LLM提供商）并获取您的API密钥。

4. 获取您的SerpAPI密钥

- 注册[SerpAPI账户](https://serpapi.com/)并获取您的API密钥。

5. 运行Streamlit应用
```bash
streamlit run ai_movie_production_agent.py
```

### 工作原理？

1. **创意输入**：用户提供电影创意、类型和目标受众
2. **剧本开发**：AI代理基于输入生成详细的剧本大纲
3. **选角建议**：搜索并推荐适合各个角色的演员
4. **概念整合**：将所有元素整合成完整的电影制作概念
5. **输出交付**：提供完整的电影制作计划和建议

### 主要功能

- **剧本大纲生成**：创建结构化的故事情节和角色发展
- **智能选角**：基于角色需求推荐合适的演员
- **类型适配**：根据不同电影类型调整创作风格
- **受众定位**：考虑目标受众的偏好和期望
- **制作建议**：提供实用的制作指导和建议

### 应用场景

- 独立电影制作规划
- 剧本创作辅助
- 选角决策支持
- 电影概念开发
- 制片人项目评估
- 创意写作教学

### 系统要求

- Python 3.8+
- Anthropic API密钥
- SerpAPI密钥
- 稳定的互联网连接

### 注意事项

- 此工具用于创意辅助，不能替代专业的电影制作经验
- 选角建议仅供参考，实际选角需考虑更多因素
- 生成的内容需要进一步的专业开发和完善
