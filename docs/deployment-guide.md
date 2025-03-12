# Deployment Guide

## Prerequisites

- **Frontend**: Node.js, Vercel/Netlify account
- **Backend**: AWS/GCP account, PostgreSQL/MongoDB database

## Frontend Deployment (Vercel/Netlify)

### Vercel:

1. Install Vercel CLI:

   ```sh
   npm install -g vercel
   ```

2. Login to Vercel:

   ```sh
   vercel login
   ```

3. Deploy project:

   ```sh
   vercel
   ```

### Netlify:

1. Install Netlify CLI:

   ```sh
   npm install -g netlify-cli
   ```

2. Login to Netlify:

   ```sh
   netlify login
   ```

3. Deploy project:

   ```sh
   netlify deploy --prod
   ```

## Backend Deployment (AWS/GCP)

### AWS:

1. Set up an EC2 instance.
2. Install Node.js and dependencies.

   ```sh
   sudo apt update && sudo apt install nodejs npm
   ```

3. Upload backend code and install packages:

   ```sh
   git clone <repository_url>
   cd backend
   npm install
   ```

4. Set up environment variables (`.env`).
5. Start the server:

   ```sh
   npm start
   ```

### Google Cloud Platform (GCP):

1. Create a Cloud Run instance.
2. Build and push a Docker image:

   ```sh
   docker build -t gcr.io/<project-id>/your-gallery .
   docker push gcr.io/<project-id>/your-gallery
   ```
3. Deploy the service:

   ```sh
   gcloud run deploy your-gallery --image gcr.io/<project-id>/your-gallery --platform managed
   ```

## Database Setup

- Use PostgreSQL or MongoDB Atlas.
- Configure database URI in backend `.env`.

## Final Steps

- Connect frontend to backend.
- Monitor logs and optimize performance.
- Set up automatic deployment using CI/CD pipelines.

This guide ensures a smooth deployment process for both frontend and backend components.

