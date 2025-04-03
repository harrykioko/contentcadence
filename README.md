# ContentCadence

<div align="center">
  <img src="public/images/contentcadence-logo.png" alt="ContentCadence Logo" width="200"/>
  <h3>AI-Powered Content Calendar & Scheduler</h3>
  <p>Plan, create, and schedule optimized content across multiple platforms with AI assistance</p>
  
  <div>
    <img src="https://img.shields.io/badge/Next.js-14-black" alt="Next.js 14" />
    <img src="https://img.shields.io/badge/TypeScript-5.3-blue" alt="TypeScript 5.3" />
    <img src="https://img.shields.io/badge/Tailwind-3.3-38bdf8" alt="Tailwind 3.3" />
    <img src="https://img.shields.io/badge/License-MIT-green" alt="License MIT" />
  </div>
</div>

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Development Workflow](#-development-workflow)
- [API Documentation](#-api-documentation)
- [Environment Variables](#-environment-variables)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

## 🚀 Overview

ContentCadence is an AI-powered content calendar and scheduling tool designed to help content creators, marketers, and small businesses plan, create, and schedule optimized content across multiple social media platforms. By leveraging artificial intelligence, ContentCadence provides trend analysis, content suggestions, and optimal posting time recommendations to maximize engagement and save time.

### Why ContentCadence?

- **Save Time**: Automate content planning and scheduling
- **Increase Engagement**: Post at optimal times with AI-recommended content
- **Centralize Workflow**: Manage all platforms in one place
- **Collaborate Effectively**: Work with team members seamlessly
- **Data-Driven Decisions**: Track performance and optimize strategy

## ✨ Features

### AI Content Planning
- Trend analysis for topic suggestions in specific niches
- Content idea generation based on user's brand and audience
- Content type recommendations (video, image, text, etc.)
- Customizable content categories and themes

### Smart Scheduling
- Optimal posting time recommendations based on platform algorithms
- Unified calendar view across multiple platforms
- Drag-and-drop content rescheduling
- Recurring content patterns and templates

### Platform Integration
- Support for major platforms (Instagram, Twitter, LinkedIn, Facebook, TikTok)
- Preview of how content will appear on each platform
- Platform-specific content recommendations
- Cross-platform content repurposing suggestions

### Content Performance Analytics
- Basic engagement metrics tracking
- Content performance comparison
- Best performing content types and topics
- Audience growth correlation

### Collaboration Tools
- Team member access with role-based permissions
- Comment and feedback system on planned content
- Content approval workflows
- Shared content library

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS with shadcn/ui components
- **State Management**: React Context API + SWR for data fetching
- **Forms**: React Hook Form with Zod validation

### Backend
- **API Framework**: Next.js API routes
- **Database**: Supabase (PostgreSQL)
- **Authentication**: NextAuth.js with multiple providers
- **File Storage**: Supabase Storage
- **Serverless Functions**: Vercel Edge Functions

### AI Components
- **Content Trend Analysis**: OpenAI API (GPT-4)
- **Scheduling Optimization**: Custom algorithm with historical data
- **Content Suggestions**: OpenAI API with fine-tuned prompts

### Third-Party Integrations
- **Social Media**: Twitter/X API, Instagram Graph API, LinkedIn API, Facebook Graph API
- **Analytics**: Vercel Analytics + custom event tracking
- **Payments**: Stripe Subscription API
- **Email**: Resend for transactional emails

## 🏁 Getting Started

### Prerequisites

- Node.js 18.0 or later
- npm or yarn
- Git
- Supabase account
- OpenAI API key
- Stripe account (for subscription features)
- Social media developer accounts (for platform integrations)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/contentcadence.git
   cd contentcadence
   ```

2. Install dependencies:
   ```bash
   npm install
   # or
   yarn install
   ```

3. Set up environment variables:
   ```bash
   cp .env.example .env.local
   # Edit .env.local with your API keys and configuration
   ```

4. Set up the database:
   ```bash
   # Run the database migrations
   npx supabase migration up
   ```

5. Run the development server:
   ```bash
   npm run dev
   # or
   yarn dev
   ```

6. Open [http://localhost:3000](http://localhost:3000) in your browser to see the application.

## 📂 Project Structure

```
contentcadence/
├── app/                      # Next.js app directory
│   ├── api/                  # API routes
│   ├── auth/                 # Authentication pages
│   ├── calendar/             # Calendar view
│   ├── dashboard/            # Dashboard pages
│   ├── settings/             # Settings pages
│   ├── layout.tsx            # Root layout
│   └── page.tsx              # Landing page
├── components/               # Reusable components
│   ├── ui/                   # UI components
│   ├── calendar/             # Calendar components
│   ├── content/              # Content components
│   ├── analytics/            # Analytics components
│   └── auth/                 # Authentication components
├── lib/                      # Utility functions
│   ├── api/                  # API utilities
│   ├── auth/                 # Auth utilities
│   ├── db/                   # Database utilities
│   ├── ai/                   # AI utilities
│   └── utils/                # General utilities
├── public/                   # Static assets
├── styles/                   # Global styles
├── types/                    # TypeScript types
├── migrations/               # Database migrations
├── .env.example              # Environment variables example
├── next.config.js            # Next.js configuration
├── package.json              # Project dependencies
├── tailwind.config.js        # Tailwind configuration
└── tsconfig.json             # TypeScript configuration
```

## 🔄 Development Workflow

### Branch Strategy

- `main`: Production-ready code
- `develop`: Integration branch for feature development
- `feature/*`: Individual feature branches
- `bugfix/*`: Bug fix branches
- `release/*`: Release preparation branches

### Commit Conventions

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification:

- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, etc.)
- `refactor`: Code changes that neither fix bugs nor add features
- `test`: Adding or updating tests
- `chore`: Changes to the build process or auxiliary tools

Example: `feat(calendar): add drag-and-drop functionality`

### Pull Request Process

1. Create a feature branch from `develop`
2. Implement your changes
3. Write or update tests
4. Update documentation
5. Submit a pull request to `develop`
6. Request review from at least one team member
7. Address review comments
8. Merge after approval

## 📚 API Documentation

### Authentication

- `POST /api/auth/signup` - Create new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/session` - Get current session
- `POST /api/auth/logout` - Logout user

### Platforms

- `GET /api/platforms` - List connected platforms
- `POST /api/platforms` - Connect new platform
- `DELETE /api/platforms/:id` - Disconnect platform
- `PUT /api/platforms/:id/refresh` - Refresh platform tokens

### Content

- `GET /api/content` - List content items
- `POST /api/content` - Create content item
- `GET /api/content/:id` - Get content details
- `PUT /api/content/:id` - Update content
- `DELETE /api/content/:id` - Delete content
- `POST /api/content/:id/schedule` - Schedule content
- `POST /api/content/:id/publish` - Publish content immediately

### AI Features

- `POST /api/ai/trends` - Get trending topics
- `POST /api/ai/suggestions` - Get content suggestions
- `POST /api/ai/optimize` - Optimize content for platform
- `POST /api/ai/schedule` - Get optimal scheduling times

### Analytics

- `GET /api/analytics/overview` - Get analytics overview
- `GET /api/analytics/content/:id` - Get content performance
- `GET /api/analytics/platforms` - Get platform performance

### Subscription

- `POST /api/subscription/create` - Create subscription
- `PUT /api/subscription/update` - Update subscription
- `DELETE /api/subscription/cancel` - Cancel subscription
- `GET /api/subscription/plans` - Get available plans

## 🔐 Environment Variables

Create a `.env.local` file with the following variables:

```
# Next Auth
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your-nextauth-secret

# Supabase
NEXT_PUBLIC_SUPABASE_URL=your-supabase-url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your-supabase-anon-key
SUPABASE_SERVICE_ROLE_KEY=your-supabase-service-role-key

# OpenAI
OPENAI_API_KEY=your-openai-api-key

# Stripe
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your-stripe-publishable-key
STRIPE_SECRET_KEY=your-stripe-secret-key
STRIPE_WEBHOOK_SECRET=your-stripe-webhook-secret

# Social Media APIs
TWITTER_CLIENT_ID=your-twitter-client-id
TWITTER_CLIENT_SECRET=your-twitter-client-secret
INSTAGRAM_CLIENT_ID=your-instagram-client-id
INSTAGRAM_CLIENT_SECRET=your-instagram-client-secret
LINKEDIN_CLIENT_ID=your-linkedin-client-id
LINKEDIN_CLIENT_SECRET=your-linkedin-client-secret
FACEBOOK_CLIENT_ID=your-facebook-client-id
FACEBOOK_CLIENT_SECRET=your-facebook-client-secret
```

## 🚢 Deployment

### Vercel Deployment

1. Push your code to GitHub
2. Connect your repository to Vercel
3. Configure environment variables in Vercel dashboard
4. Deploy

### Manual Deployment

1. Build the application:
   ```bash
   npm run build
   # or
   yarn build
   ```

2. Start the production server:
   ```bash
   npm start
   # or
   yarn start
   ```

## 🤝 Contributing

We welcome contributions to ContentCadence! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please make sure your code follows our coding standards and includes appropriate tests.

### Code Style

- We use ESLint and Prettier for code formatting
- Run `npm run lint` to check for linting issues
- Run `npm run format` to automatically format code

### Testing

- We use Jest and React Testing Library for testing
- Run `npm test` to run all tests
- Write tests for all new features and bug fixes

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

- [Next.js](https://nextjs.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [shadcn/ui](https://ui.shadcn.com/)
- [Supabase](https://supabase.io/)
- [OpenAI](https://openai.com/)
- [Vercel](https://vercel.com/)
- [Stripe](https://stripe.com/)

---

<div align="center">
  <p>Built with ❤️ by the ContentCadence Team</p>
  <p>
    <a href="https://twitter.com/contentcadence">Twitter</a> •
    <a href="https://www.linkedin.com/company/contentcadence">LinkedIn</a> •
    <a href="https://contentcadence.com">Website</a>
  </p>
</div>
# contentcadence
