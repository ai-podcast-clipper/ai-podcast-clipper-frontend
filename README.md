# AI Podcast Clipper SaaS

A full-stack SaaS application that uses AI to automatically generate short, shareable clips from podcast episodes and other audio/video content.

## Features

- **AI-Powered Clip Generation**: Upload podcast episodes and get automatically generated clips of interesting moments
- **User Authentication**: Secure email/password authentication with NextAuth.js
- **Credits System**: Pay-as-you-go model where each clip generation consumes credits
- **File Management**: Upload, view, and manage your audio/video files
- **Clip Library**: Access and organize your generated clips
- **Stripe Integration**: Purchase credit packs through Stripe

## Tech Stack

- **Frontend**: Next.js 15 with React 19, TypeScript, and Tailwind CSS
- **UI Components**: shadcn/ui with custom components
- **Authentication**: NextAuth.js with JWT and Prisma adapter
- **Database**: PostgreSQL with Prisma ORM
- **File Storage**: AWS S3 for podcast files and clips storage
- **Background Processing**: Inngest for reliable task scheduling and execution
- **Payments**: Stripe integration for purchasing credits
- **Styling**: TailwindCSS with a custom theme

## Getting Started

### Prerequisites

- Node.js 18+ and npm
- PostgreSQL database
- AWS S3 bucket
- Stripe account for payments

### Environment Variables

Create a `.env` file with the following variables:

```
# Database
DATABASE_URL=postgresql://username:password@localhost:5432/ai-podcast-clipper

# Auth
AUTH_SECRET=your-secret-key

# AWS S3
AWS_ACCESS_KEY_ID=your-access-key
AWS_SECRET_ACCESS_KEY=your-secret-key
AWS_REGION=your-region
S3_BUCKET_NAME=your-bucket-name

# AI Processing
PROCESS_VIDEO_ENDPOINT=https://your-processing-endpoint
PROCESS_VIDEO_ENDPOINT_AUTH=your-auth-token

# Stripe
STRIPE_SECRET_KEY=your-stripe-secret-key
STRIPE_WEBHOOK_SECRET=your-webhook-secret
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your-publishable-key
STRIPE_SMALL_CREDIT_PACK=price_id
STRIPE_MEDIUM_CREDIT_PACK=price_id
STRIPE_LARGE_CREDIT_PACK=price_id

# App
BASE_URL=http://localhost:3000
```

### Installation

1. Clone the repository
   ```
   git clone https://github.com/yourusername/ai-podcast-clipper-saas.git
   cd ai-podcast-clipper-saas
   ```

2. Install dependencies
   ```
   npm install
   ```

3. Set up the database
   ```
   npm run db:push
   ```

4. Run the development server
   ```
   npm run dev
   ```

5. Run Inngest for background jobs (in a separate terminal)
   ```
   npm run inngest-dev
   ```

## Development

### Database Management

- View database with Prisma Studio: `npm run db:studio`
- Push schema changes: `npm run db:push`
- Generate migrations: `npm run db:generate`
- Apply migrations: `npm run db:migrate`

### Additional Scripts

- Build for production: `npm run build`
- Start production server: `npm run start`
- Run linter: `npm run lint`
- Fix linting issues: `npm run lint:fix`
- Type check: `npm run typecheck`
- Format code: `npm run format:write`

## Project Structure

```
.
├── prisma/             # Database schema and migrations
├── public/             # Static assets
├── src/
│   ├── actions/        # Server actions
│   ├── app/            # Next.js app router pages
│   ├── components/     # React components
│   ├── inngest/        # Background job definitions
│   ├── lib/            # Utility functions
│   ├── schemas/        # Zod validation schemas
│   ├── server/         # Server-side code
│   └── styles/         # Global styles
├── .env                # Environment variables (not in repo)
└── package.json        # Project dependencies
```

## License

[MIT](LICENSE)
