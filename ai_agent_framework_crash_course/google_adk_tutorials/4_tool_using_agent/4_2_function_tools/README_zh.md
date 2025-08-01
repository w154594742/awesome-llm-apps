# ⚡ 函数工具

函数工具是您创建并集成到代理中的**自定义Python函数**。这是为代理添加特定功能的最灵活和最常用的方法。

## 🎯 您将学到什么

- **函数工具创建**：构建自定义Python函数作为工具
- **工具注册**：如何将函数注册到您的代理
- **参数处理**：管理工具输入和输出
- **错误处理**：工具中的强大错误管理
- **最佳实践**：有效函数工具的设计模式

## 🧠 核心概念：函数工具

函数工具是**具有特殊特征的Python函数**：
- **描述性文档字符串**：帮助代理理解何时使用它们
- **类型注解**：清晰的输入/输出规范
- **返回字典**：结构化、信息丰富的响应
- **错误处理**：优雅的失败管理

### 主要优势
- ✅ **最大灵活性**：创建您需要的任何功能
- ✅ **易于集成**：简单的Python函数
- ✅ **完全控制**：完全控制行为
- ✅ **调试**：易于测试和调试

## 🔧 函数工具要求

### 1. **描述性文档字符串**
```python
def calculate_area(length: float, width: float) -> dict:
    """
    计算矩形的面积。
    
    此函数接受长度和宽度参数，并返回矩形的面积。
    适用于房间测量、土地计算等场景。
    
    Args:
        length: 矩形的长度（米）
        width: 矩形的宽度（米）
    
    Returns:
        包含面积计算结果的字典
    """
    area = length * width
    return {
        "area": area,
        "unit": "平方米",
        "calculation": f"{length} × {width} = {area}"
    }
```

### 2. **类型注解**
```python
from typing import Dict, List, Optional

def analyze_numbers(numbers: List[float]) -> Dict[str, float]:
    """分析数字列表的统计信息"""
    return {
        "mean": sum(numbers) / len(numbers),
        "max": max(numbers),
        "min": min(numbers),
        "count": len(numbers)
    }
```

### 3. **错误处理**
```python
def safe_divide(a: float, b: float) -> dict:
    """安全的除法运算"""
    try:
        if b == 0:
            return {
                "error": "除数不能为零",
                "result": None
            }
        
        result = a / b
        return {
            "result": result,
            "calculation": f"{a} ÷ {b} = {result}",
            "error": None
        }
    except Exception as e:
        return {
            "error": f"计算错误: {str(e)}",
            "result": None
        }
```

## 📝 实践示例

### 基本数学工具
```python
from google.adk.agents import LlmAgent
from google.adk.tools import FunctionTool

def calculate_compound_interest(
    principal: float, 
    rate: float, 
    time: float, 
    compound_frequency: int = 1
) -> dict:
    """
    计算复利。
    
    Args:
        principal: 本金金额
        rate: 年利率（小数形式，如0.05表示5%）
        time: 投资时间（年）
        compound_frequency: 每年复利次数（默认1次）
    
    Returns:
        包含复利计算结果的字典
    """
    amount = principal * (1 + rate/compound_frequency) ** (compound_frequency * time)
    interest = amount - principal
    
    return {
        "principal": principal,
        "final_amount": round(amount, 2),
        "interest_earned": round(interest, 2),
        "rate": f"{rate*100}%",
        "time_years": time,
        "compound_frequency": compound_frequency
    }

# 创建工具
interest_tool = FunctionTool(calculate_compound_interest)

# 创建代理
finance_agent = LlmAgent(
    name="finance_agent",
    instructions="您是一个金融计算助手，可以帮助进行各种财务计算。",
    model="gemini-2.0-flash-exp",
    tools=[interest_tool]
)
```

### 数据处理工具
```python
def process_sales_data(sales_data: List[dict]) -> dict:
    """
    处理销售数据并生成报告。
    
    Args:
        sales_data: 包含销售记录的字典列表
                   每个记录应包含: amount, date, product
    
    Returns:
        销售分析报告
    """
    if not sales_data:
        return {"error": "没有提供销售数据"}
    
    total_sales = sum(item.get('amount', 0) for item in sales_data)
    product_sales = {}
    
    for item in sales_data:
        product = item.get('product', 'Unknown')
        amount = item.get('amount', 0)
        product_sales[product] = product_sales.get(product, 0) + amount
    
    best_product = max(product_sales, key=product_sales.get)
    
    return {
        "total_sales": total_sales,
        "number_of_transactions": len(sales_data),
        "average_transaction": round(total_sales / len(sales_data), 2),
        "best_selling_product": best_product,
        "product_breakdown": product_sales
    }
```

