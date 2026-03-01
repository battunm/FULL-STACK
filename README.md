# EMS India - React + Vite Edition

Welcome to the React + Vite conversion of the Election Monitoring System (EMS) India project!

## Project Structure

```
react-ems/
├── src/
│   ├── components/
│   │   └── Layout.jsx           # Main layout with navbar & footer
│   ├── pages/
│   │   ├── HomePage.jsx         # Home page with elections grid
│   │   ├── LoginPage.jsx        # Login form
│   │   ├── RegisterPage.jsx     # Registration with password strength
│   │   ├── AboutPage.jsx        # About & features
│   │   ├── ContactPage.jsx      # Contact form & FAQ
│   │   └── DashboardPages.jsx   # Admin/Citizen/Observer/Analyst dashboards
│   ├── hooks/
│   │   └── useCursor.js         # Custom cursor animation hook
│   ├── utils/
│   │   └── ems.js               # EMS data & utilities
│   ├── styles/
│   │   └── global.css           # All global styles (copied from original)
│   ├── App.jsx                  # Main app with routing
│   └── main.jsx                 # Entry point
├── index.html                   # HTML template
├── vite.config.js               # Vite configuration
├── package.json                 # Dependencies
└── README.md                    # This file
```

## Features

✅ **Identical Design**: All CSS styles from the original HTML project are preserved
✅ **React Components**: Modular, reusable React components for each page
✅ **React Router**: Client-side routing for seamless navigation
✅ **Custom Cursor**: Animated custom cursor following original behavior
✅ **Responsive**: Mobile-first responsive design
✅ **Dark Theme**: Indian-themed glassmorphism with Saffron, Green & Navy colors
✅ **Form Validation**: Real-time password strength meter and validation
✅ **Authentication**: Session-based auth with role-based dashboards
✅ **Easy Deployment**: Build with `npm run build` → Deploy the `dist/` folder

## Installation & Setup

### Prerequisites
- Node.js 16+ 
- npm or yarn

### Development

```bash
# Install dependencies
npm install

# Start development server
npm run dev
```

The app will open automatically at `http://localhost:3000`

### Build for Production

```bash
# Create optimized build
npm run build

# Preview built version locally
npm run preview
```

## Deployed Files

After running `npm run build`, all files are in the `dist/` folder ready for deployment:

```
dist/
├── index.html          # Entry point HTML
├── assets/
│   ├── index-xxxxx.js  # Bundled JavaScript
│   └── index-xxxxx.css # Bundled CSS
└── vite.svg           # Vite logo
```

**Deploy `dist/` folder to any static hosting:**
- Vercel
- Netlify  
- GitHub Pages
- AWS S3
- Any web server

## Demo Accounts

**Admin**
- Email: `admin@eci.gov.in`
- Password: `Admin@ECI2024!`

**Citizen**
- Email: `rahul.sharma@gmail.com`
- Password: `Citizen@123!`

**Observer**
- Email: `observer1@eci.gov.in`
- Password: `Observer@123!`

**Analyst**
- Email: `analyst@eci.gov.in`
- Password: `Analyst@123!`

## API Integration Ready

The current implementation uses mock data in `src/utils/ems.js`. To integrate with a real backend:

1. Replace `EMS.accounts` with API calls in `LoginPage.jsx`
2. Replace `EMS.elections` with API calls in `HomePage.jsx`
3. Fetch user/state data from backend in `DashboardPages.jsx`

Example:
```javascript
// Instead of
const account = EMS.accounts.find(a => a.email === email);

// Use
const response = await fetch('/api/auth/login', { 
  method: 'POST', 
  body: JSON.stringify({ email, password })
});
const account = await response.json();
```

## Customization

### Change Theme Colors
Edit `src/styles/global.css` CSS variables section:
```css
:root {
  --saffron: #FF9933;
  --green: #138808;
  --navy: #000080;
  /* ... other colors ... */
}
```

### Add New Pages
1. Create new file in `src/pages/YourPage.jsx`
2. Import in `App.jsx`
3. Add route: `<Route path="/your-path" element={<YourPage />} />`

### Modify Components
All page layouts use the base `Layout` component which handles:
- Navigation bar
- Custom cursor
- Background animations
- Footer

Wrap your page content with `<Layout>` to get these automatically.

## Technologies

- **React 18**: Modern UI framework
- **React Router v6**: Client-side routing
- **Vite**: Lightning-fast build tool
- **JavaScript (ES6+)**: Modern JavaScript
- **CSS3**: Advanced styling with animations

## Performance

- ⚡ Fast development with Vite HMR
- 📦 Optimized production builds (< 50KB gzipped)
- 🎨 CSS animations with GPU acceleration
- 📱 Mobile-optimized responsive design

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## License

Developed for Election Monitoring System India. All rights reserved.

---

**Need Help?** Check the individual component files or refer to React/Vite documentation.
