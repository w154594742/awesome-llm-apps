# 🌐 浏览器MCP代理

![Area](https://github.com/user-attachments/assets/285a6a02-c1a9-4581-b32b-b244f665f648)

一个基于Streamlit的应用程序，允许您通过模型上下文协议（MCP）和[MCP-Agent](https://github.com/lastmile-ai/mcp-agent)与Puppeteer集成，使用自然语言命令浏览和与网站交互。

## 功能特性

- **自然语言界面**：用简单的中文命令控制浏览器
- **完整浏览器导航**：访问网站并在页面间导航
- **交互式元素**：点击按钮、填写表单和滚动内容
- **视觉反馈**：对网页元素进行截图
- **信息提取**：从网页中提取和总结内容
- **多步骤任务**：通过对话完成复杂的浏览序列

## 设置

### 系统要求

- Python 3.8+
- Node.js和npm（用于Puppeteer）
  - 这是一个关键要求！应用程序使用Puppeteer控制无头浏览器
  - 请从[nodejs.org](https://nodejs.org/)下载并安装
- OpenAI或Anthropic API密钥

### 安装步骤

1. 克隆此仓库：
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd mcp_ai_agents/browser_mcp_agent
   ```

2. 安装所需的Python包：
   ```bash
   pip install -r requirements.txt
   ```

3. 验证Node.js和npm是否已安装：
   ```bash
   node --version
   npm --version
   ```
   两个命令都应该返回版本号。如果没有，请安装Node.js。

4. 设置您的API密钥：
   - 将OpenAI API密钥设置为环境变量：
     ```bash
     export OPENAI_API_KEY=your-openai-api-key
     ```


### 运行应用

1. 启动Streamlit应用：
   ```bash
   streamlit run main.py
   ```

2. 在应用界面中：
   - 输入您的浏览命令
   - 点击"运行命令"
   - 查看结果和截图

### 示例命令

#### 基础导航
- "访问 www.lastmileai.dev"
- "返回上一页"

#### 交互操作
- "点击登录按钮"
- "向下滚动查看更多内容"

#### 内容提取
- "总结此页面的主要内容"
- "提取导航菜单项"
- "对主要部分进行截图"

#### 多步骤任务
- "访问博客，找到最新文章，并总结其要点"

## 架构

该应用程序使用：
- Streamlit作为用户界面
- MCP（模型上下文协议）连接LLM与工具
- Puppeteer进行浏览器自动化
- [MCP-Agent](https://github.com/lastmile-ai/mcp-agent/)作为代理框架
- OpenAI的模型来解释命令并生成响应
