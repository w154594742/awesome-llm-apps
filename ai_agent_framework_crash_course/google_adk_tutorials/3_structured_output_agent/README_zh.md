# 🎯 教程3：结构化输出代理

欢迎来到结构化输出！本教程教您如何创建返回**类型安全、结构化数据**而不是纯文本的代理。这对于构建需要可预测数据格式的可靠应用程序至关重要。

## 🎯 您将学到什么

- **Pydantic模式**：定义带验证的数据结构
- **类型安全**：确保您的代理返回预期的数据格式
- **业务逻辑**：可靠地处理结构化数据
- **错误处理**：优雅地处理验证错误
- **实际应用**：客户支持和邮件生成

## 🧠 核心概念：结构化输出

结构化输出意味着您的代理返回**验证的数据对象**而不是原始文本：
- ✅ **类型安全**：确切知道您将收到什么数据格式
- ✅ **验证**：自动检查必需字段和数据类型
- ✅ **可靠性**：不再需要手动解析文本响应
- ✅ **集成**：易于在应用程序和数据库中使用

### 为什么需要结构化输出？
- **可预测**：始终获得相同的数据结构
- **已验证**：Pydantic确保数据正确性
- **类型化**：完整的IDE支持和类型检查
- **可扩展**：易于修改和扩展模式

## 🚀 教程结构

本教程包含**两个综合示例**：

### 1. **[客户支持票据代理](./3_1_customer_support_ticket_agent/README.md)**
- 分析客户查询
- 返回结构化的支持票据
- 包括优先级、类别和建议操作

### 2. **[邮件代理](./3_2_email_agent/README.md)**
- 生成专业邮件
- 结构化邮件组件（主题、正文、收件人）
- 邮件模板和格式化

## 🔧 基本设置

### 1. **安装依赖**
```bash
pip install google-adk pydantic
```

### 2. **基本模式定义**
```python
from pydantic import BaseModel
from typing import List, Optional

class TicketResponse(BaseModel):
    priority: str
    category: str
    summary: str
    suggested_actions: List[str]
    estimated_resolution_time: str
```

### 3. **创建结构化代理**
```python
from google.adk.agents import LlmAgent

agent = LlmAgent(
    name="structured_agent",
    instructions="分析客户查询并返回结构化的支持票据。",
    model="gemini-2.0-flash-exp",
    response_format=TicketResponse
)
```

## 📝 实践示例

### 基本结构化响应
```python
# 定义响应模式
class ProductReview(BaseModel):
    rating: int  # 1-5
    sentiment: str  # positive, negative, neutral
    key_points: List[str]
    recommendation: str

# 创建代理
review_agent = LlmAgent(
    name="review_analyzer",
    instructions="分析产品评论并提供结构化反馈。",
    model="gemini-2.0-flash-exp",
    response_format=ProductReview
)

# 使用代理
response = review_agent.run("这个产品很棒，但价格有点高。")
print(f"评分: {response.content.rating}")
print(f"情感: {response.content.sentiment}")
```

## 🎯 最佳实践

### 1. **清晰的模式定义**
```python
class EmailResponse(BaseModel):
    subject: str
    body: str
    recipients: List[str]
    priority: str = "normal"  # 默认值
    
    class Config:
        # 添加示例以获得更好的结果
        schema_extra = {
            "example": {
                "subject": "会议邀请",
                "body": "您好，我想邀请您参加...",
                "recipients": ["user@example.com"],
                "priority": "high"
            }
        }
```

### 2. **验证和错误处理**
```python
from pydantic import ValidationError

try:
    response = agent.run(user_query)
    validated_data = response.content
    print(f"有效数据: {validated_data}")
except ValidationError as e:
    print(f"验证错误: {e}")
```

### 3. **复杂嵌套结构**
```python
class Address(BaseModel):
    street: str
    city: str
    country: str

class Customer(BaseModel):
    name: str
    email: str
    address: Address
    preferences: List[str]
```

## 🔍 调试技巧

### 1. **检查原始响应**
```python
response = agent.run(query)
print(f"原始响应: {response.raw_content}")
print(f"结构化数据: {response.content}")
```

### 2. **模式验证**
```python
# 测试您的模式
test_data = {
    "priority": "high",
    "category": "technical",
    "summary": "测试摘要"
}

try:
    validated = TicketResponse(**test_data)
    print("模式有效！")
except ValidationError as e:
    print(f"模式错误: {e}")
```

## 🚀 运行示例

### 1. **客户支持票据代理**
```bash
cd 3_1_customer_support_ticket_agent
python customer_support_agent.py
```

### 2. **邮件代理**
```bash
cd 3_2_email_agent
python email_agent.py
```

## 🔄 下一步

现在您掌握了结构化输出！接下来：

1. **实验复杂模式**：尝试嵌套对象和列表
2. **添加验证**：使用Pydantic验证器
3. **集成到应用程序**：在真实项目中使用结构化数据

准备好进入下一个教程：**[4_tool_using_agent](../4_tool_using_agent/README.md)**，您将学习如何为代理添加强大的工具！

## 🤔 故障排除

### 常见问题：
1. **模式错误**：确保您的Pydantic模式定义正确
2. **验证失败**：检查必需字段和数据类型
3. **复杂结构**：从简单模式开始，逐步增加复杂性

### 有用的资源：
- [Pydantic文档](https://docs.pydantic.dev/)
- [Google ADK结构化输出指南](https://ai.google.dev/agentic)
- [类型提示指南](https://docs.python.org/3/library/typing.html)
