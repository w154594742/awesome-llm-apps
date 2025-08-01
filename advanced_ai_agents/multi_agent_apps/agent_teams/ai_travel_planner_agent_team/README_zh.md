# ✈️ TripCraft AI

**您的旅程，用智能完美打造。**

旅行规划令人不知所措——需要同时处理数十个标签页，比较相互矛盾的信息，花费数小时才能开始。TripCraft AI让这些烦恼消失。它是一个多代理AI系统，将简单的输入转化为完整的旅行行程。描述您理想的旅行，它会自动处理航班、酒店、活动和预算。

## 🎯 目标

让旅行规划变得轻松和个性化。没有压力，没有无休止的研究——只有一个专门为您量身定制的计划。

---

## ⚙️ 工作原理

1. **🎯 输入您的愿景** - 填写包含目的地、日期、预算、旅行风格和偏好的表单
2. **🤖 AI代理协作** - 专业代理并行处理航班、酒店、活动和预算
3. **🗺️ 获取您的行程** - 收到包含预订、费用和推荐的完整逐日计划

### 主要功能
- **个性化规划** - 根据您的旅行风格和兴趣量身定制
- **隐藏宝石发现** - 使用高级搜索超越典型的旅游景点
- **智能优化** - 平衡成本、时间和体验
- **完整套餐** - 从航班到餐饮推荐的一切

---

## 🛠️ 技术栈

**前端：** Next.js, React, TypeScript
**后端：** Python, FastAPI, PostgreSQL
**AI代理：** OpenAI GPT-4, LangChain
**搜索：** Tavily API, Google Places API
**部署：** Vercel, Railway

---

## 🚀 快速开始

### 先决条件
- Node.js 18+
- Python 3.9+
- PostgreSQL数据库

### 安装

1. **克隆仓库**
   ```bash
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/multi_agent_apps/agent_teams/ai_travel_planner_agent_team
   ```

2. **设置后端**
   ```bash
   cd backend
   pip install -r requirements.txt
   ```

3. **设置前端**
   ```bash
   cd frontend
   npm install
   ```

4. **环境配置**
   创建`.env`文件：
   ```env
   OPENAI_API_KEY=your_openai_key
   TAVILY_API_KEY=your_tavily_key
   GOOGLE_PLACES_API_KEY=your_google_places_key
   DATABASE_URL=your_postgresql_url
   ```

5. **运行应用程序**
   ```bash
   # 启动后端
   cd backend && uvicorn main:app --reload
   
   # 启动前端
   cd frontend && npm run dev
   ```

---

## 🤖 AI代理架构

### 🛫 航班代理
- 搜索最佳航班选项
- 比较价格和时间
- 考虑偏好（直飞、航空公司等）

### 🏨 住宿代理
- 根据预算和位置查找酒店
- 评估评级和便利设施
- 优化位置便利性

### 🎯 活动代理
- 发现当地景点和体验
- 匹配兴趣和旅行风格
- 包含隐藏宝石和当地推荐

### 💰 预算代理
- 跟踪所有费用
- 优化成本分配
- 提供预算替代方案

---

## 📱 功能

- **智能表单** - 直观的旅行偏好收集
- **实时规划** - 观看AI代理实时工作
- **详细行程** - 逐日计划，包含时间和成本
- **可定制选项** - 调整和完善建议
- **导出功能** - 下载PDF或分享行程

---

## 🎨 用户体验

1. **简单输入** - 最少的表单字段，最大的个性化
2. **透明过程** - 查看每个代理的工作进展
3. **即时结果** - 几分钟内获得完整计划
4. **易于调整** - 一键修改任何建议

---

## 🔮 未来功能

- **实时价格跟踪** - 监控价格变化
- **协作规划** - 与朋友一起规划
- **移动应用** - 旅行期间的原生体验
- **AI聊天助手** - 旅行期间的实时帮助

---

## 🤝 贡献

欢迎贡献！请查看我们的贡献指南并提交拉取请求。

## 📄 许可证

MIT许可证 - 详情请见LICENSE文件。
