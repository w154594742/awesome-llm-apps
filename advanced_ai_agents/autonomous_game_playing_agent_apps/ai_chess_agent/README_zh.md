# ♜ 白方代理 vs 黑方代理：国际象棋游戏

一个先进的国际象棋游戏系统，两个AI代理在Streamlit应用中使用Autogen相互对弈。它具有强大的走法验证和游戏状态管理功能。

## 功能特性

### 多代理架构
- 白方玩家：OpenAI驱动的战略决策者
- 黑方玩家：OpenAI驱动的战术对手
- 棋盘代理：走法合法性和游戏状态的验证代理

### 安全性和验证
- 强大的走法验证系统
- 非法走法预防
- 实时棋盘状态监控
- 安全的游戏进程控制

### 战略游戏
- AI驱动的位置评估
- 深度战术分析
- 动态策略适应
- 完整的国际象棋规则实现


### 如何开始？

1. 克隆GitHub仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/ai_agent_tutorials/ai_chess_agent
```

2. 安装所需依赖：

```bash
pip install -r requirements.txt
```

3. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)并获取您的API密钥。

4. 运行国际象棋游戏
```bash
streamlit run ai_chess_agent.py
```

### 工作原理？

1. **游戏初始化**：设置标准国际象棋棋盘和初始位置
2. **代理交互**：白方和黑方代理轮流进行走法
3. **走法验证**：棋盘代理验证每个走法的合法性
4. **游戏状态**：实时更新和显示当前棋盘状态
5. **游戏结束**：检测将死、和棋或其他游戏结束条件
