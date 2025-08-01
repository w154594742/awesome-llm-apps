# 🎯 教程4：工具使用代理

欢迎来到工具的世界！本教程教您如何创建能够使用**不同类型工具**执行特定任务的代理。这是您的代理变得真正强大并能够执行现实世界操作的地方。

## 🎯 您将学到什么

- **内置工具**：使用Google ADK的预构建功能
- **函数工具**：创建自定义Python函数作为工具
- **第三方工具**：与LangChain、CrewAI和其他框架集成
- **MCP工具**：与模型上下文协议集成

## 🧠 核心概念：ADK中的工具

工具是**您的代理可以调用的函数**来执行特定任务。将它们视为代理的"手" - 它们允许代理：
- 搜索网络并访问实时信息
- 执行代码和进行计算
- 调用外部API和服务
- 访问数据库和文件系统
- 与其他AI框架交互

## 🔧 ADK中的工具类型

### 1. **内置工具**
Google ADK提供强大的预构建工具：
- **搜索工具**：网络搜索功能
- **代码执行工具**：安全运行Python代码
- **RAG工具**：检索增强生成
- **云工具**：Google Cloud集成

*注意：内置工具仅适用于Gemini模型*

### 2. **函数工具**
将Python函数转换为代理工具：
```python
def calculate_area(length: float, width: float) -> float:
    """计算矩形面积"""
    return length * width

# 转换为工具
area_tool = FunctionTool(calculate_area)
```

### 3. **第三方工具**
集成现有的AI框架：
- **LangChain工具**：访问LangChain的工具生态系统
- **CrewAI工具**：使用CrewAI的专业工具
- **自定义集成**：连接任何外部服务

### 4. **MCP工具**
模型上下文协议工具：
- **文件系统访问**：读写文件
- **网络爬取**：使用Firecrawl等服务
- **数据库连接**：访问各种数据源

## 🚀 教程结构

本教程包含**四个专门的示例**：

### 1. **[内置工具](./4_1_builtin_tools/README.md)**
- 使用Google ADK的预构建工具
- 搜索和代码执行示例
- 仅限Gemini模型功能

### 2. **[函数工具](./4_2_function_tools/README.md)**
- 创建自定义Python函数工具
- 数学计算和数据处理
- 适用于所有模型

### 3. **[第三方工具](./4_3_thirdparty_tools/README.md)**
- LangChain和CrewAI集成
- 外部API连接
- 框架互操作性

### 4. **[MCP工具](./4_4_mcp_tools/README.md)**
- 模型上下文协议集成
- 文件系统和网络工具
- 高级数据访问

## 🔧 基本设置

### 1. **安装依赖**
```bash
pip install google-adk langchain crewai
```

### 2. **基本工具代理**
```python
from google.adk.agents import LlmAgent
from google.adk.tools import BuiltinTool

# 创建带搜索工具的代理
search_agent = LlmAgent(
    name="search_agent",
    instructions="您是一个研究助手，可以搜索最新信息。",
    model="gemini-2.0-flash-exp",
    tools=[BuiltinTool.SEARCH]
)
```

### 3. **自定义函数工具**
```python
from google.adk.tools import FunctionTool

def get_weather(city: str) -> str:
    """获取指定城市的天气信息"""
    # 实际实现会调用天气API
    return f"{city}的天气：晴朗，22°C"

weather_tool = FunctionTool(get_weather)

weather_agent = LlmAgent(
    name="weather_agent",
    instructions="您是一个天气助手。",
    model="gemini-2.0-flash-exp",
    tools=[weather_tool]
)
```

## 📝 实践示例

### 搜索和计算代理
```python
from google.adk.tools import BuiltinTool, FunctionTool

def calculate_percentage(value: float, total: float) -> float:
    """计算百分比"""
    return (value / total) * 100

research_agent = LlmAgent(
    name="research_calculator",
    instructions="搜索信息并进行计算分析。",
    model="gemini-2.0-flash-exp",
    tools=[
        BuiltinTool.SEARCH,
        BuiltinTool.CODE_EXECUTION,
        FunctionTool(calculate_percentage)
    ]
)

# 使用示例
response = research_agent.run(
    "搜索2024年全球人口数据，并计算中国人口占全球人口的百分比"
)
```

## 🎯 最佳实践

### 1. **工具选择指南**
- **内置工具**：快速原型和Gemini专用功能
- **函数工具**：自定义业务逻辑
- **第三方工具**：利用现有生态系统
- **MCP工具**：高级数据访问和集成

### 2. **工具组合策略**
```python
# 研究代理：搜索 + 代码执行
research_tools = [BuiltinTool.SEARCH, BuiltinTool.CODE_EXECUTION]

# 数据分析代理：自定义函数 + 文件访问
analysis_tools = [FunctionTool(analyze_data), mcp_file_tool]

# 多功能代理：混合工具
hybrid_tools = [BuiltinTool.SEARCH, FunctionTool(custom_calc), langchain_tool]
```

### 3. **错误处理**
```python
def safe_calculation(a: float, b: float) -> str:
    """安全的除法计算"""
    try:
        if b == 0:
            return "错误：除数不能为零"
        return f"结果：{a / b}"
    except Exception as e:
        return f"计算错误：{str(e)}"
```

## 🔍 工具调试

### 1. **工具执行跟踪**
```python
response = agent.run("计算10除以2")
print(f"使用的工具：{response.tool_calls}")
print(f"工具结果：{response.tool_results}")
```

### 2. **工具性能监控**
```python
import time

def timed_function(func):
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"工具执行时间：{end - start:.2f}秒")
        return result
    return wrapper

@timed_function
def slow_calculation(n: int) -> int:
    """耗时计算示例"""
    return sum(range(n))
```

## 🚀 运行示例

### 1. **内置工具示例**
```bash
cd 4_1_builtin_tools
python builtin_tools_agent.py
```

### 2. **函数工具示例**
```bash
cd 4_2_function_tools
python function_tools_agent.py
```

### 3. **第三方工具示例**
```bash
cd 4_3_thirdparty_tools
python thirdparty_tools_agent.py
```

### 4. **MCP工具示例**
```bash
cd 4_4_mcp_tools
python mcp_tools_agent.py
```

## 🔄 下一步

现在您掌握了工具的力量！接下来：

1. **创建自定义工具**：为您的特定用例构建工具
2. **组合多个工具**：创建强大的多工具代理
3. **优化性能**：改进工具执行效率
4. **集成外部服务**：连接到您的业务系统

## 🤔 故障排除

### 常见问题：
1. **工具不可用**：检查模型兼容性（内置工具需要Gemini）
2. **函数错误**：验证函数签名和类型提示
3. **权限问题**：确保API密钥和权限正确设置

### 有用的资源：
- [Google ADK工具文档](https://ai.google.dev/agentic)
- [LangChain工具指南](https://python.langchain.com/docs/modules/tools/)
- [MCP协议规范](https://modelcontextprotocol.io/)
