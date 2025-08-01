# 🔍 内置工具

Google ADK提供强大的**预构建工具**，这些工具针对性能和可靠性进行了优化。这些工具与Gemini模型无缝集成，提供网络搜索和代码执行等基本功能。

## 🎯 您将学到什么

- **搜索工具**：用于实时信息的网络搜索功能
- **代码执行工具**：安全的Python代码执行环境
- **工具限制**：了解何时使用内置工具与自定义工具
- **最佳实践**：优化内置工具使用

## 🧠 核心概念：内置工具

内置工具是**Google ADK的原生功能**，提供：
- **高性能**：针对速度和可靠性进行优化
- **安全性**：内置安全性和沙盒
- **Gemini集成**：与Google模型深度集成
- **免维护**：无需维护自定义代码

### 重要限制
- ⚠️ **仅限Gemini模型**：内置工具仅适用于Gemini模型
- ⚠️ **单一工具类型**：不能在同一代理中混合内置和自定义工具
- ⚠️ **有限定制**：固定功能，无法修改行为

## 🔧 可用的内置工具

### 1. **搜索工具**
- **目的**：用于实时信息的网络搜索
- **用例**：新闻、事实、时事、研究
- **优势**：快速、准确、最新的结果

```python
from google.adk.agents import LlmAgent
from google.adk.tools import BuiltinTool

search_agent = LlmAgent(
    name="search_agent",
    instructions="您是一个研究助手，可以搜索最新信息。",
    model="gemini-2.0-flash-exp",
    tools=[BuiltinTool.SEARCH]
)
```

### 2. **代码执行工具**
- **目的**：安全执行Python代码
- **用例**：计算、数据分析、算法实现
- **优势**：沙盒环境、安全执行

```python
code_agent = LlmAgent(
    name="code_agent",
    instructions="您是一个编程助手，可以执行Python代码。",
    model="gemini-2.0-flash-exp",
    tools=[BuiltinTool.CODE_EXECUTION]
)
```

### 3. **组合工具**
```python
research_agent = LlmAgent(
    name="research_agent",
    instructions="您是一个研究和分析助手。",
    model="gemini-2.0-flash-exp",
    tools=[BuiltinTool.SEARCH, BuiltinTool.CODE_EXECUTION]
)
```

## 📝 实践示例

### 搜索工具示例
```python
# 搜索最新信息
response = search_agent.run("2024年人工智能的最新发展是什么？")
print(response.content)

# 搜索特定事实
response = search_agent.run("目前比特币的价格是多少？")
print(response.content)
```

### 代码执行示例
```python
# 数学计算
response = code_agent.run("计算斐波那契数列的前10项")
print(response.content)

# 数据分析
response = code_agent.run("""
创建一个包含1到100的列表，然后：
1. 计算所有偶数的和
2. 找出所有质数
3. 绘制一个简单的图表
""")
print(response.content)
```

### 组合工具示例
```python
# 搜索并分析
response = research_agent.run("""
搜索2024年全球GDP数据，然后：
1. 找出前5大经济体
2. 计算它们的GDP总和
3. 分析增长趋势
""")
print(response.content)
```

## 🎯 最佳实践

### 1. **搜索工具优化**
```python
# 好的搜索查询
"2024年第三季度苹果公司财报结果"

# 避免模糊查询
"苹果信息"
```

### 2. **代码执行安全**
```python
# 安全的代码请求
"使用matplotlib创建一个简单的条形图"

# 避免危险操作
"删除系统文件" # 这会被沙盒阻止
```

### 3. **工具组合策略**
```python
# 有效的工作流
instructions = """
您是一个数据研究助手。工作流程：
1. 首先搜索相关信息
2. 然后使用代码分析数据
3. 最后提供洞察和可视化
"""
```

## 🔍 工具执行跟踪

### 查看工具调用
```python
response = research_agent.run("搜索并分析股市数据")

# 检查使用了哪些工具
if hasattr(response, 'tool_calls'):
    for tool_call in response.tool_calls:
        print(f"使用工具: {tool_call.name}")
        print(f"工具输入: {tool_call.input}")
        print(f"工具输出: {tool_call.output}")
```

## 🚀 运行示例

1. **设置环境**：
   ```bash
   export GOOGLE_API_KEY="your-google-api-key"
   ```

2. **运行搜索示例**：
   ```bash
   python builtin_tools_agent.py
   ```

## 🔧 故障排除

### 常见问题

1. **工具不可用错误**
   ```
   错误: Built-in tools are only available with Gemini models
   ```
   **解决方案**: 确保使用Gemini模型（如"gemini-2.0-flash-exp"）

2. **混合工具错误**
   ```
   错误: Cannot mix built-in and custom tools
   ```
   **解决方案**: 在同一代理中只使用内置工具或只使用自定义工具

3. **API密钥错误**
   ```
   错误: Invalid API key
   ```
   **解决方案**: 验证您的Google API密钥是否正确设置

### 性能优化

1. **搜索查询优化**
   - 使用具体、明确的搜索词
   - 包含时间范围（如"2024年"）
   - 指定数据类型（如"统计数据"、"报告"）

2. **代码执行优化**
   - 将复杂任务分解为小步骤
   - 使用高效的算法和数据结构
   - 避免无限循环和资源密集型操作

## 🔄 下一步

现在您了解了内置工具！接下来：

1. **实验不同查询**：尝试各种搜索和代码请求
2. **组合工具**：创建使用多个内置工具的工作流
3. **性能测试**：测量不同查询的响应时间

准备好学习**[函数工具](../4_2_function_tools/README.md)**，您将创建自定义工具功能！

## 📚 参考资源

- [Google ADK内置工具文档](https://ai.google.dev/agentic)
- [Gemini模型指南](https://ai.google.dev/gemini-api)
- [工具使用最佳实践](https://ai.google.dev/agentic/tools)