### 文本处理工具
```python
import re
from collections import Counter

def analyze_text(text: str) -> dict:
    """
    分析文本内容并提供统计信息。
    
    Args:
        text: 要分析的文本
    
    Returns:
        文本分析结果
    """
    # 基本统计
    word_count = len(text.split())
    char_count = len(text)
    sentence_count = len(re.split(r'[.!?]+', text))
    
    # 词频分析
    words = re.findall(r'\b\w+\b', text.lower())
    word_freq = Counter(words)
    most_common = word_freq.most_common(5)
    
    return {
        "word_count": word_count,
        "character_count": char_count,
        "sentence_count": sentence_count,
        "average_words_per_sentence": round(word_count / max(sentence_count, 1), 2),
        "most_common_words": most_common,
        "unique_words": len(set(words))
    }
```

## 🎯 最佳实践

### 1. **清晰的函数命名**
```python
# 好的命名
def calculate_monthly_payment(loan_amount, interest_rate, term_months):
    pass

# 避免模糊命名
def calc(a, b, c):
    pass
```

### 2. **全面的文档字符串**
```python
def convert_temperature(value: float, from_unit: str, to_unit: str) -> dict:
    """
    在不同温度单位之间转换。
    
    支持摄氏度(C)、华氏度(F)和开尔文(K)之间的转换。
    
    Args:
        value: 要转换的温度值
        from_unit: 源单位 ('C', 'F', 'K')
        to_unit: 目标单位 ('C', 'F', 'K')
    
    Returns:
        包含转换结果的字典
        
    Example:
        convert_temperature(100, 'C', 'F') 
        # 返回: {"result": 212.0, "from": "100°C", "to": "212.0°F"}
    """
```

### 3. **输入验证**
```python
def calculate_bmi(weight: float, height: float) -> dict:
    """计算身体质量指数(BMI)"""
    # 输入验证
    if weight <= 0:
        return {"error": "体重必须大于0"}
    if height <= 0:
        return {"error": "身高必须大于0"}
    if height > 3:  # 假设身高以米为单位
        return {"error": "身高似乎不合理，请使用米作为单位"}
    
    bmi = weight / (height ** 2)
    
    # BMI分类
    if bmi < 18.5:
        category = "体重不足"
    elif bmi < 25:
        category = "正常体重"
    elif bmi < 30:
        category = "超重"
    else:
        category = "肥胖"
    
    return {
        "bmi": round(bmi, 2),
        "category": category,
        "weight": weight,
        "height": height
    }
```

## 🚀 运行示例

1. **设置环境**：
   ```bash
   export GOOGLE_API_KEY="your-google-api-key"
   ```

2. **运行函数工具示例**：
   ```bash
   python function_tools_agent.py
   ```

## 🔧 调试技巧

### 1. **测试函数工具**
```python
# 在集成到代理之前测试函数
result = calculate_compound_interest(1000, 0.05, 5)
print(result)
```

### 2. **日志记录**
```python
import logging

def logged_function(x: int) -> dict:
    """带日志记录的函数"""
    logging.info(f"调用logged_function，参数: {x}")
    result = x * 2
    logging.info(f"返回结果: {result}")
    return {"result": result}
```

### 3. **性能监控**
```python
import time

def timed_calculation(n: int) -> dict:
    """监控执行时间的计算"""
    start_time = time.time()
    
    # 执行计算
    result = sum(range(n))
    
    execution_time = time.time() - start_time
    
    return {
        "result": result,
        "execution_time_seconds": round(execution_time, 4),
        "input_size": n
    }
```

## 🔄 下一步

现在您掌握了函数工具！接下来：

1. **创建复杂工具**：构建多步骤、多功能的工具
2. **工具组合**：创建使用多个函数工具的代理
3. **性能优化**：改进工具执行效率

准备好学习**[第三方工具](../4_3_thirdparty_tools/README.md)**，您将集成现有的AI框架！
