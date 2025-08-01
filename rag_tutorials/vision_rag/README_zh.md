# 使用Cohere Embed-4的视觉RAG 🖼️

一个强大的视觉检索增强生成（RAG）系统，利用Cohere最先进的Embed-4模型进行多模态嵌入，以及Google高效的Gemini 2.5 Flash模型来回答关于图像和PDF页面的问题。

## 功能特性

- **多模态搜索**：利用Cohere Embed-4为给定的文本问题找到语义上最相关的图像（或PDF页面图像）。
- **视觉问答**：使用Google Gemini 2.5 Flash分析检索到的图像/页面内容并生成准确、上下文感知的答案。
- **灵活的内容源**： 
    - 使用预加载的示例财务图表和信息图。
    - 上传您自己的自定义图像（PNG、JPG、JPEG）。
    - **上传PDF文档**：自动提取页面作为图像进行分析。
- **无需OCR**：直接处理PDF页面内的复杂图像和视觉元素，无需单独的文本提取步骤。
- **交互式UI**：使用Streamlit构建，便于交互，包括内容加载、问题输入和结果显示。
- **会话管理**：在会话中记住加载/上传的内容（图像和处理的PDF页面）。

## 系统要求

- Python 3.8+
- Cohere API密钥
- Google Gemini API密钥

## 如何运行

按照以下步骤设置和运行应用程序：

1.  **克隆并导航到目录** :
    ```bash
    git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
    cd awesome-llm-apps/rag_tutorials/vision_rag
    ```

2.  **安装依赖**:
    ```bash
    pip install -r requirements.txt
    ```
    *（确保您安装了最新的`PyMuPDF`以及其他要求）*

3.  **设置您的API密钥**:
    - 从以下地址获取Cohere API密钥：[https://dashboard.cohere.com/api-keys](https://dashboard.cohere.com/api-keys)
