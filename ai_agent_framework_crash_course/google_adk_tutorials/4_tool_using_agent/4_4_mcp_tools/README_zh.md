# 🌐 MCP工具集成

欢迎来到**模型上下文协议（MCP）**集成指南！此示例演示如何通过标准化的MCP协议将您的ADK代理与外部数据源和工具连接。

## 🎯 您将学到什么

- **MCP基础知识**：理解模型上下文协议
- **ADK ↔ MCP集成**：使用`MCPToolset`连接到MCP服务器
- **外部工具访问**：利用MCP服务器的工具
- **服务器通信**：使用本地和远程MCP服务器
- **实际应用**：文件系统和Wikipedia的实际示例

## 🧠 核心概念：模型上下文协议

**模型上下文协议（MCP）**是一个开放标准，使AI代理能够：
- 一致地访问外部数据源
- 使用远程服务器的工具
- 与各种应用程序通信
- 在交互中保持上下文

### MCP如何与ADK协作

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│  ADK代理    │◄──►│ MCPToolset  │◄──►│ MCP服务器   │
│             │    │             │    │             │
│   Gemini    │    │   桥接器    │    │   工具      │
└─────────────┘    └─────────────┘    └─────────────┘
```

## 🔧 设置MCP集成

### 1. **安装依赖**
```bash
pip install google-adk mcp
```

### 2. **基本MCP工具集成**
```python
from google.adk.agents import LlmAgent
from google.adk.tools import MCPToolset

# 创建MCP工具集
mcp_toolset = MCPToolset(
    server_name="filesystem",
    server_command=["npx", "-y", "@modelcontextprotocol/server-filesystem", "/tmp"]
)

# 创建带MCP工具的代理
mcp_agent = LlmAgent(
    name="mcp_agent",
    instructions="您是一个可以访问文件系统的助手。",
    model="gemini-2.0-flash-exp",
    tools=[mcp_toolset]
)
```

### 3. **多个MCP服务器**
```python
# 文件系统服务器
filesystem_tools = MCPToolset(
    server_name="filesystem",
    server_command=["npx", "-y", "@modelcontextprotocol/server-filesystem", "/tmp"]
)

# Wikipedia服务器
wikipedia_tools = MCPToolset(
    server_name="wikipedia",
    server_command=["npx", "-y", "@modelcontextprotocol/server-wikipedia"]
)

# 多工具代理
multi_mcp_agent = LlmAgent(
    name="multi_mcp_agent",
    instructions="您是一个可以访问文件系统和Wikipedia的研究助手。",
    model="gemini-2.0-flash-exp",
    tools=[filesystem_tools, wikipedia_tools]
)
```

## 📝 实践示例

### 文件系统操作
```python
# 文件操作示例
response = mcp_agent.run("""
请帮我：
1. 列出/tmp目录下的文件
2. 创建一个名为test.txt的文件
3. 在文件中写入"Hello MCP!"
4. 读取文件内容确认
""")

print(response.content)
```

### Wikipedia研究
```python
# Wikipedia搜索示例
response = multi_mcp_agent.run("""
搜索关于"人工智能"的Wikipedia文章，
然后将关键信息保存到一个文件中。
""")

print(response.content)
```

### 数据处理工作流
```python
# 复杂数据处理示例
response = multi_mcp_agent.run("""
执行以下数据研究工作流：
1. 从Wikipedia搜索"机器学习"的信息
2. 提取关键概念和定义
3. 将信息整理成结构化格式
4. 保存到名为ml_research.md的文件中
5. 确认文件已创建并显示内容摘要
""")

print(response.content)
```

## 🎯 可用的MCP服务器

### 1. **文件系统服务器**
- **功能**：文件和目录操作
- **命令**：`npx -y @modelcontextprotocol/server-filesystem <directory>`
- **用途**：读写文件、目录浏览、文件管理

```python
filesystem_tools = MCPToolset(
    server_name="filesystem",
    server_command=["npx", "-y", "@modelcontextprotocol/server-filesystem", "/home/user/documents"]
)
```

### 2. **Wikipedia服务器**
- **功能**：Wikipedia文章搜索和检索
- **命令**：`npx -y @modelcontextprotocol/server-wikipedia`
- **用途**：研究、事实查证、信息收集

```python
wikipedia_tools = MCPToolset(
    server_name="wikipedia",
    server_command=["npx", "-y", "@modelcontextprotocol/server-wikipedia"]
)
```

### 3. **自定义MCP服务器**
```python
# 自定义服务器示例
custom_tools = MCPToolset(
    server_name="custom_api",
    server_command=["python", "my_mcp_server.py"],
    server_params={
        "api_key": "your-api-key",
        "base_url": "https://api.example.com"
    }
)
```

## 🔧 高级配置

### 1. **服务器参数配置**
```python
mcp_toolset = MCPToolset(
    server_name="advanced_filesystem",
    server_command=["npx", "-y", "@modelcontextprotocol/server-filesystem", "/workspace"],
    server_params={
        "max_file_size": "10MB",
        "allowed_extensions": [".txt", ".md", ".json"],
        "read_only": False
    }
)
```

### 2. **错误处理和重试**
```python
import time

