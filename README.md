# ASCEND: Career Intelligence and Growth Platform

A web platform that helps students prepare for jobs in one place: resume analysis, skills tests, mock interviews, job opportunities and a personalised career roadmap, with a dashboard that brings the results together.

## Features

| Module | What it does |
|---|---|
| Resume analysis (ATS) | Upload a resume (PDF or Word) and get it analysed |
| Technical test | Set up a test, take it in a timed session and see the result |
| Communication test | Practise and assess communication skills |
| Mock interview | Set up an interview and answer questions in a live session |
| Opportunities | Browse job opportunities |
| Career roadmap | Get a personalised step-by-step roadmap |
| Dashboard | One page that brings test, interview and roadmap results together |

## Tech stack

| Layer | Technologies |
|---|---|
| Backend | Node.js, Express.js (REST API) |
| Database | PostgreSQL (Supabase) with Prisma |
| Frontend | HTML, CSS, JavaScript (React and Tailwind CSS loaded from a CDN on some pages) |
| File handling | Multer (uploads), pdf-parse, Mammoth, Tesseract.js (text from PDF, Word and images) |
| AI | Google Gemini API was integrated for interview questions, answer evaluation, resume analysis and roadmaps, and the project later moved to a rule-based engine |
| Tools | Git, GitHub, VS Code |

## Project structure

```
ASCEND/
  backend/
    server.js          Express server and API routes
    routes/            API routes (interview, tests, resume analysis, opportunities, roadmaps, dashboard)
    services/          Business logic and integrations
    utils/             Helper functions (for example the test evaluator)
    scripts/           Evaluation scripts
    datasets/          Data used for evaluation
    prisma/            Database schema
    package.json
  frontend/            Pages for login, dashboard, tests, mock interview, roadmap
  .env.example         Names of the settings the server needs
```

## How to run

1. Install [Node.js](https://nodejs.org/).
2. Clone the repo and install dependencies:
   ```
   git clone https://github.com/Siri6281/ASCEND.git
   cd ASCEND/backend
   npm install
   ```
3. Create a file named `.env` in the `backend` folder (see `.env.example`) and add your own database URL.
4. Set up the database tables and start the server:
   ```
   npx prisma generate
   npx prisma db push
   npm start
   ```
5. Open `http://localhost:3002` in your browser.

## Evaluation

The rule-based test evaluator is benchmarked on a labelled dataset (accuracy, precision, recall, F1-score, robustness and latency):

```
npm run evaluate
```

## What I learned

- Building a REST API with Express and connecting it to a PostgreSQL database
- Handling file uploads and extracting text from PDF, Word and image files
- Integrating an LLM API (Gemini), debugging model errors, and moving to a rule-based engine
- Working in a team with Git and GitHub
