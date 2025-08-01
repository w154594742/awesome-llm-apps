# 🔗 第三方工具

第三方工具允许您集成来自LangChain、CrewAI等框架的**现有工具生态系统**。这通过利用更广泛的AI社区中经过实战检验的工具，极大地扩展了您的代理功能。

## 🎯 您将学到什么

- **LangChain集成**：使用LangChain的广泛工具库
- **CrewAI工具**：利用CrewAI的专业代理工具
- **工具适配器**：ADK如何包装外部工具
- **生态系统优势**：使用成熟工具库的优势
- **最佳实践**：何时以及如何使用第三方工具

## 🧠 核心概念：第三方工具

第三方工具是**为ADK包装的外部库**：
- **LangChain工具**：网络爬取、文档加载器、API
- **CrewAI工具**：网络爬取、文件操作、专业函数
- **自定义集成**：任何外部服务或库
- **包装器类**：ADK提供适配器以实现无缝集成

### 主要优势
- ✅ **丰富的生态系统**：访问数百个预构建工具
- ✅ **经过实战检验**：被数千名开发者使用的经过验证的工具
- ✅ **社区支持**：活跃的社区和文档
- ✅ **快速开发**：不要重新发明轮子

## 🔧 可用的第三方集成

### 1. **LangChain工具**
- **目的**：全面的工具生态系统
- **工具类型**：网络搜索、文档处理、API集成
- **优势**：成熟、文档完善、社区支持

```python
from google.adk.agents import LlmAgent
from google.adk.tools import LangChainTool
from langchain_community.tools import WikipediaQueryRun
from langchain_community.utilities import WikipediaAPIWrapper

# 创建LangChain工具
wikipedia_tool = WikipediaQueryRun(api_wrapper=WikipediaAPIWrapper())

# 包装为ADK工具
adk_wikipedia_tool = LangChainTool(wikipedia_tool)

# 创建代理
research_agent = LlmAgent(
    name="research_agent",
    instructions="您是一个研究助手，可以搜索Wikipedia获取信息。",
    model="gemini-2.0-flash-exp",
    tools=[adk_wikipedia_tool]
)
```

### 2. **CrewAI工具**
- **目的**：专业代理工具
- **工具类型**：网络爬取、文件操作、数据处理
- **优势**：针对代理工作流优化

```python
from google.adk.tools import CrewAITool
from crewai_tools import WebsiteSearchTool

# 创建CrewAI工具
website_search_tool = WebsiteSearchTool()

# 包装为ADK工具
adk_website_tool = CrewAITool(website_search_tool)

# 创建代理
web_agent = LlmAgent(
    name="web_agent",
    instructions="您是一个网络搜索专家。",
    model="gemini-2.0-flash-exp",
    tools=[adk_website_tool]
)
```

## 📝 实践示例

### LangChain工具示例
```python
from langchain_community.tools import DuckDuckGoSearchRun
from langchain_community.tools import ShellTool
from google.adk.tools import LangChainTool

# 搜索工具
search_tool = LangChainTool(DuckDuckGoSearchRun())

# Shell工具（谨慎使用）
shell_tool = LangChainTool(ShellTool())

# 多工具代理
multi_tool_agent = LlmAgent(
    name="multi_tool_agent",
    instructions="""
    您是一个多功能助手，可以：
    1. 搜索网络信息
    2. 执行系统命令（仅限安全操作）
    """,
    model="gemini-2.0-flash-exp",
    tools=[search_tool, shell_tool]
)

# 使用示例
response = multi_tool_agent.run("搜索Python最新版本信息")
print(response.content)
```

### CrewAI工具示例
```python
from crewai_tools import FileReadTool, DirectoryReadTool
from google.adk.tools import CrewAITool

# 文件操作工具
file_read_tool = CrewAITool(FileReadTool())
directory_tool = CrewAITool(DirectoryReadTool())

# 文件管理代理
file_agent = LlmAgent(
    name="file_agent",
    instructions="您是一个文件管理助手，可以读取和分析文件。",
    model="gemini-2.0-flash-exp",
    tools=[file_read_tool, directory_tool]
)

# 使用示例
response = file_agent.run("读取当前目录下的README.md文件")
print(response.content)
```

