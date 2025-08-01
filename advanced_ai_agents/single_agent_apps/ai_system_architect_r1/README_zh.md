# 🤖 使用R1的AI系统架构师顾问

一个Agno代理系统，使用结合DeepSeek R1推理和Claude的双模型方法提供专家软件架构分析和建议。该系统为复杂软件系统提供详细的技术分析、实施路线图和架构决策。

## 功能特性

- **双AI模型架构**
  - **DeepSeek推理器**：提供关于架构模式、工具和实施策略的初始技术分析和结构化推理
  - **Claude-3.5**：基于DeepSeek的分析生成详细解释、实施路线图和技术规格

- **全面分析组件**
  - 架构模式选择
  - 基础设施资源规划
  - 安全措施和合规性
  - 数据库架构
  - 性能要求
  - 成本估算
  - 风险评估

- **分析类型**
  - 实时事件处理系统
  - 医疗数据平台
  - 金融交易平台
  - 多租户SaaS解决方案
  - 数字内容分发网络
  - 供应链管理系统

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/single_agent_apps/ai_system_architect_r1
   
   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥**
   
   您需要以下API密钥：
   ```bash
   export DEEPSEEK_API_KEY="your-deepseek-api-key"
   export ANTHROPIC_API_KEY="your-anthropic-api-key"
   ```

3. **运行应用程序**
   ```bash
   streamlit run ai_system_architect_r1.py
   ```

4. **使用应用程序**
   - 在侧边栏中输入您的API密钥
   - 选择系统类型或输入自定义描述
   - 提供系统要求和约束
   - 查看详细的架构分析和建议

## 工作原理

1. **需求分析**：系统分析用户提供的系统要求
2. **推理阶段**：DeepSeek R1进行深度技术推理和架构分析
3. **详细化阶段**：Claude-3.5基于推理结果生成详细的实施指南
4. **综合输出**：提供完整的架构建议、实施路线图和技术规格

## 示例用例

- 微服务架构设计
- 云原生应用架构
- 数据密集型系统设计
- 高可用性系统架构
- 安全架构设计
- 性能优化策略

## 系统要求

- Python 3.8+
- DeepSeek API密钥
- Anthropic API密钥
- 稳定的互联网连接

## 注意事项

- 确保您有有效的API密钥
- 复杂系统分析可能需要更长时间
- 建议基于当前最佳实践和技术标准
