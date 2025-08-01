# 🩻 医学影像诊断代理

一个基于agno构建的医学影像诊断代理，由Gemini 2.0 Flash提供支持，为各种扫描的医学图像提供AI辅助分析。该代理作为医学影像诊断专家，分析各种类型的医学图像和视频，提供详细的诊断洞察和解释。

## 功能特性

- **全面图像分析**
  - 图像类型识别（X光、MRI、CT扫描、超声）
  - 解剖区域检测
  - 关键发现和观察
  - 潜在异常检测
  - 图像质量评估
  - 研究和参考

## 如何运行

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd ai_agent_tutorials/ai_medical_imaging_agent

   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥**
   - 从[Google AI Studio](https://aistudio.google.com)获取Google API密钥

3. **运行应用程序**
   ```bash
   streamlit run ai_medical_imaging.py
   ```

## 分析组件

- **图像类型和区域**
  - 识别成像模式
  - 指定解剖区域

- **关键发现**
  - 系统性观察列表
  - 详细外观描述
  - 异常突出显示

- **诊断评估**
  - 潜在诊断排名
  - 鉴别诊断
  - 严重程度评估

- **患者友好解释**
  - 简化术语
  - 详细的第一性原理解释
  - 视觉参考点

## 注意事项

- 使用Gemini 2.0 Flash进行分析
- 需要稳定的互联网连接
- 免费API使用成本 - Google每天提供1,500次免费请求！
- 仅用于教育和开发目的
- 不能替代专业医学诊断

## 免责声明

此工具仅用于教育和信息目的。所有分析都应由合格的医疗保健专业人员审查。不要仅基于此分析做出医疗决定。
