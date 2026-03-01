# Election Monitoring System - React Vite Deployment Guide

## Quick Start

### 1. Install Dependencies
```bash
cd react-ems
npm install
```

### 2. Development
```bash
npm run dev
```
Opens at `http://localhost:3000` with hot reload

### 3. Production Build
```bash
npm run build
```
Creates optimized `dist/` folder ready to deploy

## Deployment Options

### Option 1: Vercel (Recommended)
```bash
npm install -g vercel
vercel
```
Automatically detects Vite project. Push to deploy updates.

### Option 2: Netlify
1. Connect GitHub repo to Netlify
2. Set build command: `npm run build`
3. Set publish directory: `dist`
4. Deploy!

### Option 3: GitHub Pages
```bash
npm install gh-pages --save-dev
```
Update `vite.config.js`:
```javascript
export default defineConfig({
  base: '/path-to-repo/',
  // ...
})
```

### Option 4: Traditional Server (Apache/Nginx)
1. Run `npm run build`
2. Copy `dist/` contents to web server
3. Configure server for SPA routing:

**NGINX:**
```nginx
location / {
  try_files $uri /index.html;
}
```

**Apache (.htaccess):**
```apache
<IfModule mod_rewrite.c>
  RewriteEngine On
  RewriteBase /
  RewriteRule ^index\.html$ - [L]
  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteRule . /index.html [L]
</IfModule>
```

## Environment Variables

Create `.env.local`:
```
VITE_API_URL=https://api.ems-india.gov.in
VITE_APP_NAME=EMS India
```

Use in code:
```javascript
const apiUrl = import.meta.env.VITE_API_URL;
```

## Environment-Specific Builds

Development:
```bash
npm run dev
```

Production:
```bash
npm run build
```

Preview production build locally:
```bash
npm run preview
```

## Performance Optimization

The build already includes:
- ✅ Code splitting
- ✅ CSS minification
- ✅ JavaScript compression
- ✅ Asset optimization
- ✅ Tree shaking

Verify bundle size:
```bash
npm run build -- --analyze
```

## Troubleshooting

### Routing not working
Ensure your hosting supports SPA (Single Page Application) mode.
All requests except static files should serve `index.html`.

### Styles not loading
Check that `vite.config.js` base path matches deployment URL.

### Build fails
```bash
rm -rf node_modules package-lock.json
npm install
npm run build
```

## Update Production

When you have changes:
1. Test locally: `npm run dev`
2. Build: `npm run build`
3. Deploy `dist/` folder
4. Clear browser cache (Ctrl+Shift+Del)

## Monitor Performance

Use Lighthouse in Chrome DevTools to check:
- Performance
- Accessibility
- Best Practices
- SEO

---

**Need more details?** Check the main README.md in the project folder.
