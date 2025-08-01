## 💻 网页抓取AI代理
这个Streamlit应用允许您使用OpenAI API和scrapegraphai库抓取网站。只需提供您的OpenAI API密钥，输入您想要抓取的网站URL，并指定您希望AI代理从网站中提取的内容。

### 功能特性
- 通过提供URL抓取任何网站
- 利用OpenAI的LLM（GPT-3.5-turbo或GPT-4）进行智能抓取
- 通过指定您希望AI代理提取的内容来自定义抓取任务

### 如何开始？

1. 克隆GitHub仓库

```bash
git clone https://github.com/Shubhamsaboo/awesome-llm-apps.git
cd awesome-llm-apps/advanced_tools_frameworks/web_scrapping_ai_agent
```
2. 安装所需依赖：

```bash
pip install -r requirements.txt
```
3. 获取您的OpenAI API密钥

- 注册[OpenAI账户](https://platform.openai.com/)（或您选择的LLM提供商）并获取您的API密钥。

4. 运行Streamlit应用
```bash
streamlit run ai_scrapper.py
```

### 工作原理？

- 应用提示您输入OpenAI API密钥，用于身份验证和访问OpenAI语言模型。
- 您可以为抓取任务选择所需的语言模型（GPT-3.5-turbo或GPT-4）。
- 在提供的文本输入字段中输入您想要抓取的网站URL。
- 通过输入用户提示指定您希望AI代理从网站中提取的内容。
- 应用使用提供的URL、用户提示和OpenAI配置创建SmartScraperGraph对象。
- SmartScraperGraph对象使用指定的语言模型抓取网站并提取请求的信息。
- 抓取结果在应用中显示供您查看
