# 📚 StudySnap — Intelligent Study Ecosystem

A premium, AI-powered study platform for Ethiopian students. Beautiful UI, smart planning, focus mode, leaderboard, flashcards, and future vision planner — all in one.

---

## 🚀 Quick Start (VS Code)

### 1. Prerequisites
Make sure you have installed:
- [Node.js](https://nodejs.org/) (version 16 or higher)
- [VS Code](https://code.visualstudio.com/)
- [Git](https://git-scm.com/)

### 2. Open in VS Code
```bash
# Open the studysnap folder in VS Code
code studysnap
```

### 3. Install Dependencies
Open the **VS Code terminal** (Ctrl + ` ) and run:
```bash
npm install
```

### 4. Start Development Server
```bash
npm start
```
The app will open at **http://localhost:3000** 🎉

---

## 📁 Project Structure

```
studysnap/
├── public/
│   └── index.html              # HTML template with fonts
├── src/
│   ├── index.js                # React entry point
│   ├── index.css               # Global CSS variables & animations
│   ├── App.js                  # Router & layout
│   ├── components/
│   │   ├── Navbar.js           # Navigation bar
│   │   └── Navbar.css
│   └── pages/
│       ├── LandingPage.js      # Hero, features, CTA
│       ├── LandingPage.css
│       ├── Dashboard.js        # AI planner, tasks, stats
│       ├── Dashboard.css
│       ├── Explore.js          # Subjects, resources, AI tutor chat
│       ├── Explore.css
│       ├── FocusMode.js        # Pomodoro timer, sessions
│       ├── FocusMode.css
│       ├── StudyPlay.js        # Flashcards, quiz
│       ├── StudyPlay.css
│       ├── Leaderboard.js      # Rankings, achievements
│       ├── Leaderboard.css
│       ├── FutureVision.js     # Timeline, goals, AI roadmap
│       └── FutureVision.css
├── vercel.json                 # Vercel deployment config
├── netlify.toml                # Netlify deployment config
└── package.json
```

---

## 🌐 Publishing as an Official Website

### Option A: Deploy to Vercel (Recommended — Free)

1. **Build the app:**
   ```bash
   npm run build
   ```

2. **Install Vercel CLI:**
   ```bash
   npm install -g vercel
   ```

3. **Deploy:**
   ```bash
   vercel
   ```
   Follow the prompts. Your site will be live at `https://studysnap.vercel.app`

4. **Custom domain** (e.g. studysnap.et):
   - Go to [vercel.com](https://vercel.com) → your project → Settings → Domains
   - Add your domain and follow the DNS instructions

---

### Option B: Deploy to Netlify (Also Free)

1. **Build the app:**
   ```bash
   npm run build
   ```

2. **Option B1 — Drag & Drop:**
   - Go to [netlify.com](https://netlify.com)
   - Drag the `build/` folder onto the Netlify dashboard
   - Done! Live in 30 seconds.

3. **Option B2 — Netlify CLI:**
   ```bash
   npm install -g netlify-cli
   netlify deploy --prod --dir=build
   ```

---

### Option C: Deploy to GitHub Pages (Free)

1. Create a GitHub repository for your project

2. Add `"homepage"` to `package.json`:
   ```json
   "homepage": "https://yourusername.github.io/studysnap"
   ```

3. Install gh-pages:
   ```bash
   npm install --save-dev gh-pages
   ```

4. Add deploy scripts to `package.json`:
   ```json
   "predeploy": "npm run build",
   "deploy": "gh-pages -d build"
   ```

5. Deploy:
   ```bash
   npm run deploy
   ```

---

## 🎨 Design System

| Token | Value | Usage |
|-------|-------|-------|
| `--ocean-deep` | `#0a1628` | Background |
| `--aqua` | `#38bdf8` | Primary accent |
| `--pearl` | `#f0f4ff` | Text on dark |
| `--gold` | `#f5c842` | Streaks, highlights |
| `--green` | `#34d399` | Success, progress |
| `--font-display` | Cormorant Garamond | Headings |
| `--font-body` | DM Sans | Body text |
| `--font-mono` | Space Mono | Labels, code |

---

## 🧩 Pages

| Route | Page | Description |
|-------|------|-------------|
| `/` | Landing | Hero, features, stats, CTA |
| `/dashboard` | Dashboard | AI planner, tasks, weekly progress |
| `/explore` | Explore | Subject resources, AI tutor chat |
| `/focus` | Focus Mode | Pomodoro timer, session stats |
| `/play` | Study Play | Flashcards, quizzes |
| `/leaderboard` | Leaderboard | Rankings, achievements |
| `/vision` | Future Vision | Goals timeline, AI roadmap |

---

## ⚡ VS Code Recommended Extensions

Install these for the best development experience:
- **ES7+ React/Redux/React-Native snippets** — fast component creation
- **Prettier - Code formatter** — auto format on save
- **Auto Rename Tag** — rename JSX tags simultaneously
- **CSS Peek** — peek CSS definitions from JS files
- **GitLens** — powerful Git integration

---

## 🔧 Customization

### Change App Name / Branding
- Edit `public/index.html` — update `<title>` and meta description
- Edit `src/components/Navbar.js` — update logo text
- Edit `src/pages/LandingPage.js` — update hero content

### Add Real AI
Connect the AI tutor to Claude API:
```javascript
// In Explore.js askTutor function, replace the setTimeout with:
const response = await fetch('https://api.anthropic.com/v1/messages', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'x-api-key': process.env.REACT_APP_CLAUDE_API_KEY,
    'anthropic-version': '2023-06-01'
  },
  body: JSON.stringify({
    model: 'claude-sonnet-4-20250514',
    max_tokens: 500,
    messages: [{ role: 'user', content: chatInput }]
  })
});
```

### Add Your Environment Variables
Create a `.env` file:
```
REACT_APP_CLAUDE_API_KEY=your_key_here
```

---

## 📱 Mobile Ready
StudySnap is fully responsive. Works on:
- ✅ Desktop (1280px+)
- ✅ Tablet (768px–1024px)
- ✅ Mobile (320px–767px)

---

## 🏗 Build for Production
```bash
npm run build
```
Creates an optimized `build/` folder ready for deployment.

---

Built with ❤️ for Ethiopian students.
