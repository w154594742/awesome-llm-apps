# 💻 使用o3-mini和Gemini的多模态AI编程代理团队

一个AI驱动的Streamlit应用程序，作为您的个人编程助手，由基于新的o3-mini模型构建的多个代理提供支持。您可以上传编程问题的图像或用文本描述它，AI代理将分析、生成最优解决方案，并在沙盒环境中执行。

## 功能特性

#### 多模态问题输入
- 上传编程问题图像（支持PNG、JPG、JPEG）
- 用自然语言输入问题
- 从图像自动提取问题
- 交互式问题处理

#### 智能代码生成
- 生成具有最佳时间/空间复杂度的最优解决方案
- 清洁、有文档的Python代码输出
- 类型提示和适当的文档
- 边缘情况处理

#### 安全代码执行
- 沙盒代码执行环境
- 实时执行结果
- 错误处理和解释
- 30秒执行超时保护

#### 多代理架构
- 视觉代理（Gemini-2.0-flash）用于图像处理
- 编程代理（OpenAI o3-mini）用于解决方案生成
- 执行代理（OpenAI）用于代码运行和结果分析
- E2B沙盒用于安全代码执行

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/multi_agent_apps/agent_teams/multimodal_coding_agent_team
   
   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥**
   
   您需要以下API密钥：
   ```bash
   export OPENAI_API_KEY="your-openai-api-key"
   export GOOGLE_API_KEY="your-google-api-key"
   export E2B_API_KEY="your-e2b-api-key"
   ```

3. **运行应用程序**
   ```bash
   streamlit run multimodal_coding_agent_team.py
   ```

4. **使用应用程序**
   - 上传编程问题的图像或输入文本描述
   - 让AI代理团队分析问题
   - 查看生成的解决方案和执行结果

## 工作原理

1. **问题分析**：视觉代理处理图像或文本输入
2. **解决方案生成**：编程代理使用o3-mini生成最优代码
3. **代码执行**：执行代理在安全沙盒中运行代码
4. **结果分析**：提供执行结果和性能分析

## 主要功能

- **多模态输入**：支持图像和文本输入
- **智能分析**：深度理解编程问题
- **最优解决方案**：生成高效的代码解决方案
- **安全执行**：在隔离环境中测试代码
- **实时反馈**：即时查看执行结果

## 应用场景

- 编程学习和练习
- 算法问题解决
- 代码审查和优化
- 编程竞赛准备
- 技术面试练习
- 代码调试和测试

## 系统要求

- Python 3.8+
- OpenAI API密钥（o3-mini访问）
- Google API密钥（Gemini访问）
- E2B API密钥（沙盒执行）
- 稳定的互联网连接

## 注意事项

- 代码执行在安全沙盒中进行
- 执行时间限制为30秒
- 支持的编程语言主要是Python
- 图像质量影响问题识别准确性
