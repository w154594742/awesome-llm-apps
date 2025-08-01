## 📨 与Gmail收件箱聊天 

仅用30行Python代码就能实现与Gmail聊天的RAG LLM应用。该应用使用检索增强生成（RAG）基于您Gmail收件箱的内容为问题提供准确答案。

### 功能特性

- 连接到您的Gmail收件箱
- 询问关于您邮件内容的问题
- 使用RAG和选定的LLM获得准确答案

### 安装步骤

1. 克隆仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd advanced_llm_apps/chat_with_X_tutorials/chat_with_gmail
```
2. 安装所需依赖

```bash
pip install -r requirements.txt
```

3. 设置您的Google Cloud项目并启用Gmail API：

- 访问[Google Cloud控制台](https://console.cloud.google.com/)并创建新项目。
- 导航到"APIs & Services > OAuth consent screen"并配置OAuth同意屏幕。
- 通过提供必要的应用信息发布OAuth同意屏幕。
- 启用Gmail API并创建OAuth客户端ID凭据。
- 下载JSON格式的凭据并将其保存为工作目录中的`credentials.json`。

4. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)（或您选择的LLM提供商）并获取您的API密钥。

4. 运行Streamlit应用

```bash
streamlit run chat_gmail.py
