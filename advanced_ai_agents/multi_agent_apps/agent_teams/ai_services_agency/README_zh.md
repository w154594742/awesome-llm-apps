# AI服务机构 👨‍💼

一个AI应用程序，使用多个AI代理模拟全方位服务的数字机构来分析和规划软件项目。每个代理代表项目生命周期中的不同角色，从战略规划到技术实施。

## 演示：

https://github.com/user-attachments/assets/a0befa3a-f4c3-400d-9790-4b9e37254405

## 功能特性

### 五个专业AI代理

- **CEO代理**：战略领导者和最终决策者
  - 使用结构化评估分析创业想法
  - 在产品、技术、营销和财务领域做出战略决策
  - 使用AnalyzeStartupTool和MakeStrategicDecision工具

- **CTO代理**：技术架构和可行性专家
  - 评估技术要求和可行性
  - 提供架构决策
  - 使用QueryTechnicalRequirements和EvaluateTechnicalFeasibility工具

- **产品经理代理**：产品策略专家
  - 定义产品策略和路线图
  - 协调技术和营销团队之间的工作
  - 专注于产品市场匹配

- **开发者代理**：技术实施专家
  - 提供详细的技术实施指导
  - 建议最优技术栈和云解决方案

- **营销代理**：市场推广专家
  - 制定营销策略和推广计划
  - 分析目标市场和竞争环境
  - 提供品牌和推广建议

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/multi_agent_apps/agent_teams/ai_services_agency
   
   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥**
   
   您需要OpenAI API密钥：
   ```bash
   export OPENAI_API_KEY="your-openai-api-key"
   ```

3. **运行应用程序**
   ```bash
   streamlit run ai_services_agency.py
   ```

4. **使用应用程序**
   - 输入您的项目或创业想法
   - 描述项目的技术要求和目标
   - 查看来自专业代理团队的全面分析和建议

## 工作原理

1. **项目分析**：CEO代理分析项目的整体可行性和战略价值
2. **技术评估**：CTO代理评估技术要求和实施可行性
3. **产品规划**：产品经理代理制定产品策略和发展路线图
4. **技术实施**：开发者代理提供详细的技术实施方案
5. **营销策略**：营销代理制定市场推广和品牌策略
6. **综合决策**：所有代理协作提供完整的项目分析和建议

## 主要功能

- **全面项目分析**：从多个角度评估项目可行性
- **技术架构设计**：提供详细的技术实施方案
- **产品策略制定**：制定产品发展和市场策略
- **营销计划**：创建全面的市场推广策略
- **风险评估**：识别项目风险和缓解策略

## 应用场景

- 创业项目评估
- 软件项目规划
- 产品开发策略
- 技术架构设计
- 市场进入策略
- 投资决策支持

## 系统要求

- Python 3.8+
- OpenAI API密钥
- 稳定的互联网连接
