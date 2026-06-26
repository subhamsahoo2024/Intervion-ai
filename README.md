# Intervion AI

InterviewPrep is a Vite + React + TypeScript interview preparation platform with separate student and admin experiences. Students can move through multi-round mock interview workflows, while admins can manage company workflows, question banks, and review analytics.

## Live Link
- https://intervion-ai-sst.vercel.app/

## Features

- Student dashboard with mock performance visualizations
- Multi-round mock interview marathon by company
- Resume analysis with AI-generated ATS feedback
- Aptitude test round with timing, scoring, and review
- Coding lab round for company-specific coding questions
- HR interview simulation
- Group discussion simulation with voice input and AI participants
- Admin analytics dashboard
- Admin CMS for company workflows, aptitude CSV import, and coding question management

## Student Flow

Students sign in through a auth screen, choose a target company, and progress through the configured rounds for that company. Supported round types are:

- `resume`
- `aptitude`
- `coding`
- `gd`
- `hr`

## Admin Flow

Admins can:

- Review candidate analytics from the admin dashboard
- Manage companies and interview workflows
- Upload aptitude questions from CSV
- Manage coding questions per company
- Configure HR interview tone and persona settings

## Tech Stack

- React 19
- TypeScript
- Vite 6
- React Router 7
- Zustand for persisted client-side state
- Framer Motion / Motion for animations
- Recharts for analytics visualizations
- Supabase for aptitude and coding question storage
- Gemini and Groq-based AI integrations for resume, HR, and discussion features

## Project Structure

```text
src/
  components/
    DashboardLayout.tsx
  lib/
    supabase.ts
  pages/
    AdminAnalytics.tsx
    AdminCMS.tsx
    AptitudeTest.tsx
    CodingLab.tsx
    GroupDiscussion.tsx
    HRInterview.tsx
    LoginPage.tsx
    MockMarathon.tsx
    ResumeAnalyzer.tsx
    StudentDashboard.tsx
  services/
    geminiService.ts
  store/
    useCmsStore.ts
    useStore.ts
```

## Getting Started

### Prerequisites

- Node.js 18+
- npm
- A Supabase project if you want CMS-backed aptitude and coding data
- AI provider credentials for Gemini and Groq-backed features

### Install

```bash
npm install
```

### Environment Variables

Create a `.env` file in the project root.

```env
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
VITE_GEMINI_API_KEY=your_shared_gemini_api_key
VITE_GEMINI_API_KEY_CODING=your_coding_lab_gemini_api_key
VITE_GEMINI_API_KEY_HR=your_hr_interview_gemini_api_key
VITE_GROQ_API_KEY_HR=your_hr_interview_groq_api_key
VITE_GROQ_API_KEY_GD=your_group_discussion_groq_api_key
VITE_JDOODLE_CLIENT_ID=your_jdoodle_client_id
VITE_JDOODLE_CLIENT_SECRET=your_jdoodle_client_secret
```

### Run Locally

```bash
npm run dev
```

Open the local Vite URL shown in the terminal.

## Available Scripts

- `npm run dev` starts the Vite development server
- `npm run build` creates a production build
- `npm run preview` previews the production build locally
- `npm run lint` runs `tsc --noEmit`

## Routing

### Public

- `/login`

### Student Routes

- `/dashboard`
- `/mock-marathon`
- `/resume`
- `/aptitude`
- `/coding`
- `/group-discussion`
- `/hr`

### Admin Routes

- `/admin`
- `/admin/students`
- `/admin/cms`

