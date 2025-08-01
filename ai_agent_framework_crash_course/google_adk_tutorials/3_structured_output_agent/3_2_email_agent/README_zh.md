# 📧 具有结构化输出的邮件生成代理

一个演示如何使用Google的ADK（代理开发工具包）框架实现结构化输出的教程。此示例使用邮件生成代理来展示如何使用Pydantic模式和Gemini 2.5 Flash模型创建类型安全、结构化的响应。

## 教程功能

- 📝 **结构化输出实现**：
  - 学习如何使用Pydantic模式进行类型安全输出
  - 理解如何定义结构化响应格式
  - 了解Google ADK如何处理结构化响应

- 🎯 **邮件生成器示例**：
  - 使用邮件生成作为用例的实际示例
  - 展示如何创建具有适当结构的专业邮件内容
  - 演示结构化输出的实际应用

- 🔧 **Google ADK最佳实践**：
  - 具有清晰指令的简单代理定义
  - 正确使用输出模式以获得可靠结果
  - 演示核心概念的最小代码库

## 🚀 开始使用

1. **设置您的环境**：
   ```bash
   cd 3_2_email_agent
   
   # 复制环境模板
   cp env.example .env
   
   # 编辑.env文件并添加您的Google API密钥
   # GOOGLE_API_KEY=your_google_api_key_here
   ```

2. **安装依赖**：
   ```bash
   pip install google-adk pydantic python-dotenv
   ```

3. **运行邮件代理**：
   ```bash
   python email_agent.py
   ```

## 🏗️ 架构概述

### 邮件响应模式
```python
from pydantic import BaseModel, Field
from typing import List, Optional

class EmailResponse(BaseModel):
    subject: str = Field(description="邮件主题行")
    body: str = Field(description="邮件正文内容")
    recipients: List[str] = Field(description="收件人邮箱地址列表")
    cc: Optional[List[str]] = Field(default=None, description="抄送收件人（可选）")
    priority: str = Field(default="normal", description="邮件优先级")
    tone: str = Field(description="邮件语调（正式/非正式/友好等）")
```

### 代理配置
```python
from google.adk.agents import LlmAgent

email_agent = LlmAgent(
    name="email_generator",
    instructions="""
    您是一个专业的邮件写作助手。根据用户的请求生成结构化的邮件内容。
    确保邮件内容专业、清晰且适合指定的语调。
    """,
    model="gemini-2.0-flash-exp",
    response_format=EmailResponse
)
```

## 📝 示例用法

### 基本邮件生成
```python
# 用户请求
request = "写一封邮件给团队，通知他们明天的会议取消了"

# 代理处理
response = email_agent.run(request)
email = response.content

print(f"主题: {email.subject}")
print(f"收件人: {email.recipients}")
print(f"正文: {email.body}")
print(f"语调: {email.tone}")
```

### 复杂邮件场景
```python
complex_request = """
写一封正式邮件给客户，解释我们的服务将在下周末进行维护，
可能会有短暂的停机时间。包括道歉和联系信息。
"""

response = email_agent.run(complex_request)
email = response.content

# 结构化输出确保所有必需字段都存在
assert email.subject is not None
assert email.body is not None
assert email.tone == "formal"
```

## 🎯 关键功能

### 1. **智能主题生成**
代理根据邮件内容自动生成相关主题：
```python
# 会议通知 → "明天会议取消通知"
# 维护通知 → "计划维护通知 - 服务暂时中断"
# 感谢邮件 → "感谢您的合作"
```

### 2. **语调适应**
根据上下文自动调整邮件语调：
- **正式**：商业通信、官方通知
- **友好**：团队内部、日常沟通
- **道歉**：服务问题、延迟通知
- **紧急**：重要通知、时间敏感信息

### 3. **收件人智能识别**
从请求中提取或推断收件人：
```python
# "发送给团队" → ["team@company.com"]
# "通知所有客户" → ["customers@company.com"]
# "发送给John和Mary" → ["john@company.com", "mary@company.com"]
```

## 🔍 高级功能

### 优先级设置
自动根据内容紧急程度设置优先级：
```python
# 紧急维护 → priority: "high"
# 日常更新 → priority: "normal"
# 信息通知 → priority: "low"
```

### 抄送建议
智能建议相关的抄送收件人：
```python
# 客户邮件可能抄送客户经理
# 技术通知可能抄送IT团队
# 财务相关可能抄送财务部门
```

### 模板识别
识别常见邮件类型并应用适当模板：
- 会议邀请
- 状态更新
- 道歉邮件
- 感谢信
- 通知公告

## 📊 业务价值

### 1. **效率提升**
- 快速生成专业邮件
- 减少写作时间
- 标准化邮件格式

### 2. **一致性保证**
- 统一的邮件结构
- 一致的专业语调
- 标准化的格式

### 3. **错误减少**
- 自动字段验证
- 结构化数据确保完整性
- 减少遗漏重要信息

## 🔧 自定义选项

### 扩展邮件模式
```python
class ExtendedEmailResponse(BaseModel):
    subject: str
    body: str
    recipients: List[str]
    attachments: Optional[List[str]] = None
    scheduled_time: Optional[str] = None
    template_type: str = Field(description="邮件模板类型")
    call_to_action: Optional[str] = None
```

### 添加验证规则
```python
from pydantic import validator

class EmailResponse(BaseModel):
    # ... 其他字段 ...
    
    @validator('recipients')
    def validate_emails(cls, v):
        for email in v:
            if '@' not in email:
                raise ValueError('无效的邮箱地址')
        return v
```

## 🔄 下一步

1. **集成邮件服务**：连接到SMTP服务器实际发送邮件
2. **添加模板库**：创建预定义的邮件模板
3. **个性化功能**：根据收件人定制邮件内容

继续到**[工具使用代理教程](../4_tool_using_agent/README.md)**学习如何为代理添加强大的工具功能！
