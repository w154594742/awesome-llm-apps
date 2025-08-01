这是一个使用[`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app)引导创建的[Next.js](https://nextjs.org)项目。

## 开始使用

首先，运行开发服务器：

```bash
npm run dev
# 或
yarn dev
# 或
pnpm dev
# 或
bun dev
```

在浏览器中打开[http://localhost:3000](http://localhost:3000)查看结果。

您可以通过修改`app/page.tsx`开始编辑页面。文件编辑时页面会自动更新。

此项目使用[`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts)自动优化和加载[Geist](https://vercel.com/font)，这是Vercel的新字体系列。

## 了解更多

要了解更多关于Next.js的信息，请查看以下资源：

- [Next.js文档](https://nextjs.org/docs) - 了解Next.js功能和API。
- [学习Next.js](https://nextjs.org/learn) - 交互式Next.js教程。

您可以查看[Next.js GitHub仓库](https://github.com/vercel/next.js) - 欢迎您的反馈和贡献！

## 部署

部署Next.js应用最简单的方法是使用来自Next.js创建者的[Vercel平台](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme)。

查看我们的[Next.js部署文档](https://nextjs.org/docs/app/building-your-application/deploying)了解更多详情。

## TripCraft AI前端

这个Next.js应用程序是TripCraft AI旅行规划系统的前端界面。它提供了一个现代化、响应式的用户界面，让用户能够：

### 主要功能
- **旅行偏好输入**：直观的表单收集用户的旅行需求
- **实时规划进度**：显示AI代理的工作进展
- **交互式行程展示**：美观的行程展示和编辑界面
- **响应式设计**：在所有设备上都有良好的用户体验

### 技术特性
- **现代React**：使用最新的React功能和钩子
- **TypeScript**：类型安全的开发体验
- **Tailwind CSS**：实用优先的CSS框架
- **组件化架构**：可重用和可维护的组件结构

### 开发环境设置
1. 确保已安装Node.js 18+
2. 安装依赖：`npm install`
3. 配置环境变量（如果需要）
4. 运行开发服务器：`npm run dev`

### 生产部署
- 构建应用：`npm run build`
- 启动生产服务器：`npm start`
- 或部署到Vercel、Netlify等平台
