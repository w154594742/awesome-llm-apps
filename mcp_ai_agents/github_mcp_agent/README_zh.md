# 🐙 GitHub MCP 智能代理

一个基于 Streamlit 的应用程序，允许您通过模型上下文协议 (MCP) 使用自然语言查询来探索和分析 GitHub 仓库。

## 功能特性

- **自然语言界面**：用简单的中文或英文提问关于仓库的问题
- **全面分析**：探索问题、拉取请求、仓库活动和代码统计
- **交互式界面**：用户友好的界面，提供示例查询和自定义输入
- **MCP 集成**：利用模型上下文协议与 GitHub API 进行交互
- **实时结果**：获得关于仓库活动和健康状况的即时洞察

## 设置

### 系统要求

- Python 3.8+
- Node.js 和 npm（用于 MCP GitHub 服务器）
  - 这是一个关键要求！应用程序使用 `npx` 来运行 MCP GitHub 服务器
  - 请从 [nodejs.org](https://nodejs.org/) 下载并安装
- 具有适当权限的 GitHub 个人访问令牌
- OpenAI API 密钥

### 安装步骤

1. 克隆此仓库：
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd mcp-github-agent
   ```

2. 安装所需的 Python 包：
   ```bash
   pip install -r requirements.txt
   ```

3. 验证 Node.js 和 npm 是否已安装：
   ```bash
   node --version
   npm --version
   npx --version
   ```
   所有这些命令都应该返回版本号。如果没有，请安装 Node.js。

4. 设置您的 API 密钥：
   - 将 OpenAI API 密钥设置为环境变量：
     ```bash
     export OPENAI_API_KEY=your-openai-api-key
     ```
   - GitHub 令牌将直接在应用程序界面中输入

5. 创建 GitHub 个人访问令牌：
   - 访问 https://github.com/settings/tokens
   - 创建一个具有 `repo` 和 `user` 权限范围的新令牌
   - 将令牌保存在安全的地方

### 运行应用

1. 启动 Streamlit 应用：
   ```bash
   streamlit run app.py
   ```

2. 在应用界面中：
   - 在侧边栏中输入您的 GitHub 令牌
   - 指定要分析的仓库
   - 选择查询类型或编写您自己的查询
   - 点击"运行查询"

### 示例查询

#### 问题相关
- "按标签显示问题"
- "哪些问题正在被积极讨论？"
- "查找标记为 bug 的问题"

#### 拉取请求
- "哪些 PR 需要审查？"
- "显示最近合并的 PR"
- "查找有冲突的 PR"

#### 仓库分析
- "显示仓库健康指标"
- "显示仓库活动模式"
- "分析代码质量趋势"
