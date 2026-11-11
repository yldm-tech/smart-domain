# Smart Domain Generator 🚀

[English](./README.md) | 中文

基于 AI 的智能域名生成和管理系统

<div align="center">

[![Next.js](https://img.shields.io/badge/Next.js-14.2.5-black?style=flat-square&logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.5.0-blue?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38B2AC?style=flat-square&logo=tailwind-css)](https://tailwindcss.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](LICENSE)
[![X](https://img.shields.io/badge/X-%40suzukaze__haduki-000000?logo=x&logoColor=white)](https://x.com/suzukaze_haduki)
[![GitHub Sponsors](https://img.shields.io/badge/GitHub%20Sponsors-ea4aaa?logo=githubsponsors&logoColor=white)](https://github.com/sponsors/houko)

</div>

## 🌟 项目特点

### 核心功能

- 🤖 **AI 驱动生成**：利用 OpenAI GPT-4 进行智能域名建议
- 🎯 **智能命名策略**：多种生成策略包括直接组合、概念融合、创造新词、文化适配
- 🔍 **实时可用性检查**：批量域名可用性检查及价格对比
- 💰 **多注册商支持**：对比不同域名注册商的价格
- 🌐 **国际化支持**：完整支持中英文界面

### 高级功能

- 🔐 **用户认证**：通过 Supabase 实现安全的 Google OAuth 登录
- ❤️ **收藏管理**：保存、组织和跟踪您喜欢的域名
- 🔑 **API 密钥管理**：生成和管理用于程序化访问的 API 密钥
- 📊 **使用分析**：跟踪 API 使用情况并监控速率限制
- 📱 **PWA 支持**：可安装为渐进式 Web 应用以供离线访问
- 🎨 **深色模式**：美观的 UI 支持明暗主题切换

### 性能与安全

- ⚡ **优化性能**：响应时间 < 3 秒，智能缓存机制
- 🛡️ **速率限制**：内置速率限制防止滥用
- 🔒 **安全 API**：API 密钥认证和使用跟踪
- 📈 **可扩展架构**：使用 Turborepo 构建的 monorepo 管理

## 🛠 技术栈

### 前端

- **框架**: [Next.js 14](https://nextjs.org/) with App Router
- **语言**: [TypeScript](https://www.typescriptlang.org/)
- **UI 组件**: [Shadcn/ui](https://ui.shadcn.com/) + [Radix UI](https://www.radix-ui.com/)
- **样式**: [Tailwind CSS](https://tailwindcss.com/)
- **国际化**: [next-intl](https://next-intl-docs.vercel.app/)

### 后端和基础设施

- **API**: Next.js API Routes
- **认证**: [Supabase Auth](https://supabase.com/auth)
- **数据库**: PostgreSQL (通过 Supabase)
- **AI 集成**: OpenAI API
- **分析**: [Statsig](https://statsig.com/)

### 开发工具

- **包管理器**: [pnpm](https://pnpm.io/)
- **Monorepo**: [Turborepo](https://turbo.build/)
- **代码质量**: [Biome](https://biomejs.dev/)
- **部署**: Vercel

## 📁 项目结构

```bash
smart-domain/
├── apps/
│   └── web/                 # Next.js 应用
│       ├── src/
│       │   ├── app/         # App router 页面
│       │   ├── components/  # React 组件
│       │   ├── lib/         # 工具和辅助函数
│       │   └── types/       # TypeScript 定义
│       └── public/          # 静态资源
├── packages/
│   ├── ai/                  # AI 集成包
│   ├── db/                  # 数据库模型和查询
│   ├── domain/              # 域名检查逻辑
│   └── types/               # 共享 TypeScript 类型
├── docs/                    # 文档
└── scripts/                 # 实用脚本
```

## 🚀 快速开始

### 环境要求

- Node.js >= 20.0.0
- pnpm >= 9.0.0
- Supabase 账户
- OpenAI API 密钥

### 安装

1. 克隆仓库：

```bash
git clone https://github.com/yourusername/smart-domain.git
cd smart-domain
```

1. 安装依赖：

```bash
pnpm install
```

1. 设置环境变量：

```bash
cp apps/web/.env.example apps/web/.env.local
```

1. 配置您的 `.env.local`：

```env
# Supabase
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key

# OpenAI
OPENAI_API_KEY=your_openai_api_key

# App URL (生产环境)
NEXT_PUBLIC_APP_URL=https://your-domain.com

# 可选：域名检查
GODADDY_API_KEY=your_godaddy_api_key
GODADDY_API_SECRET=your_godaddy_api_secret

# 可选：分析
NEXT_PUBLIC_STATSIG_CLIENT_KEY=your_statsig_key
```

### 开发

```bash
# 启动开发服务器
pnpm dev

# 应用将在 http://localhost:3000 可用
```

### 构建

```bash
# 构建生产版本
pnpm build

# 本地运行生产版本
pnpm start
```

### 代码质量

```bash
# 格式化代码
pnpm format

# 运行 lint
pnpm lint

# 类型检查
pnpm typecheck
```

## 📱 功能概览

### 域名生成

基于您的项目描述生成创意域名：

- AI 驱动的建议及理由说明
- 多种命名策略
- 实时可用性检查
- 跨注册商价格对比

### 用户仪表板

- **收藏夹**：保存和组织您喜欢的域名
- **历史记录**：跟踪您的域名搜索历史
- **API 密钥**：生成和管理 API 访问密钥
- **使用统计**：监控您的 API 使用情况

### API 访问

域名生成的程序化访问：

```bash
POST /api/v1/generate
Authorization: Bearer your_api_key
Content-Type: application/json

{
  "description": "一个宠物主人的社交应用",
  "options": {
    "maxSuggestions": 10,
    "includePricing": true,
    "targetMarket": "global"
  }
}
```

## 🔐 认证

应用使用 Supabase Auth 和 Google OAuth 提供商：

1. 用户可以使用 Google 账户登录
2. 受保护的路由自动重定向到登录页
3. 会话管理由 Supabase 处理

## 🌍 国际化

完整支持多语言：

- 英文（默认）
- 中文

使用导航栏中的语言选择器切换语言。

## 📊 API 文档

### 端点

#### 生成域名建议

```http
POST /api/v1/generate
```

#### 健康检查

```http
GET /api/v1/health
```

#### 使用统计

```http
GET /api/v1/stats
```

### 速率限制

- **免费层级**：50 请求/天
- **认证用户**：200 请求/天
- **API 密钥用户**：基于计划

## 🚀 部署

### Vercel（推荐）

1. 将代码推送到 GitHub
2. 在 Vercel 中导入项目
3. 配置环境变量
4. 部署！

### 自托管

查看 [docs/DEPLOYMENT.md](docs/DEPLOYMENT.md) 获取详细说明。

## 🤝 贡献

我们欢迎贡献！请查看我们的[贡献指南](CONTRIBUTING.md)了解详情。

### 开发工作流

1. Fork 仓库
2. 创建您的功能分支（`git checkout -b feature/amazing-feature`）
3. 提交您的更改（`git commit -m 'Add amazing feature'`）
4. 推送到分支（`git push origin feature/amazing-feature`）
5. 开启 Pull Request

## 📄 许可证

本项目基于 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 🙏 致谢

- [Next.js](https://nextjs.org/) 提供的优秀框架
- [Shadcn/ui](https://ui.shadcn.com/) 提供的精美 UI 组件
- [OpenAI](https://openai.com/) 提供的 AI 能力
- [Supabase](https://supabase.com/) 提供的认证和数据库
- 所有贡献者和用户！

---

<div align="center">
由 Smart Domain 团队用 ❤️ 打造
</div>
