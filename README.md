# rag-knowledge-web

Angular 17 frontend for the [UK Employment Law Assistant](https://github.com/PotatoUser69/rag-knowledge-api).

Live: **https://raf-knowledge.ahmed-ai.com**

## Prerequisites

- Node 20+
- The backend API running (see [rag-knowledge-api](https://github.com/PotatoUser69/rag-knowledge-api))

## Local development

```bash
npm install
npm start
# UI: http://localhost:4200
# Expects the backend at http://localhost:8000
```

## Configuration

The backend URL is set in the Angular environment files:

| File | Used when |
|------|-----------|
| `src/environments/environment.ts` | `npm start` (development) |
| `src/environments/environment.prod.ts` | `npm run build:prod` (production) |

Once you have your Railway backend URL, update `src/environments/environment.prod.ts`:

```typescript
export const environment = {
  production: true,
  apiUrl: 'https://your-app.railway.app', // paste your Railway URL here
};
```

Then commit and push — Vercel will rebuild automatically.

## Deploy to Vercel

1. Push this repo to GitHub
2. Import into [Vercel](https://vercel.com)
3. Set **Framework Preset** → `Angular`
4. Set **Build Command** → `npm run build:prod`
5. Set **Output Directory** → `dist/rag-knowledge-web`
6. Add a custom domain → `raf-knowledge.ahmed-ai.com`
7. After Railway gives you a backend URL, update `environment.prod.ts` and redeploy

## Docker

```bash
docker build -t rag-knowledge-web .
docker run -p 80:80 rag-knowledge-web
