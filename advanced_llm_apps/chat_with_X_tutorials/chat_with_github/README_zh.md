## 💬 与GitHub仓库聊天

仅用30行Python代码就能实现与GitHub仓库聊天的RAG LLM应用。该应用使用检索增强生成（RAG）基于指定GitHub仓库的内容为问题提供准确答案。

### 功能特性

- 提供GitHub仓库名称作为输入
- 询问关于GitHub仓库内容的问题
- 使用OpenAI的API和Embedchain获得准确答案

### 如何开始？

1. 克隆GitHub仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd advanced_llm_apps/chat_with_X_tutorials/chat_with_github
```
2. 安装所需依赖：

```bash
pip install -r requirements.txt
```
3. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)（或您选择的LLM提供商）并获取您的API密钥。

4. 获取您的GitHub访问令牌

- 创建一个[个人访问令牌](https://docs.github.com/en/enterprise-server@3.6/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token)，具有访问所需GitHub仓库的必要权限。

4. 运行Streamlit应用
```bash
streamlit run chat_github.py
```

### 工作原理？

- 应用提示用户输入他们的OpenAI API密钥，用于验证对OpenAI API的请求。
