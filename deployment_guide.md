# Witness - Deployment Guide

## Quick Start

This guide will help you deploy your Witness AI mental health companion to production.

## Prerequisites

- Node.js 18+ installed
- Supabase account and project set up
- Vercel account (recommended for deployment)

## Local Development

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Set up environment variables:**
   Create a `.env.local` file with your Supabase credentials:
   ```
   NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
   NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
   OPENAI_API_KEY=your_openai_api_key
   ```

3. **Run development server:**
   ```bash
   npm run dev
   ```

## Deployment Options

### Option 1: Vercel (Recommended)

1. **Connect to GitHub:**
   - Push your code to GitHub
   - Go to [vercel.com](https://vercel.com)
   - Click "New Project"
   - Import your GitHub repository

2. **Environment Variables:**
   - In Vercel dashboard, go to your project settings
   - Add the same environment variables from your `.env.local`

3. **Deploy:**
   - Vercel will automatically deploy on every push to main branch
   - Your app will be available at `your-project.vercel.app`

### Option 2: Manual GitHub Upload

If you can't push via git, you can manually upload files:

1. Go to your GitHub repository
2. Click "uploading an existing file"
3. Drag and drop your project files
4. Commit the changes

## Domain Configuration

To use your custom domain (portablecortex.com):

1. **In Vercel:**
   - Go to Project Settings → Domains
   - Add your custom domain
   - Follow DNS configuration instructions

2. **DNS Settings:**
   - Add a CNAME record pointing to your Vercel deployment
   - Or use A record with Vercel's IP addresses

## Database Setup

Your Supabase database should include these tables:
- `profiles` - User profiles
- `journal_entries` - Journal entries
- `check_ins` - Daily check-ins
- `ai_alerts` - AI-generated alerts
- `behavioral_analysis` - Behavioral data

## Troubleshooting

### Common Issues:

1. **Build Errors:**
   ```bash
   npm run build
   ```
   Fix any TypeScript or build errors before deploying.

2. **Environment Variables:**
   Make sure all required env vars are set in your deployment platform.

3. **Supabase Connection:**
   Verify your Supabase URL and keys are correct.

## Security Checklist

- [ ] Environment variables are properly set
- [ ] Supabase RLS policies are configured
- [ ] OpenAI API key is secured
- [ ] HTTPS is enabled on custom domain

## Support

For deployment issues, check:
- Vercel deployment logs
- Browser console for client-side errors
- Supabase logs for database issues
