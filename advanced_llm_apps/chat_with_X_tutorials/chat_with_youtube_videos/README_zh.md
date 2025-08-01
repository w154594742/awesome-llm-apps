## 📽️ 与YouTube视频聊天 

使用OpenAI的gpt-4o、mem0/embedchain作为记忆和youtube-transcript-api与YouTube视频聊天的RAG LLM应用。该应用使用检索增强生成（RAG）基于上传视频的内容为问题提供准确答案。

### 功能特性

- 输入YouTube视频URL
- 询问关于视频内容的问题
- 使用RAG和选定的LLM获得准确答案

### 如何开始？

1. 克隆GitHub仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/chat_with_X_tutorials/chat_with_youtube_videos
```
2. 安装所需依赖：

```bash
pip install -r requirements.txt
```
3. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)（或您选择的LLM提供商）并获取您的API密钥。

4. 运行Streamlit应用
```bash
streamlit run chat_youtube.py
