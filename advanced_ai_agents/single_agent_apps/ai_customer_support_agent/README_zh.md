## 🛒 具有记忆的AI客户支持代理
这个Streamlit应用实现了一个AI驱动的客户支持代理，用于使用GPT-4o生成的合成数据。该代理使用OpenAI的GPT-4o模型，并使用Mem0库和Qdrant作为向量存储来维护过去交互的记忆。

### 功能特性

- 与AI客户支持代理交互的聊天界面
- 客户交互和档案的持久记忆
- 用于测试和演示的合成数据生成
- 利用OpenAI的GPT-4o模型进行智能响应

### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd advanced_ai_agents/single_agent_apps/ai_customer_support_agent
```

2. 安装所需依赖：

```bash
pip install -r requirements.txt
```

3. 确保Qdrant正在运行：
应用期望Qdrant在localhost:6333上运行。如果您的设置不同，请调整代码中的配置。

```bash
docker pull qdrant/qdrant
docker run -p 6333:6333 qdrant/qdrant
```

4. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)并获取您的API密钥。

5. 运行Streamlit应用
```bash
streamlit run ai_customer_support_agent.py
```

### 工作原理？

1. **客户识别**：系统识别或创建客户档案
2. **记忆检索**：从Qdrant向量存储中检索相关的历史交互
3. **上下文理解**：AI代理理解当前查询和历史上下文
4. **智能响应**：基于客户历史和当前需求生成个性化响应
5. **记忆更新**：将新的交互信息存储到记忆系统中

### 主要功能

- **个性化服务**：基于客户历史提供定制化支持
- **上下文感知**：理解对话的完整上下文
- **持久记忆**：跨会话保持客户信息
- **智能路由**：根据查询类型提供适当的响应
- **情感分析**：理解客户情绪并相应调整响应

### 应用场景

- 电子商务客户支持
- 技术支持服务
- 产品咨询和建议
- 订单状态查询
- 退换货处理
- 客户关系管理

### 系统要求

- Python 3.8+
- OpenAI API密钥
- Qdrant向量数据库
- 稳定的互联网连接

### 注意事项

- 确保Qdrant服务正常运行
- 客户数据隐私和安全需要适当保护
- 定期备份记忆数据
- 监控API使用成本
