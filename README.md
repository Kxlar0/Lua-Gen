# 🎮 Manifest & Lua Generator

A modern web application for generating Steam game manifest files and Lua injection scripts. Features **live game preview** with cover art, game name, and direct instant downloads (no shortlinks).

**🚀 Live Demo:** Deploy on GitHub Pages and share the link with anyone!

## ✨ Features

- 🎮 **Steam Game Lookup** - Enter App ID to preview game info and cover art
- 📊 **Live Game Preview** - See game name, App ID, and description before generating
- 📋 **Inject Script Generation** - Auto-generates Lua injection scripts for steamtools
- 📥 **Direct Downloads** - Instant downloads without any redirects or shortlinks
- 🌙 **Dark Theme** - Modern, eye-friendly dark UI inspired by steamtools.site
- ⚡ **Fast & Responsive** - Works instantly, 100% client-side processing
- 🛡️ **Safe & Secure** - All processing done locally in your browser, no server data collection
- 📱 **Mobile Friendly** - Works perfectly on desktop, tablet, and mobile devices

## 🚀 Deployment

### Option 1: GitHub Pages (Recommended - Free & Easy)

1. **Fork or create a repository** on GitHub
2. **Go to Settings → Pages**
3. **Source:** Select `Deploy from a branch`
4. **Branch:** Select `main` 
5. **Folder:** Select `/root` (or `/` - which deploys from repository root)
6. **Save** - GitHub will automatically deploy the `public` folder

Your site will be live at: `https://yourusername.github.io/your-repo-name`

### Option 2: Manual Local Setup

```bash
# Clone your repository
git clone https://github.com/yourusername/lua-gen.git
cd lua-gen

# Install dependencies (optional - only if you want to run backend)
npm install

# For GitHub Pages: Just push the public/ folder to GitHub
# GitHub will automatically serve index.html from public/ folder

# Or run locally with Node.js
npm start
# Visit http://localhost:3000
```

### Option 3: Deploy on Vercel (Easiest Alternative)

1. Go to [vercel.com](https://vercel.com)
2. Connect your GitHub repository
3. Select the project
4. Set "Root Directory" to `public`
5. Deploy - Vercel will provide you a live URL instantly

### Option 4: Deploy on Netlify

1. Go to [netlify.com](https://netlify.com)
2. Click "Connect your own site" → GitHub
3. Select your repository
4. Set "Publish directory" to `public`
5. Deploy - Get a live URL immediately

## 📝 How to Use

1. **Visit the website** (or open `public/index.html` locally)
2. **Enter Steam App ID** (Find it at [steamdb.info](https://steamdb.info))
   - Example: 730 (CS:GO), 570 (Dota 2), 440 (Team Fortress 2)
3. **Click "Generate Files"**
4. **Preview game details** - See cover art, game name, and info
5. **Download files:**
   - `inject_[appid].lua` - Lua injection script for steamtools
   - `manifest_[appid].json` - Manifest metadata (for reference)

## 📁 Project Structure

```
lua-gen/
├── public/
│   └── index.html              # Main application (GitHub Pages serves this)
├── .github/
│   └── workflows/
│       └── pages.yml           # GitHub Pages auto-deployment
├── .gitignore                  # Git ignore rules
├── server.js                   # Optional: Local Express server
├── package.json                # Node.js dependencies
└── README.md                   # This file
```

## 🎯 How It Works

### Game Preview
1. **API Call** → Fetches game data from Steam Web API
2. **Cover Image** → Displays game header from Steam CDN
3. **Game Details** → Shows name, description, and App ID

### File Generation (100% Client-Side)
1. **Lua Inject Script** - Generates commands for steamtools:
   ```lua
   addappid(431960)
   addappid(431960,0,"[hash]")
   setManifestid(431960,"[id]")
   ```

2. **Manifest JSON** - Contains metadata:
   ```json
   {
     "appid": 431960,
     "game_name": "Game Name",
     "depotid": 0,
     "manifestid": "unique-id",
     "hash": "sha256-like-hash"
   }
   ```

## 🔧 Technology Stack

- **Frontend:** HTML5, Tailwind CSS, Vanilla JavaScript
- **API:** Steam Web API (public, no authentication needed)
- **File Download:** Blob API for direct browser downloads
- **Hosting:** GitHub Pages, Vercel, Netlify, or any static host

## 📊 Supported Steam Games

Works with **ANY** Steam game. Just get the App ID from:
- [SteamDB.info](https://steamdb.info) - Search game name
- [Steam Store](https://store.steampowered.com) - Check URL (appid=number)
- Steam client - Right-click game → Properties → copy App ID from URL

## ⚙️ Local Development

### Requirements
- Node.js 14+ (optional, only if running local server)
- Modern web browser

### Run Locally

```bash
# Option A: Pure static (no server needed)
# Just open public/index.html in your browser

# Option B: With local Node.js server
npm install
npm start
# Visit http://localhost:3000
```

## 🛡️ Privacy & Security

✅ **100% Client-Side Processing**
- No data sent to external servers (except Steam API for game info)
- App ID only used to fetch public game metadata
- Files generated entirely in your browser
- Direct downloads with no tracking or redirects

## 🤝 Contributing

Feel free to:
- Report bugs or issues
- Suggest features
- Fork and create your own version
- Share improvements via pull requests

## 📜 License

Free to use, modify, and distribute.

## 🎓 Educational Resources

### Understanding Steam App IDs
- Browse games at [SteamDB.info](https://steamdb.info)
- Check store links: `store.steampowered.com/app/[APPID]`
- Find in Steam client properties

### About Manifest & Lua Files
- **manifest.json** - Game metadata and configuration
- **inject.lua** - Commands to register games with steamtools
- Both files work together for game downloading and management

## 🚀 Quick Start for GitHub Pages

```bash
# 1. Create repo on GitHub
# 2. Clone locally
git clone https://github.com/yourusername/lua-gen.git
cd lua-gen

# 3. Push to main branch
git add .
git commit -m "Initial commit"
git push origin main

# 4. Enable GitHub Pages in Settings
# Settings → Pages → Branch: main → /root folder → Save

# Done! Your site is live at:
# https://yourusername.github.io/lua-gen
```

## 📞 Support

For issues, questions, or suggestions:
1. Check that you're using a valid Steam App ID
2. Try a different App ID to test functionality
3. Clear browser cache and reload
4. Check browser console (F12) for error messages

---

**Manifest & Lua Generator** • GitHub Pages Ready • Direct Download Version • No External Dependencies

Generated files are compatible with [steamtools](https://steamtools.net/) for game downloading and management.

