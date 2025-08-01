# 🎮 X代理 vs O代理：井字棋游戏

一个交互式井字棋游戏，两个由不同语言模型驱动的AI代理相互竞争，基于Agno代理框架构建，使用Streamlit作为UI。

此示例展示了如何构建一个AI代理相互竞争的交互式井字棋游戏。该应用程序展示了如何：
- 在回合制游戏中协调多个AI代理
- 为不同玩家使用不同的语言模型
- 使用Streamlit创建交互式网络界面
- 处理游戏状态和走法验证
- 显示实时游戏进度和走法历史

## 功能特性
- 支持多种AI模型（GPT-4、Claude、Gemini等）
- 实时游戏可视化
- 带棋盘状态的走法历史跟踪
- 交互式玩家选择
- 游戏状态管理
- 走法验证和协调

## 如何运行？ 

1. **设置环境**
   ```bash
   # 克隆仓库
   git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
   cd advanced_ai_agents/autonomous_game_playing_agent_apps/ai_tic_tac_toe_agent

   # 安装依赖
   pip install -r requirements.txt
   ```

2. **配置API密钥**
   
   您需要为要使用的AI模型设置API密钥：
   
   ```bash
   # OpenAI
   export OPENAI_API_KEY="your-openai-api-key"
   
   # Anthropic (Claude)
   export ANTHROPIC_API_KEY="your-anthropic-api-key"
   
   # Google (Gemini)
   export GOOGLE_API_KEY="your-google-api-key"
   ```

3. **运行应用程序**
   ```bash
   streamlit run ai_tic_tac_toe_agent.py
   ```

4. **游戏玩法**
   - 为X玩家和O玩家选择AI模型
   - 点击"开始游戏"开始比赛
   - 观看AI代理轮流进行走法
   - 查看实时棋盘更新和走法历史

## 游戏流程

1. **初始化**：设置3x3棋盘和游戏状态
2. **玩家选择**：为每个玩家选择AI模型
3. **游戏循环**：
   - X代理进行走法
   - 验证走法并更新棋盘
   - 检查获胜条件
   - O代理进行走法
   - 重复直到游戏结束
4. **结果**：显示获胜者或平局
