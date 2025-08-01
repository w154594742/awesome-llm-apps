# 🎮 使用DeepSeek R1的AI 3D PyGame可视化器
此项目演示了R1的代码能力，具有PyGame代码生成器和可视化器，并使用浏览器。该系统使用DeepSeek进行推理，使用OpenAI进行代码提取，使用浏览器自动化代理在Trinket.io上可视化代码。

### 功能特性

- 从自然语言描述生成PyGame代码
- 使用DeepSeek推理器进行代码逻辑和解释
- 使用OpenAI GPT-4o提取清洁代码
- 使用浏览器代理在Trinket.io上自动化代码可视化
- 提供简化的Streamlit界面
- 用于处理不同任务的多代理系统（导航、编码、执行、查看）

### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/ai_agent_tutorials/ai_3dpygame_r1
```

2. 安装所需依赖：
```bash
pip install -r requirements.txt
```

3. 获取您的API密钥
- 注册[DeepSeek](https://platform.deepseek.com/)并获取您的API密钥
- 注册[OpenAI](https://platform.openai.com/)并获取您的API密钥

4. 运行AI PyGame可视化器
```bash
streamlit run ai_3dpygame_r1.py
```

5. 浏览器使用自动打开您的网络浏览器并导航到控制台输出中提供的URL，与PyGame生成器交互。

### 工作原理？

1. **查询处理：** 用户输入所需PyGame可视化的自然语言描述。
2. **代码生成：** 
   - DeepSeek R1分析请求并生成详细的推理
   - OpenAI GPT-4o提取清洁的可执行PyGame代码
3. **浏览器自动化：** 多代理系统自动化整个过程：
   - 导航代理：打开并导航到Trinket.io
   - 编码代理：将生成的代码粘贴到编辑器中
   - 执行代理：运行代码
   - 查看代理：捕获并显示结果

### 系统要求

- Python 3.8+
- 稳定的互联网连接
- 现代网络浏览器
- DeepSeek API密钥
- OpenAI API密钥
