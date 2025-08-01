# 👨‍🏫 AI教学代理团队

一个Streamlit应用程序，汇集了一个专业AI教学代理团队，他们像专业教学团队一样协作。每个代理都充当专业教育者：课程设计师、学习路径专家、资源图书管理员和实践指导员 - 协同工作通过Google Docs创建完整的教育体验。

## 🪄 认识您的AI教学代理团队

#### 🧠 教授代理
- 在Google Docs中创建基础知识库
- 使用适当的标题和章节组织内容
- 包含详细的解释和示例
- 输出：带有目录的全面知识库文档

#### 🗺️ 学术顾问代理
- 在结构化的Google Doc中设计学习路径
- 创建渐进式里程碑标记
- 包含时间估算和先决条件
- 输出：具有清晰进展路径的可视化路线图文档

#### 📚 研究图书管理员代理
- 在有组织的Google Doc中编译资源
- 包含学术论文和教程的链接
- 添加描述和难度级别
- 输出：带有质量评级的分类资源列表

#### ✍️ 助教代理
- 在交互式Google Doc中开发练习
- 创建结构化的练习部分
- 包含解决方案指南
- 输出：带有答案的完整练习册

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/multi_agent_apps/agent_teams/ai_teaching_agent_team
   
   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥和Google集成**
   
   您需要：
   - OpenAI API密钥
   - Google Docs API凭据
   - Composio集成设置

3. **设置Google Docs集成**
   ```bash
   # 设置Composio Google Docs集成
   composio add googledocs
   ```

4. **运行应用程序**
   ```bash
   streamlit run ai_teaching_agent_team.py
   ```

5. **使用应用程序**
   - 输入您想要学习的主题
   - 指定学习目标和难度级别
   - 让AI教学团队创建完整的学习材料
   - 查看在Google Docs中生成的教学资源

## 工作原理

1. **主题分析**：团队分析学习主题和目标
2. **知识构建**：教授代理创建基础知识文档
3. **路径设计**：学术顾问代理设计学习路径
4. **资源收集**：图书管理员代理编译相关资源
5. **练习开发**：助教代理创建实践练习
6. **文档整合**：所有材料在Google Docs中组织和链接

## 主要功能

- **全面课程设计**：从基础知识到实践练习的完整课程
- **个性化学习路径**：根据学习目标定制的进展路径
- **丰富资源库**：精选的学习资源和参考材料
- **实践练习**：结构化的练习和评估材料
- **协作文档**：在Google Docs中的可共享学习材料

## 应用场景

- 在线课程开发
- 企业培训材料创建
- 学术课程设计
- 自主学习计划
- 技能培训项目
- 教育内容开发

## 系统要求

- Python 3.8+
- OpenAI API密钥
- Google账户和API凭据
- Composio集成设置
- 稳定的互联网连接

## 注意事项

- 需要适当的Google API权限
- 生成的文档将保存在您的Google Drive中
- 确保有足够的Google Drive存储空间
