# Smart Domain Generator 🚀

[![English](https://img.shields.io/badge/lang-English-blue.svg)](README.md) [![中文](https://img.shields.io/badge/lang-中文-red.svg)](README-zh.md) [![日本語](https://img.shields.io/badge/lang-日本語-green.svg)](README-ja.md) [![X](https://img.shields.io/badge/X-%40suzukaze__haduki-000000?logo=x&logoColor=white)](https://x.com/suzukaze_haduki) [![GitHub Sponsors](https://img.shields.io/badge/GitHub%20Sponsors-ea4aaa?logo=githubsponsors&logoColor=white)](https://github.com/sponsors/houko)

AI-powered intelligent domain name generation and management platform that helps you find the perfect domain for your projects.

<div align="center">

[![Next.js](https://img.shields.io/badge/Next.js-14.2.5-black?style=flat-square&logo=next.js)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.5.0-blue?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.4-38B2AC?style=flat-square&logo=tailwind-css)](https://tailwindcss.com/)
[![Supabase](https://img.shields.io/badge/Supabase-Database-green?style=flat-square&logo=supabase)](https://supabase.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

[Live Demo](https://smart-domain.com) | [API Documentation](docs/API.md) | [Contributing](#-contributing)

</div>

## ✨ Features

### 🤖 AI-Powered Intelligence
- **Smart Domain Generation**: Leverages OpenAI GPT-4 for intelligent naming suggestions
- **Multiple Strategies**: Direct combination, concept fusion, neologism creation, and cultural adaptation
- **Context Understanding**: Analyzes your project description to generate relevant names

### 🔍 Domain Management
- **Real-time Availability**: Batch domain availability checking with pricing comparison
- **Multi-registrar Support**: Compare prices across different domain registrars
- **Favorites System**: Save, organize, and track your preferred domain names
- **Search History**: Keep track of all your searches and results

### 🌐 International Support
- **Multi-language**: Full support for English, Chinese (Simplified), and Japanese
- **Cultural Adaptation**: Domain suggestions adapted for different markets
- **RTL Support**: Ready for right-to-left languages

### 🔐 Developer Features
- **REST API**: Complete API for programmatic access
- **API Key Management**: Generate and manage multiple API keys
- **Usage Analytics**: Track API usage with detailed metrics
- **Rate Limiting**: Built-in protection against abuse

### 🎨 Modern UI/UX
- **Responsive Design**: Beautiful interface that works on all devices
- **PWA Support**: Install as a Progressive Web App
- **Dark/Light Theme**: Automatic theme switching
- **Accessibility**: WCAG 2.1 compliant

## 🛠 Tech Stack

### Frontend
- **Framework**: [Next.js 14](https://nextjs.org/) with App Router
- **Language**: [TypeScript](https://www.typescriptlang.org/) for type safety
- **UI Library**: [Shadcn/ui](https://ui.shadcn.com/) + [Radix UI](https://www.radix-ui.com/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) for utility-first CSS
- **Internationalization**: [next-intl](https://next-intl-docs.vercel.app/) for i18n

### Backend
- **Database**: [Supabase](https://supabase.com/) (PostgreSQL)
- **Authentication**: Supabase Auth with Google OAuth
- **API**: RESTful API with TypeScript
- **Caching**: Redis for performance optimization

### AI & External APIs
- **AI Models**: OpenAI GPT-4 for domain generation
- **Domain Checking**: GoDaddy API for availability and pricing
- **Analytics**: Statsig for feature flags and analytics

### DevOps
- **Monorepo**: [Turborepo](https://turbo.build/) for efficient builds
- **Deployment**: [Vercel](https://vercel.com/) for seamless deployment
- **CI/CD**: GitHub Actions for automated testing and deployment

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ and pnpm
- Supabase account and project
- OpenAI API key
- (Optional) GoDaddy API credentials for real domain checking

### 1. Clone and Install
```bash
git clone https://github.com/houko/smart-domain.git
cd smart-domain
pnpm install
```

### 2. Environment Setup
Copy the environment template and fill in your credentials:
```bash
cp apps/web/.env.example apps/web/.env.local
```

Required environment variables:
```env
# Database (Required)
NEXT_PUBLIC_SUPABASE_URL=your_supabase_project_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key

# AI Generation (Required)
OPENAI_API_KEY=your_openai_api_key

# Application URL (Required for production)
NEXT_PUBLIC_APP_URL=https://your-domain.com

# Domain Checking (Optional - uses mock data if not provided)
GODADDY_API_KEY=your_godaddy_api_key
GODADDY_API_SECRET=your_godaddy_api_secret

# Analytics (Optional)
NEXT_PUBLIC_STATSIG_CLIENT_KEY=your_statsig_client_key
```

### 3. Database Setup
Set up your Supabase database using the provided SQL files:
```bash
# Run database migrations
psql -h your-supabase-host -d postgres -f apps/web/sql/setup.sql
```

### 4. Run Development Server
```bash
pnpm dev
```

Visit `http://localhost:3000` to see your application running!

## 📁 Project Structure

```
smart-domain/
├── apps/
│   └── web/                 # Next.js application
│       ├── src/
│       │   ├── app/         # App Router pages
│       │   ├── components/  # React components
│       │   ├── lib/         # Utility functions
│       │   └── types/       # TypeScript definitions
│       ├── messages/        # Internationalization files
│       └── sql/             # Database schemas
├── packages/
│   ├── ai/                  # AI generation logic
│   └── domain/              # Domain checking utilities
└── docs/                    # Documentation
```

## 🔧 Configuration

### Database Schema
The application uses PostgreSQL with the following main tables:
- `users` - User profiles and authentication
- `favorites` - Saved domain names
- `search_history` - Search records
- `api_keys` - API key management
- `usage_stats` - Analytics and usage tracking

### API Routes
- `POST /api/generate` - Generate domain suggestions
- `GET /api/v1/favorites` - Get user favorites
- `POST /api/v1/favorites` - Add to favorites
- `GET /api/v1/history` - Get search history
- `GET /api/v1/stats` - Get usage statistics

See [API Documentation](docs/API.md) for complete API reference.

## 🌍 Internationalization

Adding a new language:

1. Create translation file:
```bash
cp apps/web/messages/en.json apps/web/messages/[locale].json
```

2. Update `i18n.ts` configuration:
```typescript
export const locales = ['en', 'zh', 'ja', 'your-locale'] as const;
```

3. Translate the JSON file and test:
```bash
pnpm dev
```

## 🧪 Testing

Run the test suite:
```bash
# Unit tests
pnpm test

# E2E tests
pnpm test:e2e

# Type checking
pnpm type-check

# Linting
pnpm lint
```

## 📦 Deployment

### Vercel (Recommended)
1. Connect your GitHub repository to Vercel
2. Set environment variables in Vercel dashboard
3. Deploy automatically on push to main branch

### Docker
```bash
# Build Docker image
docker build -t smart-domain .

# Run container
docker run -p 3000:3000 --env-file .env.local smart-domain
```

### Manual Deployment
```bash
# Build for production
pnpm build

# Start production server
pnpm start
```

## 🤝 Contributing

We welcome contributions! Please read our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Workflow
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes and add tests
4. Commit using conventional commits: `git commit -m "feat: add amazing feature"`
5. Push to your branch: `git push origin feature/amazing-feature`
6. Open a Pull Request

### Code Style
- Use TypeScript for all new code
- Follow the existing code style (Prettier + ESLint)
- Write tests for new features
- Update documentation as needed

## 📖 Documentation

- [API Documentation](docs/API.md) - Complete API reference
- [Deployment Guide](docs/DEPLOYMENT.md) - Production deployment
- [Contributing Guide](CONTRIBUTING.md) - How to contribute
- [Changelog](CHANGELOG.md) - Version history

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [OpenAI](https://openai.com/) for powerful AI capabilities
- [Supabase](https://supabase.com/) for the amazing backend platform
- [Vercel](https://vercel.com/) for seamless deployment
- [Shadcn/ui](https://ui.shadcn.com/) for beautiful UI components

## 🔗 Links

- **Live Demo**: [https://smart-domain.com](https://smart-domain.com)
- **Issues**: [GitHub Issues](https://github.com/houko/smart-domain/issues)
- **Discussions**: [GitHub Discussions](https://github.com/houko/smart-domain/discussions)

---

<div align="center">
Made with ❤️ by the Smart Domain team
<br />
<a href="https://github.com/houko/smart-domain/stargazers">⭐ Star us on GitHub</a>
</div>