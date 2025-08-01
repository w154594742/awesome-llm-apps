# 📊 AI数据分析代理

一个使用Agno代理框架和OpenAI的gpt-4o模型构建的AI数据分析代理。该代理帮助用户通过自然语言查询分析他们的数据 - csv、excel文件，由OpenAI的语言模型和DuckDB提供支持以进行高效的数据处理 - 使数据分析对用户来说变得易于访问，无论他们的SQL专业知识如何。

## 功能特性

- 📤 **文件上传支持**: 
  - 上传CSV和Excel文件
  - 自动数据类型检测和模式推断
  - 支持多种文件格式

- 💬 **自然语言查询**: 
  - 将自然语言问题转换为SQL查询
  - 获得关于您数据的即时答案
  - 无需SQL知识

- 🔍 **高级分析**:
  - 执行复杂的数据聚合
  - 过滤和排序数据
  - 生成统计摘要
  - 创建数据可视化

- 🎯 **交互式UI**:
  - 用户友好的Streamlit界面
  - 实时查询处理
  - 清晰的结果展示

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd awesome-llm-apps/starter_ai_agents/ai_data_analysis_agent

   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥**
   - 从[OpenAI平台](https://platform.openai.com)获取OpenAI API密钥

3. **运行应用程序**
   ```bash
   streamlit run ai_data_analyst.py
   ```

## 使用方法

1. 使用上述命令启动应用程序
2. 在Streamlit侧边栏中提供您的OpenAI API密钥
3. 通过Streamlit界面上传您的CSV或Excel文件
4. 用自然语言询问关于您数据的问题
5. 查看结果和生成的可视化
