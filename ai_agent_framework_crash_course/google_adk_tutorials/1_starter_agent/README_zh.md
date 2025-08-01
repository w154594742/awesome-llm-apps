# 🎯 教程1：您的第一个ADK代理

欢迎来到Google ADK之旅的第一步！本教程向您介绍使用Google代理开发工具包创建简单AI代理的基本概念。

## 🎯 您将学到什么

- **基本代理创建**：如何创建您的第一个ADK代理
- **ADK工作流**：理解代理生命周期
- **简单文本处理**：基本输入/输出处理
- **代理配置**：基本参数和设置

## 🧠 核心概念：什么是ADK代理？

ADK代理是一个**可编程的AI助手**，它可以：
- 处理用户输入（文本、图像等）
- 使用AI模型（如Gemini）来理解和响应
- 根据您的指令执行特定任务
- 返回结构化或非结构化响应

将其视为创建一个**智能函数**，使用AI来处理复杂任务。

## 🔧 关键组件

### 1. **LlmAgent类**
在ADK中创建AI代理的主要构建块：
```python
from google.adk.agents import LlmAgent
```

### 2. **基本参数**
- **name**: 代理的唯一标识符
- **instructions**: 定义代理行为的系统提示
- **model**: 要使用的AI模型（例如，"gemini-2.0-flash-exp"）

### 3. **基本工作流**
```python
# 1. 创建代理
agent = LlmAgent(
    name="my_first_agent",
    instructions="您是一个有用的助手",
    model="gemini-2.0-flash-exp"
)

# 2. 运行代理
response = agent.run("Hello, world!")

# 3. 获取响应
print(response.content)
```

## 📝 实践示例

### 示例1：基本问候代理
```python
from google.adk.agents import LlmAgent

# 创建一个简单的问候代理
greeting_agent = LlmAgent(
    name="greeting_agent",
    instructions="您是一个友好的问候助手。总是以热情和积极的方式回应。",
    model="gemini-2.0-flash-exp"
)

# 测试代理
response = greeting_agent.run("你好！")
print(response.content)
```

### 示例2：文本摘要代理
```python
summary_agent = LlmAgent(
    name="summary_agent",
    instructions="您是一个文本摘要专家。将长文本总结为简洁的要点。",
    model="gemini-2.0-flash-exp"
)

long_text = """
人工智能（AI）是计算机科学的一个分支，致力于创建能够执行通常需要人类智能的任务的机器。
这包括学习、推理、问题解决、感知和语言理解。AI有许多应用，从自动驾驶汽车到医疗诊断。
"""

response = summary_agent.run(f"请总结以下文本：{long_text}")
print(response.content)
```

## 🚀 运行您的第一个代理

1. **设置环境**
   ```bash
   # 确保您有Google API密钥
   export GOOGLE_API_KEY="your-google-api-key"
   ```

2. **安装依赖**
   ```bash
   pip install google-adk
   ```

3. **运行示例**
   ```bash
   python starter_agent.py
   ```

## 🔍 理解响应对象

ADK代理返回一个包含以下属性的响应对象：
- **content**: 代理的主要响应文本
- **metadata**: 关于执行的额外信息
- **usage**: 令牌使用统计

```python
response = agent.run("解释量子计算")
print(f"响应: {response.content}")
print(f"使用的令牌: {response.usage}")
```

## 🎯 最佳实践

### 1. **清晰的指令**
```python
# 好的指令
instructions = "您是一个Python编程助手。提供清晰、简洁的代码示例和解释。"

# 避免模糊的指令
instructions = "帮助编程"
```

### 2. **适当的模型选择**
- **gemini-2.0-flash-exp**: 快速响应，适合简单任务
- **gemini-1.5-pro**: 更强大，适合复杂推理

### 3. **错误处理**
```python
try:
    response = agent.run(user_input)
    print(response.content)
except Exception as e:
    print(f"错误: {e}")
```

## 🔄 下一步

恭喜！您已经创建了您的第一个ADK代理。接下来：

1. **实验不同的指令**：尝试不同的系统提示
2. **测试各种输入**：看看您的代理如何处理不同类型的查询
3. **探索模型选项**：尝试不同的Gemini模型

准备好进入下一个教程：**[2_model_agnostic_agent](../2_model_agnostic_agent/README.md)**，您将学习如何使用不同的AI模型！

## 🤔 故障排除

### 常见问题：
1. **API密钥错误**：确保您的GOOGLE_API_KEY已正确设置
2. **导入错误**：验证google-adk是否已正确安装
3. **模型不可用**：检查您是否有权访问指定的模型

### 获取帮助：
- 查看[Google ADK文档](https://ai.google.dev/agentic)
- 检查[示例仓库](https://github.com/google/adk-examples)
- 在社区论坛中提问
