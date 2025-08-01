## 🖇️ 使用Claude 3.5 Sonnet的RAG即服务
使用Claude 3.5 Sonnet和Ragie.ai构建和部署生产就绪的检索增强生成（RAG）服务。该实现允许您用不到50行Python代码创建一个带有用户友好Streamlit界面的文档查询系统。

### 功能特性
- 生产就绪的RAG管道
- 与Claude 3.5 Sonnet集成进行响应生成
- 从URL上传文档
- 实时文档查询
- 支持快速和准确的文档处理模式

### 如何开始？

1. 克隆GitHub仓库
```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/rag_tutorials/rag-as-a-service
```

2. 安装所需依赖：

```bash
pip install -r requirements.txt
```

3. 获取您的Anthropic API和Ragie API密钥

- 注册[Anthropic账户](https://console.anthropic.com/)并获取您的API密钥
- 注册[Ragie账户](https://www.ragie.ai/)并获取您的API密钥

4. 运行Streamlit应用
