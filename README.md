# rag-knowledge-web

Angular 17 frontend for the [UK Employment Law Assistant](https://github.com/PotatoUser69/rag-knowledge-api).

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

Before deploying, update `environment.prod.ts` with your backend's public URL:

```typescript
export const environment = {
  production: true,
  apiUrl: 'https://your-backend-url.railway.app',
};
```

## Deploy to Vercel

1. Push this repo to GitHub
2. Import into [Vercel](https://vercel.com)
3. Set **Framework Preset** → `Angular`
4. Set **Build Command** → `npm run build:prod`
5. Set **Output Directory** → `dist/rag-knowledge-web`
6. Update `src/environments/environment.prod.ts` with the deployed backend URL and redeploy

## Docker

```bash
docker build -t rag-knowledge-web .
docker run -p 80:80 rag-knowledge-web
```
