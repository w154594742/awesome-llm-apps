# 🧠 数学导师代理 – 带反馈循环的代理式RAG

该项目实现了**代理式RAG架构**来模拟数学教授，解决**JEE级别的数学问题**并提供逐步解释。系统智能地在向量数据库和网络搜索之间路由查询，应用输入/输出护栏，并结合人类反馈进行持续学习。

## 📌 功能特性

- ✅ **输入护栏**（DSPy）：仅接受学术数学问题。
- 📚 **知识库搜索**：使用**Qdrant向量数据库**和OpenAI嵌入来匹配已知问题。
- 🌐 **网络回退**：当找不到良好匹配时集成**Tavily API**。
- ✍️ **GPT-4.1解释**：生成逐步数学解决方案。
- 🛡️ **输出护栏**：过滤正确性和安全性。
- 👍 **人在回路反馈**：用户对答案评分（是/否），记录用于未来学习。
- 📊 **基准测试**：在**JEEBench**数据集上评估，可调整问题限制。
- 💻 **Streamlit UI**：带多个选项卡的交互式仪表板。

## 🚀 架构流程
<img width="465" alt="Screenshot 2025-05-04 at 3 45 58 PM" src="https://github.com/user-attachments/assets/c0a9e612-2ef0-413c-b779-c99fe9f48619" />


## 📚 知识库

- **数据集：** [JEEBench (HuggingFace)](https://huggingface.co/datasets/daman1209arora/jeebench)
- **向量数据库：** Qdrant（使用OpenAI嵌入）
- **存储：** 使用`llama-index`构建以持久化嵌入并执行top-1相似性搜索

## 🌐 网络搜索

- 当知识库不包含良好匹配时，使用**Tavily API**进行回退搜索
- 获取的内容输入到**GPT-4o**中进行清晰解释


## 🔐 护栏

- **输入护栏（DSPy）：** 仅接受与数学相关的学术问题
- **输出护栏（DSPy）：** 阻止幻觉或偏题内容


## 👨‍🏫 人在回路反馈

- Streamlit UI允许学生在看到答案后给出👍 / 👎
- 反馈记录到本地JSON文件以供未来改进

## 📊 基准测试

- 在**50个随机JEEBench数学问题**上评估
- **当前准确率：** 66%
- 基准测试结果保存到：`benchmark/results.csv`


## 🚀 演示 

使用Streamlit运行应用：

```bash
streamlit run app/streamlit.py
