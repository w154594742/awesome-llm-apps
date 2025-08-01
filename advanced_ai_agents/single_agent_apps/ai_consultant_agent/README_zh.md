# 🤝 使用Google ADK的AI顾问代理


一个由Google代理开发工具包驱动的强大商业顾问，提供全面的市场分析、战略规划和可操作的商业建议，具有实时网络研究功能。


## 功能特性

- **实时网络研究**：使用Perplexity AI搜索获取当前市场数据、趋势和竞争对手情报
- **市场分析**：利用网络搜索和AI洞察分析市场条件和机会
- **战略建议**：生成带有时间表和实施计划的可操作商业策略
- **风险评估**：识别潜在风险并提供缓解策略
- **交互式UI**：清洁的Google ADK网络界面，便于咨询
- **评估系统**：内置评估和调试功能，具有会话跟踪

## 工作原理

1. **输入阶段**：用户通过ADK网络界面提供商业问题或咨询请求
2. **研究阶段**：代理使用Perplexity AI进行实时网络研究，收集当前市场数据
3. **分析阶段**：代理使用市场分析工具处理查询并生成洞察
4. **策略阶段**：基于分析和网络研究生成战略建议
5. **综合阶段**：代理将发现结合成带有引用的全面咨询报告
6. **输出阶段**：呈现带有时间表和实施步骤的可操作建议

## 系统要求

- Python 3.8+
- Google API密钥（用于Gemini模型）
- Perplexity API密钥（用于实时网络搜索）
- 所需的Python包（见`requirements.txt`）

## 安装

1. 克隆此仓库：
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/single_agent_apps/ai_consultant_agent
   ```

2. 安装依赖：
   ```bash
   pip install -r requirements.txt
   ```

3. 获取API密钥：
   - [Google API密钥](https://aistudio.google.com/apikey)
   - [Perplexity API密钥](https://www.perplexity.ai/)

## 使用方法

1. 设置环境变量：
   ```bash
   export GOOGLE_API_KEY="your-google-api-key"
   export PERPLEXITY_API_KEY="your-perplexity-api-key"
   ```

2. 运行代理：
   ```bash
   python ai_consultant_agent.py
   ```

3. 在浏览器中打开提供的URL

4. 输入您的商业咨询问题

5. 查看全面的分析和建议

## 示例用例

- 市场进入策略
- 竞争对手分析
- 产品发布规划
- 商业模式优化
- 风险评估和缓解
- 增长策略制定

## 注意事项

- 确保您有有效的API密钥
- 建议质量取决于可用的市场数据
- 复杂的商业问题可能需要更长时间处理
