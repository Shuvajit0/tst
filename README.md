# YouTube ScriptForge AI - Comprehensive SaaS Application

A modern, production-ready SaaS web application for generating professional YouTube video scripts using AI.

## Features

### Core Functionality
- **AI-Powered Script Generation**: Generate complete YouTube video scripts in seconds
- **Multiple Configuration Options**:
  - Video Length (Short: 30-60 seconds, Long: 8-12 minutes)
  - Content Type (Tutorial, Storytelling, Review, Vlog)
  - Tone (Funny, Serious, Professional, Storytelling, Motivational)
  - Language (English, Spanish, French, German, Portuguese)
  - Additional Notes for customization

### Generated Output
- 5 catchy, SEO-optimized title options
- Strong hook (first 30-60 seconds)
- Complete script divided into sections with timestamps
- Natural ending with call-to-action
- Visual/B-roll suggestions throughout

### User Features
- User authentication (Email/Password + Google OAuth ready)
- Dashboard with recent scripts
- Script editor and viewer with syntax highlighting
- Copy-to-clipboard functionality
- Download scripts as .txt (extensible for .docx)
- Save scripts to account for later access

### Subscription Plans
- **Free Plan**: 3 scripts/day, English only
- **Starter Plan** ($8/month): 100 scripts/month, 3+ languages
- **Pro Plan** ($18/month): Unlimited scripts, all features

### Design & UX
- Dark mode (default) and light mode support
- Responsive design (mobile, tablet, desktop)
- Modern, minimal UI with rounded cards and soft shadows
- Gradient accents (pink/purple) for YouTube creator vibes
- Accessible form inputs and error handling

## Tech Stack

### Frontend
- **Framework**: Next.js 15+ with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Components**: React with custom UI library
- **State Management**: Zustand
- **Form Handling**: React Hook Form
- **Icons**: Lucide React
- **HTTP Client**: Axios

### Backend
- **API Routes**: Next.js API routes
- **Database**: Supabase (PostgreSQL)
- **Authentication**: Supabase Auth + NextAuth.js ready
- **AI Integration**: OpenAI API (configurable for other providers)

### DevTools
- **Linting**: ESLint
- **Package Manager**: npm
- **Version Control**: Git

## Getting Started

### Prerequisites
- Node.js 18+
- npm or pnpm
- Supabase account (free tier available)
- OpenAI API key (for script generation)

### Installation

1. **Navigate to project**:
```bash
cd scriptforge
```

2. **Set up environment variables**:
```bash
cp .env.example .env.local
```

Fill in your actual values:
- `NEXT_PUBLIC_SUPABASE_URL`: Your Supabase project URL
- `NEXT_PUBLIC_SUPABASE_ANON_KEY`: Your Supabase anon key
- `AI_API_KEY`: Your OpenAI API key

3. **Run development server**:
```bash
npm run dev
```

Visit `http://localhost:3000`

### Build for Production

```bash
npm run build
npm start
```

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.
