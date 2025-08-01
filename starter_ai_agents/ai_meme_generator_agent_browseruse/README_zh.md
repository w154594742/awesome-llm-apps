# 🥸 AI表情包生成代理 - 浏览器使用

AI表情包生成代理是一个强大的浏览器自动化工具，使用AI代理创建表情包。该应用结合了多LLM功能和自动化浏览器交互，通过直接网站操作基于文本提示生成表情包。

## 功能特性

- **多LLM支持**
  - Claude 3.5 Sonnet (Anthropic)
  - GPT-4o (OpenAI)
  - Deepseek v3 (Deepseek)
  - 带API密钥验证的自动模型切换

- **浏览器自动化**：
  - 与imgflip.com表情包模板直接交互
  - 自动搜索相关表情包格式
  - 为顶部/底部标题动态插入文本
  - 从生成的表情包中提取图像链接

- **智能生成工作流**：
  - 从提示中提取动作动词
  - 隐喻模板匹配
  - 多步骤质量验证
  - 失败生成的自动重试机制

- **用户友好界面**：
  - 模型配置侧边栏
  - API密钥管理
  - 带可点击链接的直接表情包预览
  - 响应式错误处理


所需API密钥：
- **Anthropic**（用于Claude）
- **Deepseek** 
- **OpenAI**（用于GPT-4o）

## 如何运行

1. **克隆仓库**：
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd ai_agent_tutorials/ai_meme_generator_browseruse
   ```
2. **安装依赖**：
    ```bash
    pip install -r requirements.txt
    ```
    如需要，安装`playwright`。
    ```bash
    python -m playwright install --with-deps
    ```
3. **运行Streamlit应用**：
    ```bash
    streamlit run ai_meme_generator_agent.py

    ```
