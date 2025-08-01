# 🚀 Google ADK速成课程

一个从基础到高级概念学习Google代理开发工具包（ADK）的综合教程系列。这个速成课程旨在让您从零开始成为使用Google ADK构建AI代理的专家。

## 📚 什么是Google ADK？

Google ADK（代理开发工具包）是一个用于**开发和部署AI代理**的灵活模块化框架。它针对Gemini和Google生态系统进行了优化，但是**模型无关**和**部署无关**的，使其与其他框架兼容。

### 主要功能：
- **灵活编排**：使用工作流代理或LLM驱动的动态路由定义工作流
- **多代理架构**：使用多个专业代理构建模块化应用程序
- **丰富的工具生态系统**：使用预构建工具、创建自定义函数或集成第三方库
- **部署就绪**：容器化并在任何地方部署代理
- **内置评估**：系统性地评估代理性能
- **安全性**：为可信代理内置安全模式

## 🎯 学习路径

这个速成课程通过实践教程涵盖Google ADK的基本概念：

### 📚 **教程**

1. **[1_starter_agent](./1_starter_agent/README.md)** - 您的第一个ADK代理
   - 基本代理创建
   - 理解ADK工作流
   - 简单文本处理

2. **[2_model_agnostic_agent](./2_model_agnostic_agent/README.md)** - 模型无关代理开发
   - Google Gemini模型（AI Studio和Vertex AI）
   - Anthropic Claude集成
   - OpenAI GPT集成

3. **[3_structured_output_agent](./3_structured_output_agent/README.md)** - 结构化输出代理
   - JSON模式输出
   - 数据验证
   - 类型安全响应

4. **[4_tool_using_agent](./4_tool_using_agent/README.md)** - 工具使用代理
   - 内置工具
   - 自定义函数工具
   - 第三方工具集成
   - MCP工具

## 🛠️ 先决条件

开始之前，请确保您有：

- Python 3.9+
- Google Cloud账户（用于Vertex AI）
- Google AI Studio API密钥（用于Gemini）
- 基本的Python编程知识

## 🚀 快速开始

1. **克隆仓库**
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd ai_agent_framework_crash_course/google_adk_tutorials
   ```

2. **安装依赖**
   ```bash
   pip install -r requirements.txt
   ```

3. **设置API密钥**
   ```bash
   export GOOGLE_API_KEY="your-google-api-key"
   export ANTHROPIC_API_KEY="your-anthropic-api-key"
   export OPENAI_API_KEY="your-openai-api-key"
   ```

4. **开始第一个教程**
   ```bash
   cd 1_starter_agent
   python starter_agent.py
   ```

## 📖 教程概述

### 初学者级别
- **入门代理**：学习ADK基础知识
- **模型无关代理**：使用不同的LLM提供商

### 中级
- **结构化输出**：处理JSON和类型化响应
- **工具集成**：为代理添加功能

### 高级
- **多代理系统**：协调多个专业代理
- **自定义工具**：构建专门的工具和集成

## 🎯 学习目标

完成这个速成课程后，您将能够：

- 使用Google ADK创建基本AI代理
- 集成多个LLM提供商
- 实现结构化输出和数据验证
- 为代理添加工具和功能
- 构建多代理系统
- 部署生产就绪的代理

## 📚 其他资源

- [Google ADK官方文档](https://ai.google.dev/agentic)
- [Google AI Studio](https://aistudio.google.com/)
- [Vertex AI](https://cloud.google.com/vertex-ai)
- [社区示例](https://github.com/google/adk-examples)

## 🤝 贡献

欢迎贡献！请随时提交问题、功能请求或拉取请求。

## 📄 许可证

本项目采用MIT许可证。详情请见LICENSE文件。