def robust_mcp_agent(query: str, max_retries: int = 3):
    """带重试机制的MCP代理调用"""
    for attempt in range(max_retries):
        try:
            response = mcp_agent.run(query)
            return response
        except Exception as e:
            print(f"尝试 {attempt + 1} 失败: {e}")
            if attempt < max_retries - 1:
                time.sleep(2 ** attempt)  # 指数退避
            else:
                raise e
```

### 3. **性能监控**
```python
import time
import logging

class MonitoredMCPToolset(MCPToolset):
    """带监控的MCP工具集"""
    
    def __init__(self, *args, **kwargs):
        super().__init__(*args, **kwargs)
        self.call_count = 0
        self.total_time = 0
    
    def call_tool(self, tool_name: str, **kwargs):
        """监控工具调用"""
        start_time = time.time()
        self.call_count += 1
        
        try:
            result = super().call_tool(tool_name, **kwargs)
            execution_time = time.time() - start_time
            self.total_time += execution_time
            
            logging.info(f"MCP工具调用: {tool_name}, 耗时: {execution_time:.2f}s")
            return result
        except Exception as e:
            logging.error(f"MCP工具调用失败: {tool_name}, 错误: {e}")
            raise
```

## 🚀 运行示例

1. **安装Node.js和MCP服务器**：
   ```bash
   # 确保安装了Node.js
   node --version
   
   # MCP服务器会自动通过npx安装
   ```

2. **设置环境**：
   ```bash
   export GOOGLE_API_KEY="your-google-api-key"
   ```

3. **运行MCP示例**：
   ```bash
   python mcp_tools_agent.py
   ```

## 🔧 故障排除

### 常见问题

1. **服务器启动失败**
   ```bash
   # 检查Node.js是否安装
   node --version
   npm --version
   
   # 手动测试MCP服务器
   npx -y @modelcontextprotocol/server-filesystem /tmp
   ```

2. **权限问题**
   ```python
   # 确保目录权限正确
   import os
   os.chmod("/tmp", 0o755)
   ```

3. **网络连接问题**
   ```python
   # 检查网络连接
   import requests
   try:
       requests.get("https://www.wikipedia.org", timeout=5)
       print("网络连接正常")
   except:
       print("网络连接问题")
   ```

## 🎯 最佳实践

### 1. **安全考虑**
```python
# 限制文件系统访问
safe_filesystem = MCPToolset(
    server_name="safe_filesystem",
    server_command=["npx", "-y", "@modelcontextprotocol/server-filesystem", "/safe/directory"],
    server_params={"read_only": True}
)
```

### 2. **资源管理**
```python
# 使用上下文管理器
with MCPToolset("filesystem", ["npx", "-y", "@modelcontextprotocol/server-filesystem", "/tmp"]) as tools:
    agent = LlmAgent(
        name="temp_agent",
        instructions="临时文件操作代理",
        model="gemini-2.0-flash-exp",
        tools=[tools]
    )
    response = agent.run("列出文件")
```

### 3. **性能优化**
```python
# 缓存MCP连接
from functools import lru_cache

@lru_cache(maxsize=5)
def get_mcp_toolset(server_name: str, directory: str):
    """缓存MCP工具集连接"""
    return MCPToolset(
        server_name=server_name,
        server_command=["npx", "-y", f"@modelcontextprotocol/server-{server_name}", directory]
    )
```

## 🔄 下一步

恭喜！您已经完成了Google ADK工具教程！现在您可以：

1. **构建生产应用**：将学到的知识应用到实际项目中
2. **探索更多MCP服务器**：查找社区创建的MCP服务器
3. **创建自定义MCP服务器**：为您的特定需求构建服务器
4. **优化性能**：实现缓存、监控和错误处理

## 📚 参考资源

- [MCP官方文档](https://modelcontextprotocol.io/)
- [MCP服务器列表](https://github.com/modelcontextprotocol/servers)
- [Google ADK文档](https://ai.google.dev/agentic)
- [MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk)
