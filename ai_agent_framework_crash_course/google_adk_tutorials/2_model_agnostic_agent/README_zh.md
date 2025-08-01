# 🎯 教程2：模型无关代理

学习如何使用OpenRouter创建与**不同AI模型**协作的代理。此示例展示了ADK如何通过单独的代理实现使用OpenAI和Anthropic模型。

## 🎯 您将学到什么

- **OpenRouter集成**：使用一个API密钥访问多个模型提供商
- **独立代理实现**：并排比较不同模型
- **工具集成**：为您的代理添加简单工具
- **根代理模式**：正确的ADK代理命名约定

## 🧠 核心概念：一个API，多个模型

[OpenRouter](https://openrouter.ai/)提供统一的API来访问多个AI模型：
- ✅ **单一API密钥**：使用一个密钥访问OpenAI和Anthropic
- ✅ **轻松比较**：运行不同代理来比较响应
- ✅ **成本效益**：按使用付费定价
- ✅ **无供应商锁定**：随时切换提供商

## 📁 项目结构

```
2_model_agnostic_agent/
├── README.md                    # 此概述
├── requirements.txt             # 共享依赖
├── openai_adk_agent/           # OpenAI GPT-4代理
│   └── agent.py                # 代理实现
└── anthropic_adk_agent/        # Anthropic Claude代理
    └── agent.py                # 代理实现
```

## 🔧 设置OpenRouter

### 1. 获取API密钥
1. 访问[OpenRouter](https://openrouter.ai/)
2. 创建账户并获取API密钥
3. 设置环境变量：
   ```bash
   export OPENROUTER_API_KEY="your-openrouter-api-key"
   ```

### 2. 安装依赖
```bash
pip install -r requirements.txt
```

## 🤖 代理实现

### OpenAI GPT-4代理
```python
from google.adk.agents import LlmAgent
from google.adk.tools import BuiltinTool

# 创建OpenAI代理
openai_agent = LlmAgent(
    name="openai_research_agent",
    instructions="您是一个研究助手，专门提供详细和准确的信息。",
    model="openai/gpt-4o",
    tools=[BuiltinTool.SEARCH],
    api_key=os.getenv("OPENROUTER_API_KEY"),
    base_url="https://openrouter.ai/api/v1"
)
```

### Anthropic Claude代理
```python
# 创建Anthropic代理
anthropic_agent = LlmAgent(
    name="anthropic_research_agent", 
    instructions="您是一个分析助手，专门提供深思熟虑的分析。",
    model="anthropic/claude-3-5-sonnet-20241022",
    tools=[BuiltinTool.SEARCH],
    api_key=os.getenv("OPENROUTER_API_KEY"),
    base_url="https://openrouter.ai/api/v1"
)
```

## 🚀 运行代理

### 1. 运行OpenAI代理
```bash
cd openai_adk_agent
python agent.py
```

### 2. 运行Anthropic代理
```bash
cd anthropic_adk_agent
python agent.py
```

## 🔍 比较响应

两个代理都会处理相同的查询，但可能提供不同的视角：

**示例查询**："解释量子计算的基本原理"

**OpenAI GPT-4响应**：通常提供结构化、技术性的解释
**Anthropic Claude响应**：通常提供更具分析性、细致入微的解释

## 🛠️ 工具集成

两个代理都使用内置搜索工具：
```python
tools=[BuiltinTool.SEARCH]
```

这使它们能够：
- 搜索最新信息
- 验证事实
- 提供当前数据

## 🎯 最佳实践

### 1. **模型选择指南**
- **OpenAI GPT-4**：擅长代码生成、结构化输出
- **Anthropic Claude**：擅长分析、创意写作、安全性

### 2. **成本优化**
```python
# 对于简单任务使用较便宜的模型
simple_agent = LlmAgent(
    model="openai/gpt-3.5-turbo",  # 更便宜
    # ...
)

# 对于复杂任务使用高级模型
complex_agent = LlmAgent(
    model="anthropic/claude-3-5-sonnet-20241022",  # 更强大
    # ...
)
```

### 3. **错误处理**
```python
try:
    response = agent.run(query)
    print(response.content)
except Exception as e:
    print(f"代理错误: {e}")
```

## 🔄 下一步

现在您知道如何使用不同的模型了！接下来：

1. **实验不同模型**：尝试其他OpenRouter可用的模型
2. **比较响应**：对相同查询运行两个代理
3. **优化成本**：根据任务复杂性选择模型

准备好进入下一个教程：**[3_structured_output_agent](../3_structured_output_agent/README.md)**，您将学习如何获得结构化的JSON响应！

## 🤔 故障排除

### 常见问题：
1. **OpenRouter API密钥**：确保您的密钥有效且有余额
2. **模型可用性**：检查OpenRouter上的模型状态
3. **网络问题**：验证您的互联网连接

### 有用的资源：
- [OpenRouter文档](https://openrouter.ai/docs)
- [可用模型列表](https://openrouter.ai/models)
- [定价信息](https://openrouter.ai/pricing)
