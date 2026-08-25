# AniVerse - Deployment & Performance Guide

## Deployment Options

### Vercel (Recommended)
```bash
npm i -g vercel
vercel --prod
```

### Netlify
```bash
npm run build
# Upload dist/ folder to Netlify
```

### Docker
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build
EXPOSE 3000
CMD ["npm", "start"]
```

## Performance Optimization
- Enable lazy loading for images
- Use intersection observer for infinite scroll
- Implement service worker for offline caching
- Compress images with WebP format
- Use CDN for static assets

## API Rate Limiting
- Cache API responses in localStorage (TTL: 5 min)
- Implement request deduplication
- Use stale-while-revalidate pattern