### 自定义第三方集成
```python
import requests
from google.adk.tools import FunctionTool

def weather_api_tool(city: str) -> dict:
    """
    使用外部天气API获取天气信息。
    
    Args:
        city: 城市名称
    
    Returns:
        天气信息字典
    """
    try:
        # 示例API调用（需要实际API密钥）
        api_key = "your-weather-api-key"
        url = f"http://api.openweathermap.org/data/2.5/weather"
        params = {
            "q": city,
            "appid": api_key,
            "units": "metric"
        }
        
        response = requests.get(url, params=params)
        data = response.json()
        
        return {
            "city": city,
            "temperature": data["main"]["temp"],
            "description": data["weather"][0]["description"],
            "humidity": data["main"]["humidity"]
        }
    except Exception as e:
        return {"error": f"无法获取{city}的天气信息: {str(e)}"}

# 创建工具
weather_tool = FunctionTool(weather_api_tool)

# 天气代理
weather_agent = LlmAgent(
    name="weather_agent",
    instructions="您是一个天气助手，可以提供实时天气信息。",
    model="gemini-2.0-flash-exp",
    tools=[weather_tool]
)
```

## 🎯 最佳实践

### 1. **工具选择指南**
```python
# LangChain - 适用于：
# - 文档处理
# - 网络搜索
# - API集成
# - 数据库连接

# CrewAI - 适用于：
# - 网络爬取
# - 文件操作
# - 代理特定任务

# 自定义集成 - 适用于：
# - 特定业务逻辑
# - 专有API
# - 性能关键操作
```

### 2. **安全考虑**
```python
# 安全的工具使用
safe_tools = [
    LangChainTool(WikipediaQueryRun()),  # 只读操作
    CrewAITool(FileReadTool()),          # 受限文件访问
]

# 避免危险工具
# ShellTool() - 可能执行危险命令
# FileWriteTool() - 可能修改重要文件
```

### 3. **性能优化**
```python
# 缓存工具结果
from functools import lru_cache

@lru_cache(maxsize=100)
def cached_api_call(query: str) -> dict:
    """缓存API调用结果"""
    # 实际API调用
    return {"result": f"Cached result for {query}"}

# 异步工具（如果支持）
import asyncio

async def async_tool(query: str) -> dict:
    """异步工具示例"""
    await asyncio.sleep(0.1)  # 模拟异步操作
    return {"result": f"Async result for {query}"}
```

## 🔧 故障排除

### 常见问题

1. **导入错误**
   ```python
   # 确保安装了必要的包
   pip install langchain-community crewai-tools
   ```

2. **API密钥问题**
   ```python
   # 设置环境变量
   import os
   os.environ["API_KEY"] = "your-api-key"
   ```

3. **工具兼容性**
   ```python
   # 检查工具是否与ADK兼容
   try:
       tool = LangChainTool(external_tool)
       print("工具兼容")
   except Exception as e:
       print(f"兼容性问题: {e}")
   ```

## 🚀 运行示例

1. **安装依赖**：
   ```bash
   pip install langchain-community crewai-tools
   ```

2. **设置API密钥**：
   ```bash
   export GOOGLE_API_KEY="your-google-api-key"
   export OPENWEATHER_API_KEY="your-weather-api-key"
   ```

3. **运行示例**：
   ```bash
   python thirdparty_tools_agent.py
   ```

## 🔄 下一步

现在您掌握了第三方工具集成！接下来：

1. **探索更多工具**：尝试LangChain和CrewAI的其他工具
2. **创建自定义集成**：包装您自己的外部服务
3. **优化性能**：缓存和异步操作

准备好学习**[MCP工具](../4_4_mcp_tools/README.md)**，您将使用模型上下文协议进行高级集成！
