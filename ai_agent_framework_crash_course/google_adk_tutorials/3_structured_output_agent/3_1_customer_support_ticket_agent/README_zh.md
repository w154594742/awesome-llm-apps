# 🎫 具有结构化输出的客户支持票据代理

一个演示如何使用Google的ADK（代理开发工具包）框架实现结构化客户支持票据系统的教程。此示例展示了如何使用Pydantic模式和Gemini 2.0 Flash模型创建类型安全、结构化的支持票据，包括优先级、类别和解决时间估算。

## 教程功能

- 🎫 **结构化支持票据**：
  - 学习如何创建全面的支持票据模式
  - 理解优先级和分类
  - 了解如何估算解决时间

- 🔧 **高级模式设计**：
  - 带有枚举和可选字段的复杂Pydantic模型
  - 适当的字段验证和描述
  - 类型安全的结构化响应

- 🎯 **实际应用**：
  - 实用的客户支持用例
  - 展示如何处理不同类型的支持请求
  - 演示业务流程的结构化输出

- 📊 **优先级管理**：
  - 四级优先级系统（低、中、高、紧急）
  - 基于问题描述的自动优先级分配
  - 基于类别的不同部门路由

## 🚀 开始使用

1. **设置您的环境**：
   ```bash
   # 确保您有Google API密钥
   export GOOGLE_API_KEY="your-google-api-key"
   
   # 安装依赖
   pip install google-adk pydantic
   ```

2. **运行客户支持代理**：
   ```bash
   python customer_support_agent.py
   ```

## 🏗️ 架构概述

### 支持票据模式
```python
from pydantic import BaseModel, Field
from enum import Enum
from typing import List, Optional

class Priority(str, Enum):
    LOW = "low"
    MEDIUM = "medium"
    HIGH = "high"
    CRITICAL = "critical"

class Category(str, Enum):
    TECHNICAL = "technical"
    BILLING = "billing"
    ACCOUNT = "account"
    GENERAL = "general"

class SupportTicket(BaseModel):
    priority: Priority = Field(description="票据优先级")
    category: Category = Field(description="问题类别")
    summary: str = Field(description="问题的简洁摘要")
    suggested_actions: List[str] = Field(description="建议的解决步骤")
    estimated_resolution_time: str = Field(description="预计解决时间")
    requires_escalation: bool = Field(description="是否需要升级")
    customer_sentiment: str = Field(description="客户情绪（积极/消极/中性）")
```

## 📝 示例用法

### 基本票据创建
```python
# 客户查询示例
customer_query = "我无法登录我的账户，已经尝试了多次但一直失败。"

# 代理处理
response = support_agent.run(customer_query)
ticket = response.content

print(f"优先级: {ticket.priority}")
print(f"类别: {ticket.category}")
print(f"摘要: {ticket.summary}")
print(f"建议操作: {ticket.suggested_actions}")
```

### 复杂问题处理
```python
complex_query = """
我们的生产服务器宕机了，影响了所有客户。
这是一个紧急情况，需要立即关注。
我们正在失去业务，请尽快帮助！
"""

response = support_agent.run(complex_query)
ticket = response.content

# 自动检测为紧急优先级
assert ticket.priority == Priority.CRITICAL
assert ticket.requires_escalation == True
```

## 🎯 关键功能

### 1. **智能优先级分配**
代理分析客户查询的紧急程度：
- **紧急**：服务器宕机、安全漏洞
- **高**：功能故障、付费客户问题
- **中**：一般功能问题
- **低**：功能请求、一般查询

### 2. **自动分类**
基于内容将票据路由到正确部门：
- **技术**：登录问题、错误、性能
- **账单**：付款、发票、订阅
- **账户**：个人资料、设置、权限
- **一般**：信息请求、反馈

### 3. **可操作的建议**
每个票据包含具体的解决步骤：
```python
suggested_actions = [
    "验证客户的登录凭据",
    "检查账户状态和权限",
    "如果问题持续存在，重置密码"
]
```

## 🔍 高级功能

### 情绪分析
代理检测客户情绪以改善服务：
```python
# 积极情绪
"感谢您的快速响应！"

# 消极情绪  
"这太令人沮丧了，我已经等了几个小时！"

# 中性情绪
"我需要帮助更新我的个人资料信息。"
```

### 升级检测
自动识别需要高级支持的复杂问题：
```python
if ticket.priority == Priority.CRITICAL or "法律" in query:
    ticket.requires_escalation = True
```

## 📊 业务价值

### 1. **效率提升**
- 自动票据分类节省时间
- 优先级排序确保紧急问题优先处理
- 结构化数据便于报告和分析

### 2. **一致性**
- 标准化的票据格式
- 可预测的数据结构
- 减少人为错误

### 3. **可扩展性**
- 易于添加新类别和优先级
- 结构化数据支持自动化工作流
- 与现有系统集成

## 🔄 下一步

1. **自定义模式**：根据您的业务需求修改票据结构
2. **集成数据库**：将票据保存到您的支持系统
3. **添加工具**：集成邮件发送、通知等功能

继续到**[邮件代理教程](../3_2_email_agent/README.md)**学习如何生成结构化邮件！
