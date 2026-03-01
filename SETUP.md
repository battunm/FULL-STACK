# Setup Instructions for React EMS India

## 📍 Project Location
```
c:\Users\Lenovo\.gemini\antigravity\scratch\react-ems
```

## Step-by-Step Setup

### 1️⃣ Open This Folder in VS Code

**Option A: Via Command Line**
```bash
cd c:\Users\Lenovo\.gemini\antigravity\scratch\react-ems
code .
```

**Option B: Via VS Code**
- Open VS Code
- File → Open Folder
- Navigate to: `c:\Users\Lenovo\.gemini\antigravity\scratch\react-ems`
- Click Select Folder

### 2️⃣ Open Terminal in VS Code

Press `Ctrl + `  (backtick) or go to View → Terminal

You should see the path:
```
PS C:\Users\Lenovo\.gemini\antigravity\scratch\react-ems>
```

### 3️⃣ Install Dependencies

Type this command in terminal:
```bash
npm install
```

**What it does:**
- Downloads React, React Router, Vite, and other packages
- Creates `node_modules` folder
- Creates `package-lock.json`
- Takes 2-5 minutes depending on internet speed

**Wait for it to complete** until you see the prompt again.

### 4️⃣ Start Development Server

```bash
npm run dev
```

**Expected output:**
```
  VITE v5.0.8  ready in xxx ms

  ➜  Local:   http://localhost:3000/
  ➜  press h to show help
```

**Your browser should automatically open** to `http://localhost:3000`

If browser doesn't open, click the link in terminal.

### 5️⃣ Test the App

**Home page should show:**
- ✅ Navbar with "EMS India" logo
- ✅ Hero section with "Empowering Democracy"
- ✅ Stats grid
- ✅ Elections section
- ✅ Footer

**Navigation works:**
- Click "About" → About page loads
- Click "Contact" → Contact page loads
- Click "Register" → Registration form loads
- Click "Login" → Login form loads

### 6️⃣ Test Authentication

**Try logging in with demo account:**

1. Click "Login" in navbar
2. Click "🔐 Admin" button
3. Fields auto-fill with: `admin@eci.gov.in` / `Admin@ECI2024!`
4. Click "Login to Dashboard"
5. Should redirect to Admin Dashboard
6. Try clicking "Logout" to go back

## 🛑 Stop Development Server

In terminal where `npm run dev` is running:
- Press `Ctrl + C`
- Confirm with `Y`

## 📦 Build for Production

When ready to deploy:

```bash
npm run build
```

**Creates:**
- `dist/` folder with optimized files
- Ready to deploy to any web hosting

**Test production build locally:**
```bash
npm run preview
```

Then visit `http://localhost:4173` to test.

## 📁 Project Files You Can Edit

**Safe to modify:**
- `src/styles/global.css` - Change colors/styles
- `src/pages/*.jsx` - Edit page content
- `src/utils/ems.js` - Add/modify data
- `index.html` - Page title/meta tags
- `vite.config.js` - Build configuration

**Don't delete:**
- `src/main.jsx` - App entry point
- `src/App.jsx` - Router configuration
- `src/components/Layout.jsx` - Main layout
- `src/hooks/useCursor.js` - Custom cursor

## 🔗 Project Links Summary

### All Original HTML Files → React Components

| Original | React Path | URL |
|----------|----------|-----|
| index.html | `src/pages/HomePage.jsx` | `/` |
| login.html | `src/pages/LoginPage.jsx` | `/login` |
| register.html | `src/pages/RegisterPage.jsx` | `/register` |
| about.html | `src/pages/AboutPage.jsx` | `/about` |
| contact.html | `src/pages/ContactPage.jsx` | `/contact` |
| admin-dashboard.html | `src/pages/DashboardPages.jsx` | `/admin-dashboard` |
| citizen-dashboard.html | `src/pages/DashboardPages.jsx` | `/citizen-dashboard` |
| observer-dashboard.html | `src/pages/DashboardPages.jsx` | `/observer-dashboard` |
| analyst-dashboard.html | `src/pages/DashboardPages.jsx` | `/analyst-dashboard` |

### CSS & JS Files → React Equivalents

| Original | React Path | Purpose |
|----------|----------|---------|
| `css/styles.css` | `src/styles/global.css` | All styling |
| `js/cursor.js` | `src/hooks/useCursor.js` | Custom cursor |
| `js/auth.js` | `src/utils/ems.js` | Auth & validation |
| `js/data.js` | `src/utils/ems.js` | Election data |

## 🎯 How It All Works

```
Browser Request (e.g., /about)
         ↓
React Router (App.jsx)
         ↓
Routes to AboutPage.jsx
         ↓
AboutPage renders inside Layout
         ↓
Layout provides navbar + footer + cursor
         ↓
Styles applied from global.css
         ↓
Dynamic content from ems.js data store
```

## 📝 Common Commands

| Command | What it does |
|---------|-------------|
| `npm install` | Install dependencies |
| `npm run dev` | Start dev server (localhost:3000) |
| `npm run build` | Create production build |
| `npm run preview` | Preview production build |
| `npm run lint` | Check code quality |

## 🐛 If Something Goes Wrong

**Error: "Cannot find module"**
```bash
rm -rf node_modules package-lock.json
npm install
```

**Error: "Port 3000 already in use"**
```bash
npm run dev -- --port 3001
```

**Page won't load after clicking link**
- Make sure you're running `npm run dev`
- Try hard refresh: `Ctrl + Shift + R`

**Styles look weird/broken**
- Clear browser cache: `Ctrl + Shift + Del`
- Check if `global.css` is imported in `src/main.jsx` ✓

## ✅ Verification Checklist

After setup, verify:

- [ ] Terminal shows `http://localhost:3000/` 
- [ ] Browser opens automatically
- [ ] Home page displays correctly
- [ ] Can navigate to About page
- [ ] Can navigate to Contact page
- [ ] Demo login works (admin account)
- [ ] Can view Admin Dashboard
- [ ] Logout button works
- [ ] Navbar is visible on all pages
- [ ] Footer is visible on all pages

## 🚀 You're Ready!

If all checks pass, your React EMS India app is fully functional! 🎉

- Develop locally with `npm run dev`
- Build for production with `npm run build`
- Deploy the `dist/` folder to any web hosting

## 📞 Need Help?

Check these files:
- `PROJECT_GUIDE.md` - Detailed guide
- `README.md` - Project overview
- `DEPLOYMENT.md` - Deployment instructions
- `src/pages/*.jsx` - Component examples

---

**Happy coding! 🎨✨**
