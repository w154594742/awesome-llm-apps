# 💼 AI招聘代理团队

一个Streamlit应用程序，使用多个AI代理模拟全方位服务的招聘团队，自动化和简化招聘流程。每个代理代表不同的招聘专家角色 - 从简历分析和候选人评估到面试安排和沟通 - 协同工作提供全面的招聘解决方案。该系统将技术招聘人员、HR协调员和调度专家的专业知识结合到一个连贯的自动化工作流程中。

## 功能特性

#### 专业AI代理

- 技术招聘代理：分析简历并评估技术技能
- 沟通代理：处理专业邮件通信
- 调度协调代理：管理面试安排和协调
- 每个代理都有特定的专业知识，并为全面招聘进行协作


#### 端到端招聘流程
- 自动化简历筛选和分析
- 特定角色的技术评估
- 专业候选人沟通
- 自动化面试安排
- 集成反馈系统

## 运行应用程序前的重要事项

- 为招聘人员创建/使用新的Gmail账户
- 启用两步验证并为Gmail账户生成应用密码
- 应用密码是一个16位代码（使用时不带空格），应在此处生成 - [Google应用密码](https://support.google.com/accounts/answer/185833?hl=en) 请按照步骤生成密码 - 格式为'afec wejf awoj fwrv'（删除空格并在streamlit应用中输入）
- 创建/使用Zoom账户并前往Zoom应用市场获取API凭据：
[Zoom市场](https://marketplace.zoom.us)
- 前往开发者仪表板并创建新应用 - 选择服务器到服务器OAuth并获取凭据，您会看到3个凭据 - 客户端ID、客户端密钥和账户ID
- 之后，您需要为应用添加一些范围 - 以便通过邮件发送和创建候选人的zoom链接。

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/multi_agent_apps/agent_teams/ai_recruitment_agent_team
   
   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥和凭据**
   
   您需要以下凭据：
   - OpenAI API密钥
   - Gmail应用密码
   - Zoom API凭据（客户端ID、客户端密钥、账户ID）

3. **运行应用程序**
   ```bash
   streamlit run ai_recruitment_agent_team.py
   ```

4. **使用应用程序**
   - 在侧边栏中输入所有必需的凭据
   - 上传候选人简历
   - 输入职位描述
   - 让AI代理团队处理招聘流程

## 工作原理

1. **简历分析**：技术招聘代理分析上传的简历
2. **技能评估**：评估候选人与职位要求的匹配度
3. **沟通**：沟通代理起草专业邮件
4. **调度**：调度协调代理安排面试
5. **集成**：所有代理协作提供完整的招聘解决方案
