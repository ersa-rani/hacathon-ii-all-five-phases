
<img width="1362" height="643" alt="image" src="https://github.com/user-attachments/assets/84541433-7001-43c9-9295-d076f899d1ec" />


demo video 👉🏻https://youtu.be/wpvfFQmd1LQ?si=4d6yOh6u03H2lDVw


# TaskFlow AI

TaskFlow AI is a full-stack productivity workspace built with **Next.js**, **Firebase**, and **Genkit (Gemini)**.  
It combines task management, reminders, and an AI assistant in one modern dashboard.

## Features

- Email/password and Google authentication (Firebase Auth)
- Personal dashboard with live task stats
- Task management (create, search, complete, delete, priority levels)
- Activity log / reminders timeline
- AI assistant chat with task extraction from natural language
- Per-user data isolation with Firestore security rules
- Responsive premium UI with dark/light theme

## Tech Stack

- **Frontend:** Next.js 15, React 19, TypeScript, Tailwind CSS, Radix UI, Lucide
- **Backend/Data:** Firebase Auth + Firestore
- **AI:** Genkit + Google Gemini (`gemini-2.5-flash`)
- **Utilities:** date-fns, zod, react-hook-form

## Project Structure

```txt
src/
  app/
    page.tsx                  # Landing page
    about/page.tsx            # About page
    (auth)/login/page.tsx     # Login
    (auth)/signup/page.tsx    # Signup
    (dashboard)/dashboard     # Dashboard
    (dashboard)/tasks         # Task manager
    (dashboard)/assistant     # AI assistant chat
    (dashboard)/reminders     # Activity log
    (dashboard)/settings      # User settings
  ai/
    flows/                    # Genkit AI flows
    genkit.ts                 # Genkit config
    dev.ts                    # Genkit dev entry
  firebase/
    config.ts                 # Firebase config
    provider.tsx              # Firebase context/hooks
firestore.rules               # Firestore security rules
Getting Started
Prerequisites
Node.js 20+
npm
Firebase project (Auth + Firestore enabled)
Google AI API key (for Genkit)
Installation
bash

npm install
Environment Variables
Create .env.local in the project root:

env

GOOGLE_API_KEY=your_google_ai_api_key
Optional (recommended for public repos): move Firebase config values to env variables instead of hardcoding src/firebase/config.ts.

Run Locally
bash

npm run dev
App runs on:

http://localhost:9002
AI Flow Development (Optional)
bash

npm run genkit:dev
# or
npm run genkit:watch
Available Scripts
npm run dev - start Next.js dev server on port 9002
npm run build - production build
npm run start - run production server
npm run lint - lint project
npm run typecheck - TypeScript checks
npm run genkit:dev - start Genkit flow server
npm run genkit:watch - start Genkit with watch mode
Security
Firestore rules enforce strict user ownership under:

/users/{userId}
/users/{userId}/tasks/{taskId}
/users/{userId}/reminders/{reminderId}
/users/{userId}/aiAssistantMessages/{messageId}
Users can only access their own data.

Deployment
This project includes Firebase App Hosting config via apphosting.yaml.
You can also deploy on platforms like Vercel (Next.js compatible).

Author
Developed by Ersa Rani
