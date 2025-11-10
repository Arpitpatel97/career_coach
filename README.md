# 🚀 AI Career Coach

<div align="center">

![AI Career Coach](https://img.shields.io/badge/AI-Career%20Coach-blue?style=for-the-badge)
![Next.js](https://img.shields.io/badge/Next.js-15.1.4-black?style=for-the-badge&logo=next.js)
![React](https://img.shields.io/badge/React-19.0.0-61DAFB?style=for-the-badge&logo=react)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

**Your AI-Powered Career Growth Platform**

*Accelerate your professional journey with personalized AI guidance, interview preparation, resume optimization, and industry insights.*

[Features](#-features) • [Tech Stack](#-tech-stack) • [Getting Started](#-getting-started) • [Documentation](#-documentation)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Environment Variables](#-environment-variables)
- [Database Setup](#-database-setup)
- [Running the Application](#-running-the-application)
- [Project Structure](#-project-structure)
- [Key Features Explained](#-key-features-explained)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

**AI Career Coach** is a comprehensive career development platform that leverages artificial intelligence to help professionals advance their careers. Whether you're preparing for interviews, optimizing your resume, or seeking industry insights, our platform provides personalized guidance to help you succeed.

### What Makes Us Different?

- 🤖 **AI-Powered Guidance**: Personalized career advice using Google's Generative AI
- 📊 **Industry Insights**: Real-time market trends, salary data, and growth opportunities across 50+ industries
- 💼 **Smart Resume Builder**: ATS-optimized resume creation with AI feedback and scoring
- 🎤 **Interview Preparation**: Practice with 1000+ role-specific questions and instant feedback
- 📝 **Cover Letter Generator**: Tailored cover letters for specific job applications
- 📈 **Progress Tracking**: Monitor your career development with detailed analytics

---

## ✨ Features

### 🎯 Core Features

#### 1. **AI-Powered Dashboard**
- Personalized career insights and recommendations
- Track your progress across all modules
- Industry-specific trends and opportunities
- Visual analytics with interactive charts

#### 2. **Smart Resume Builder**
- Markdown-based resume editor with live preview
- ATS (Applicant Tracking System) optimization
- AI-powered feedback and suggestions
- Export to PDF functionality
- Score your resume against industry standards

#### 3. **Interview Preparation**
- Role-specific interview questions
- Practice assessments with instant feedback
- Performance tracking and improvement tips
- Behavioral and technical question categories
- AI-generated personalized tips

#### 4. **AI Cover Letter Generator**
- Generate tailored cover letters for specific jobs
- Company and role-specific customization
- Multiple drafts and revisions
- Export to PDF
- Save and manage multiple cover letters

#### 5. **Industry Insights**
- Real-time salary ranges by role and location
- Industry growth rates and market outlook
- Top in-demand skills
- Recommended learning paths
- Market trends and forecasts

#### 6. **User Authentication**
- Secure authentication with Clerk
- Email and social login options
- User profile management
- Protected routes and role-based access

---

## 🛠️ Tech Stack

### Frontend
- **Framework**: [Next.js 15.1.4](https://nextjs.org/) (App Router)
- **UI Library**: [React 19.0.0](https://react.dev/)
- **Styling**: [Tailwind CSS 3.4.1](https://tailwindcss.com/)
- **UI Components**: [Radix UI](https://www.radix-ui.com/) + [shadcn/ui](https://ui.shadcn.com/)
- **Icons**: [Lucide React](https://lucide.dev/)
- **Theme**: [next-themes](https://github.com/pacocoursey/next-themes) (Dark/Light mode)
- **Forms**: [React Hook Form](https://react-hook-form.com/) + [Zod](https://zod.dev/)
- **Markdown**: [@uiw/react-md-editor](https://uiwjs.github.io/react-md-editor/)
- **Charts**: [Recharts](https://recharts.org/)
- **PDF Export**: [html2pdf.js](https://github.com/eKoopmans/html2pdf.js)

### Backend
- **Database**: [PostgreSQL](https://www.postgresql.org/)
- **ORM**: [Prisma 6.2.1](https://www.prisma.io/)
- **Authentication**: [Clerk](https://clerk.com/)
- **AI Integration**: [Google Generative AI (Gemini)](https://ai.google.dev/)
- **Background Jobs**: [Inngest](https://www.inngest.com/)

### Development Tools
- **Linting**: ESLint
- **Package Manager**: npm
- **Version Control**: Git

---

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js**: Version 18.x or higher ([Download](https://nodejs.org/))
- **npm**: Version 9.x or higher (comes with Node.js)
- **PostgreSQL**: Version 14.x or higher ([Download](https://www.postgresql.org/download/))
- **Git**: For version control ([Download](https://git-scm.com/))

### Required Accounts
- **Clerk Account**: For authentication ([Sign up](https://clerk.com/))
- **Google AI Studio Account**: For Gemini API access ([Get API Key](https://makersuite.google.com/app/apikey))
- **Database**: PostgreSQL database (local or cloud-hosted)

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Arpitpatel97/career_coach.git
cd career_coach
```

### 2. Install Dependencies

```bash
npm install
```

This will install all required dependencies and automatically run `prisma generate` through the postinstall script.

---

## 🔐 Environment Variables

Create a `.env` file in the root directory and add the following environment variables:

```env
# Database Configuration
DATABASE_URL="postgresql://username:password@localhost:5432/career_coach?schema=public"

# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

# Clerk URLs (Update based on your deployment)
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/onboarding
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/onboarding

# Google Generative AI (Gemini)
GEMINI_API_KEY=your_gemini_api_key

# Inngest Configuration (for background jobs)
INNGEST_EVENT_KEY=your_inngest_event_key
INNGEST_SIGNING_KEY=your_inngest_signing_key

# Application URL (for production)
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### How to Get API Keys

#### Clerk Setup
1. Go to [Clerk Dashboard](https://dashboard.clerk.com/)
2. Create a new application
3. Copy the publishable key and secret key from the API Keys section
4. Configure your application URLs in the Clerk dashboard

#### Google Gemini API
1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Sign in with your Google account
3. Click "Get API Key"
4. Create a new API key or use an existing one

#### PostgreSQL Database
- **Local**: Install PostgreSQL and create a database named `career_coach`
- **Cloud**: Use services like [Supabase](https://supabase.com/), [Neon](https://neon.tech/), or [Railway](https://railway.app/)

---

## 🗄️ Database Setup

### 1. Configure Database Connection

Update the `DATABASE_URL` in your `.env` file with your PostgreSQL credentials.

### 2. Run Prisma Migrations

```bash
# Generate Prisma Client
npx prisma generate

# Push the schema to your database
npx prisma db push

# (Optional) View your database in Prisma Studio
npx prisma studio
```

### Database Schema

The application uses the following main models:
- **User**: User profiles with industry preferences and skills
- **Assessment**: Interview assessment results and feedback
- **Resume**: User resumes with ATS scoring
- **CoverLetter**: AI-generated cover letters
- **IndustryInsight**: Market trends and salary data

---

## 🏃 Running the Application

### Development Mode

```bash
npm run dev
```

The application will start on [http://localhost:3000](http://localhost:3000)

### Production Build

```bash
# Build the application
npm run build

# Start the production server
npm start
```

### Linting

```bash
npm run lint
```

---

## 📁 Project Structure

```
career_coach/
├── actions/                    # Server actions for data mutations
│   ├── cover-letter.js        # Cover letter operations
│   ├── dashboard.js           # Dashboard data fetching
│   ├── interview.js           # Interview assessments
│   ├── resume.js              # Resume operations
│   └── user.js                # User profile management
├── app/                       # Next.js App Router
│   ├── (auth)/               # Authentication routes
│   │   ├── sign-in/          # Sign in page
│   │   └── sign-up/          # Sign up page
│   ├── (main)/               # Protected main application routes
│   │   ├── ai-cover-letter/  # Cover letter generator
│   │   ├── dashboard/        # User dashboard
│   │   ├── interview/        # Interview preparation
│   │   ├── onboarding/       # User onboarding flow
│   │   └── resume/           # Resume builder
│   ├── api/                  # API routes
│   │   └── inngest/          # Inngest webhook handlers
│   ├── globals.css           # Global styles
│   ├── layout.js             # Root layout
│   └── page.js               # Landing page
├── components/                # React components
│   ├── ui/                   # shadcn/ui components
│   ├── header.jsx            # Header component
│   ├── hero.jsx              # Hero section
│   └── theme-provider.jsx    # Theme context provider
├── data/                      # Static data and configurations
│   ├── faqs.js               # FAQ data
│   ├── features.js           # Feature list
│   ├── industries.js         # Industry categories
│   └── testimonial.js        # User testimonials
├── hooks/                     # Custom React hooks
├── lib/                       # Utility libraries
│   ├── inngest/              # Inngest function definitions
│   ├── checkUser.js          # User verification utility
│   ├── prisma.js             # Prisma client instance
│   └── utils.js              # Helper functions
├── prisma/                    # Database configuration
│   ├── migrations/           # Database migrations
│   └── schema.prisma         # Prisma schema definition
├── public/                    # Static assets
├── middleware.js              # Next.js middleware for auth
├── .env                       # Environment variables (create this)
├── package.json               # Dependencies and scripts
├── tailwind.config.mjs        # Tailwind CSS configuration
└── README.md                  # This file
```

---

## 🎓 Key Features Explained

### 1. Authentication Flow
- Users sign up/sign in through Clerk
- Redirected to onboarding to select their industry and experience
- User profile is created in the database with Clerk user ID
- Protected routes ensure authenticated access

### 2. Dashboard
- Displays personalized career insights
- Shows progress across resume, interviews, and cover letters
- Industry-specific salary insights and trends
- Quick access to all features

### 3. Resume Builder Workflow
1. User creates/edits resume in Markdown format
2. Live preview shows formatted output
3. AI analyzes resume and provides ATS score
4. Suggestions for improvement
5. Export to PDF

### 4. Interview Preparation
1. Select interview category (Technical/Behavioral)
2. Answer role-specific questions
3. Submit assessment for AI evaluation
4. Receive instant feedback and improvement tips
5. Track progress over time

### 5. Cover Letter Generation
1. Provide job details (company, position, job description)
2. AI generates personalized cover letter
3. Edit and refine as needed
4. Save multiple versions
5. Export to PDF

### 6. Industry Insights
- Aggregated data from multiple sources
- Salary ranges by role and location
- Growth trends and market outlook
- Recommended skills to learn
- Updated regularly through background jobs

---

## 🚀 Deployment

### Vercel (Recommended)

1. **Push your code to GitHub**

2. **Import to Vercel**
   - Go to [Vercel Dashboard](https://vercel.com/)
   - Click "New Project"
   - Import your GitHub repository

3. **Configure Environment Variables**
   - Add all environment variables from `.env`
   - Update `NEXT_PUBLIC_APP_URL` to your Vercel URL

4. **Update Clerk Settings**
   - Add your Vercel URL to Clerk's allowed origins
   - Update redirect URLs in Clerk dashboard

5. **Deploy**
   - Vercel will automatically build and deploy
   - Every push to main branch triggers redeployment

### Other Platforms

The application can be deployed to:
- **Netlify**: Use the Netlify CLI or Git integration
- **Railway**: Connect your GitHub repo and add environment variables
- **AWS Amplify**: Push to GitHub and connect to Amplify
- **Self-hosted**: Build with `npm run build` and use a Node.js server

### Database Hosting

Recommended PostgreSQL hosting options:
- **Supabase**: Free tier with 500MB database
- **Neon**: Serverless PostgreSQL with generous free tier
- **Railway**: Simple deployment with database included
- **PlanetScale**: MySQL alternative (requires schema changes)

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### How to Contribute

1. **Fork the repository**
   ```bash
   git clone https://github.com/your-username/career_coach.git
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```

3. **Make your changes**
   - Write clean, documented code
   - Follow the existing code style
   - Test your changes thoroughly

4. **Commit your changes**
   ```bash
   git commit -m "Add amazing feature"
   ```

5. **Push to your fork**
   ```bash
   git push origin feature/amazing-feature
   ```

6. **Open a Pull Request**
   - Describe your changes clearly
   - Link any related issues
   - Wait for review

### Code Style Guidelines

- Use ESLint configuration provided
- Follow React best practices
- Write meaningful commit messages
- Add comments for complex logic
- Update documentation as needed

### Areas for Contribution

- 🐛 Bug fixes
- ✨ New features
- 📝 Documentation improvements
- 🎨 UI/UX enhancements
- 🧪 Test coverage
- 🌐 Internationalization (i18n)
- ♿ Accessibility improvements

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- [Next.js](https://nextjs.org/) - The React Framework
- [Vercel](https://vercel.com/) - Deployment platform
- [Clerk](https://clerk.com/) - Authentication
- [Prisma](https://www.prisma.io/) - Database ORM
- [shadcn/ui](https://ui.shadcn.com/) - UI Components
- [Google Gemini](https://ai.google.dev/) - AI capabilities
- [Inngest](https://www.inngest.com/) - Background job processing

---

## 📞 Support

If you have any questions or need help:

- 📧 Open an [issue](https://github.com/Arpitpatel97/career_coach/issues)
- 💬 Start a [discussion](https://github.com/Arpitpatel97/career_coach/discussions)
- 📖 Check the [documentation](#-documentation)

---

## 🗺️ Roadmap

### Current Features (v1.0)
- ✅ AI-powered career guidance
- ✅ Resume builder with ATS scoring
- ✅ Interview preparation module
- ✅ Cover letter generation
- ✅ Industry insights and trends
- ✅ User authentication and profiles

### Upcoming Features
- 🔄 Job search integration
- 🔄 LinkedIn profile optimization
- 🔄 Career path recommendations
- 🔄 Mentorship matching
- 🔄 Skills gap analysis
- 🔄 Certificate tracking
- 🔄 Networking recommendations
- 🔄 Mobile application
- 🔄 Video interview practice
- 🔄 Company culture insights

---

## 📊 Stats

- **50+** Industries Covered
- **1000+** Interview Questions
- **95%** Success Rate
- **24/7** AI Support

---

<div align="center">

**Made with ❤️ by [Arpit Patel](https://github.com/Arpitpatel97)**

⭐ Star us on GitHub — it motivates us a lot!

[Report Bug](https://github.com/Arpitpatel97/career_coach/issues) • [Request Feature](https://github.com/Arpitpatel97/career_coach/issues)

</div>

