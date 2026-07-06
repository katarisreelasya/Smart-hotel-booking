# ApplyWise - Smart Job Portal

ApplyWise is a smart job applying portal focused on reducing repeated form filling, expired applications, unclear application status, long job descriptions, and irrelevant job search results. It uses React, Node.js, Express, and SQL with SQLite for a free local database.

## Core Features

- One-time job seeker profile with skills, education, projects, resume links, and portfolio links.
- Recruiter-created internal jobs with Easy Apply and recruiter-controlled status updates.
- External company jobs for companies such as Amazon or Cognizant, tracked as `Applied Externally`.
- Smart skill extraction from job descriptions using a free rule-based matching engine.
- Resume-to-job match score with matched and missing skills.
- Deadline alerts and expired job prevention.
- Application tracker with statuses like Applied, Resume Viewed, Shortlisted, Interview, Offered, and Rejected.

## Architecture

```text
client/  React + Vite frontend
server/  Express + SQLite SQL backend
```

```text
React UI -> Express API -> SQLite database
              |
              -> Smart matching service
```

## Setup

Install dependencies:

```bash
npm install
npm run install:all
```

Create server environment file if it does not already exist:

```bash
copy server\.env.example server\.env
```

Run the app:

```bash
npm run dev
```

Frontend: `http://127.0.0.1:5173`

Backend: `http://127.0.0.1:5000`

The SQLite database is created automatically at `server/data/hireflow.sqlite`.

## External Company Status

For jobs posted inside the portal, recruiters update application status directly.

For external company jobs, the platform cannot verify the true status automatically. The user can add the job to their tracker as `Applied Externally` and manually update it later.
