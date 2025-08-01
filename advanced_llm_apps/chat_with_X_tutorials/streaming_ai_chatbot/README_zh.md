# 流式AI聊天机器人

一个演示**实时AI流式传输**和**对话状态管理**的最小示例，使用Motia框架。
![streaming-ai-chatbot](docs/images/streaming-ai-chatbot.gif)

## 🚀 功能特性

- **实时AI流式传输**：使用OpenAI的流式API进行逐令牌响应生成
- **实时状态管理**：对话状态实时更新，包含消息历史
- **事件驱动架构**：清晰的API → 事件 → 流式响应流程
- **最小复杂性**：仅用3个核心文件实现最大影响

## 📁 架构

```
streaming-ai-chatbot/
├── steps/
│   ├── conversation.stream.ts    # 实时对话状态
│   ├── chat-api.step.ts         # 简单聊天API端点  
│   └── ai-response.step.ts      # 流式AI响应处理器
├── package.json                 # 依赖项
├── .env.example                 # 配置模板
└── README.md                    # 此文件
```

## 🛠️ 设置

### 安装和设置

```bash
# 克隆仓库
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/chat_with_X_tutorials/streaming_ai_chatbot

# 安装依赖
npm install

# 设置环境变量
cp .env.example .env
# 编辑.env并添加您的OpenAI API密钥
```

### 环境配置

在`.env`文件中：
```env
OPENAI_API_KEY=your_openai_api_key_here
```

### 运行应用程序

```bash
npm run dev
```

应用程序将在`http://localhost:3000`启动

## 🔧 工作原理

1. **用户输入**：用户在聊天界面中输入消息
2. **API调用**：消息发送到`/api/chat`端点
3. **事件触发**：API触发`ai-response`事件
4. **流式响应**：AI响应实时流式传输回客户端
5. **状态更新**：对话状态实时更新

## 📝 核心组件

### conversation.stream.ts
管理对话状态和消息历史的实时流。

### chat-api.step.ts
处理传入聊天消息的简单API端点。

### ai-response.step.ts
处理OpenAI API集成和流式响应生成。
