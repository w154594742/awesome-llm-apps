<div align="center">

  <h1>🪟 Windows使用自主代理</h1>

  <a href="https://github.com/CursorTouch/windows-use/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-green" alt="License">
  </a>
  <img src="https://img.shields.io/badge/python-3.12%2B-blue" alt="Python">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%20%7C%2011-blue" alt="Platform">
  <br>

  <a href="https://x.com/CursorTouch">
    <img src="https://img.shields.io/badge/follow-%40CursorTouch-1DA1F2?logo=twitter&style=flat" alt="Follow on Twitter">
  </a>
  <a href="https://discord.com/invite/Aue9Yj2VzS">
    <img src="https://img.shields.io/badge/Join%20on-Discord-5865F2?logo=discord&logoColor=white&style=flat" alt="Join us on Discord">
  </a>

</div>

<br>

**Windows-Use**是一个强大的自动化代理，直接在GUI层与Windows交互。它弥合了AI代理和Windows操作系统之间的差距，执行诸如打开应用程序、点击按钮、输入、执行shell命令和捕获UI状态等任务，所有这些都无需依赖传统的计算机视觉模型。使任何LLM都能执行计算机自动化，而不是依赖特定的模型。

## 🛠️安装指南

### **先决条件**

- Python 3.12或更高版本
- [UV](https://github.com/astral-sh/uv)（或`pip`）
- Windows 10或Windows 11
- 管理员权限（用于某些功能）

### **安装步骤**

1. **克隆仓库**
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/single_agent_apps/windows_use_autonomous_agent
   ```

2. **安装依赖**
   ```bash
   # 使用UV（推荐）
   uv pip install -r requirements.txt
   
   # 或使用pip
   pip install -r requirements.txt
   ```

3. **配置API密钥**
   ```bash
   # 设置您的OpenAI API密钥
   set OPENAI_API_KEY=your_openai_api_key_here
   ```

## 🚀 功能特性

### 核心功能
- **GUI自动化**：直接与Windows GUI元素交互
- **应用程序控制**：打开、关闭和管理应用程序
- **文本输入**：在任何应用程序中自动输入文本
- **鼠标操作**：点击、拖拽和滚动操作
- **屏幕捕获**：实时捕获和分析屏幕状态
- **Shell命令执行**：运行Windows命令和脚本

### 高级功能
- **智能等待**：等待UI元素出现或状态改变
- **错误处理**：自动重试和错误恢复
- **多显示器支持**：在多显示器设置中工作
- **可访问性集成**：使用Windows可访问性API

## 📖 使用方法

### 基本用法
```python
from windows_use import WindowsAgent

# 初始化代理
agent = WindowsAgent()

# 执行任务
agent.execute("打开记事本并输入'Hello World'")
```

### 高级用法
```python
# 复杂任务示例
task = """
1. 打开文件资源管理器
2. 导航到桌面文件夹
3. 创建新文件夹名为'AI_Projects'
4. 在该文件夹中创建新的文本文件
"""

agent.execute(task)
```

## 🎯 应用场景

- **办公自动化**：自动化重复的办公任务
- **软件测试**：自动化GUI测试
- **数据输入**：批量数据输入和处理
- **系统管理**：自动化系统维护任务
- **用户界面测试**：验证应用程序功能

## ⚠️ 注意事项

- 需要Windows 10或11操作系统
- 某些功能可能需要管理员权限
- 建议在测试环境中首先验证自动化脚本
- 确保有适当的备份，特别是在处理重要文件时

## 🔧 配置选项

- **延迟设置**：调整操作之间的延迟
- **重试次数**：设置失败操作的重试次数
- **日志级别**：配置详细的日志记录
- **安全模式**：启用额外的安全检查

## 📝 许可证

本项目采用MIT许可证。详情请见LICENSE文件。
