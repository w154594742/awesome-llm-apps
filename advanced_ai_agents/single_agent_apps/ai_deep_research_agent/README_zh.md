# 使用OpenAI代理SDK和Firecrawl的深度研究代理

一个强大的研究助手，利用OpenAI的代理SDK和Firecrawl的深度研究能力，对任何主题和任何问题进行全面的网络研究。

## 功能特性

- **深度网络研究**：自动搜索网络、提取内容并综合发现
- **增强分析**：使用OpenAI的代理SDK通过额外的上下文和洞察来详细阐述研究发现
- **交互式UI**：清洁的Streamlit界面，便于交互
- **可下载报告**：将研究发现导出为markdown文件

## 工作原理

1. **输入阶段**：用户提供研究主题和API凭据
2. **研究阶段**：工具使用Firecrawl搜索网络并提取相关信息
3. **分析阶段**：基于发现生成初始研究报告
4. **增强阶段**：第二个代理详细阐述初始报告，增加深度和上下文
5. **输出阶段**：向用户呈现增强报告并可供下载

## 系统要求

- Python 3.8+
- OpenAI API密钥
- Firecrawl API密钥
- 所需的Python包（见`requirements.txt`）

## 安装

1. 克隆此仓库：
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/single_agent_apps/ai_deep_research_agent
   ```

2. 安装依赖：
   ```bash
   pip install -r requirements.txt
   ```

3. 获取API密钥：
   - [OpenAI API密钥](https://platform.openai.com/)
   - [Firecrawl API密钥](https://firecrawl.dev/)

## 使用方法

1. 运行应用程序：
   ```bash
   streamlit run ai_deep_research_agent.py
   ```

2. 在侧边栏中输入您的API密钥

3. 输入您的研究主题

4. 点击"开始研究"

5. 查看生成的研究报告并下载

## 示例用例

- 学术研究和文献综述
- 市场研究和竞争分析
- 技术趋势分析
- 政策研究和分析
- 新闻和时事研究

## 注意事项

- 确保您有有效的API密钥
- 研究质量取决于可用的网络资源
- 大型研究主题可能需要更长时间处理
