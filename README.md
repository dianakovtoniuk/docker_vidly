# Vidly

A movie rental web application built with React on the frontend, containerized with Docker, and deployed via Vercel (frontend) and Render (backend).

## About

Vidly lets users browse, add, and manage a list of movies through a simple, clean interface. The project demonstrates a full deployment pipeline — from local Docker development to a production setup split across two hosting providers.

## Tech Stack

- **Frontend:** React 17, Axios
- **Build tool:** Create React App (`react-scripts`)
- **Containerization:** Docker
- **Frontend hosting:** Vercel
- **Backend hosting:** Render

## Getting Started

### Prerequisites

- Node.js 20.x
- npm

### Installation

```bash
git clone https://github.com/dianakovtoniuk/docker_vidly.git
cd docker_vidly/frontend
npm install
```


### Running Locally

```bash
npm start
```

The app will be available at `http://localhost:3000`.

### Building for Production

```bash
npm run build
```

## Running with Docker

Build and run the frontend container:

```bash
cd frontend
docker build -t vidly-frontend .
docker run -p 3000:3000 vidly-frontend
```

## Deployment

### Frontend (Vercel)

The frontend is deployed on [Vercel](https://vercel.com). Environment variables (such as `REACT_APP_API_URL`) must be configured in **Project Settings → Environment Variables**, and a redeploy is required after any changes since these variables are baked into the build at build time.

### Backend (Render)

The backend is hosted on [Render](https://render.com) as a Dockerized web service.

> **Note:** Render's free-tier instances spin down after inactivity, which can delay the first request by up to 50 seconds.

## Available Scripts

| Command         | Description                          |
|-----------------|---------------------------------------|
| `npm start`     | Runs the app in development mode      |
| `npm run build` | Builds the app for production         |
| `npm test`      | Launches the test runner              |
| `npm run eject` | Ejects the CRA configuration          |

Contributions, issues, and feature requests are welcome. Feel free to open a pull request or file an issue.

Create a `.env` file in the `frontend` directory:
