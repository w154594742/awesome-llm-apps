## 📡 RouteLLM聊天应用 

> 注意：此项目受开源[RouteLLM库](https://github.com/lm-sys/RouteLLM/tree/main)启发，该库提供不同语言模型之间的智能路由。

这个Streamlit应用程序演示了RouteLLM的使用，这是一个根据任务复杂性智能地在不同语言模型之间路由查询的系统。它提供了一个聊天界面，用户可以与AI模型交互，应用程序会自动为每个查询选择最合适的模型。

### 功能特性
- 与AI模型交互的聊天界面
- 使用RouteLLM自动选择模型
- 利用GPT-4和Meta-Llama 3.1模型
- 显示带有模型信息的聊天历史

### 如何开始？

1. 克隆GitHub仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/advanced_tools_frameworks/llm_router_app
```
2. 安装所需依赖：

```bash
pip install -r requirements.txt
```
3. 设置您的API密钥：

```bash
os.environ["OPENAI_API_KEY"] = "your_openai_api_key"
os.environ['TOGETHERAI_API_KEY'] = "your_togetherai_api_key"
```

4. 运行Streamlit应用
```bash
streamlit run llm_router_app.py
```

### 工作原理？

- 应用程序使用RouteLLM根据查询复杂性在GPT-4和Meta-Llama 3.1之间智能路由
- 简单查询路由到更快、更便宜的模型
- 复杂查询路由到更强大的模型
- 聊天历史显示每个响应使用的模型
