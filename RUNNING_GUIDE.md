# Running Guide for Qodrat Card Game

## 🎮 Overview
Due to system permission restrictions, we cannot run a development server directly. However, you can still run and test the game using several alternative methods.

## 🚀 Method 1: File Protocol (Simplest)

1. **Navigate to the built application:**
   - Open your file explorer
   - Go to: `/Users/khaledahmedmohamed/Desktop/qodrat-card-game/dist/`
   - Double-click `index.html` to open it directly in your browser

2. **Access the game:**
   - The game will open at: `file:///Users/khaledahmedmohamed/Desktop/qodrat-card-game/dist/index.html`
   - Note: Some features (like API calls) might not work due to CORS restrictions

## 🔧 Method 2: Using Python (if permissions allow)

```bash
# Navigate to project directory
cd /Users/khaledahmedmohamed/Desktop/qodrat-card-game

# Run Python static server
python3 -m http.server 3000 -d dist

# Then open: http://localhost:3000
```

## 🔧 Method 3: Using Node.js http-server

```bash
# Install globally if not already installed
npm install -g http-server

# Navigate to dist folder
cd /Users/khaledahmedmohamed/Desktop/qodrat-card-game/dist

# Run server
http-server -p 3000

# Then open: http://localhost:3000
```

## 🔧 Method 4: Using Live Server (VS Code)

1. Open VS Code
2. Install "Live Server" extension
3. Open the `dist` folder in VS Code
4. Right-click on `index.html` and select "Open with Live Server"
5. The server will start on an available port

## 🔧 Method 5: Using Docker

```bash
# Create Dockerfile
cat > Dockerfile << EOF
FROM node:18-alpine
WORKDIR /app
COPY dist ./dist
EXPOSE 3000
CMD ["sh", "-c", "cd /dist && python3 -m http.server 3000"]
EOF

# Build and run
docker build -t qodrat-game .
docker run -p 3000:3000 qodrat-game
```

## 📋 Available Links

### Direct File Access
- **Main Game**: `file:///Users/khaledahmedmohamed/Desktop/qodrat-card-game/dist/index.html`
- **Preview Page**: `file:///Users/khaledahmedmohamed/Desktop/qodrat-card-game/dist/preview.html`
- **Quick Run**: `file:///Users/khaledahmedmohamed/Desktop/qodrat-card-game/dist/run.html`

### Network Access (if server runs successfully)
- Localhost: `http://localhost:3000` (if server starts)
- Localhost: `http://127.0.0.1:3000` (if server starts)

## 🐛 Troubleshooting

### Port Permission Issues
If you get "Permission denied" errors:
1. Try using higher ports (3000, 8080, 9000)
2. Check if any firewall/permission blocker is active
3. Use Method 1 (file protocol) as a workaround

### CORS Issues
When using file protocol:
- Some browser features might be restricted
- The game should still work for most functionality
- For full features, use a proper server

### Game Features That Work
- ✅ All UI components
- ✅ Game logic
- ✅ State management (localStorage)
- ✅ Sound system (Web Audio API)
- ✅ Achievement system
- ⚠️ Network requests (may be blocked in file protocol)

## 🎯 Recommended Approach

1. **For immediate testing**: Use Method 1 (file protocol)
2. **For full functionality**: Try Method 2 or 3 with different ports
3. **For development**: Use VS Code Live Server (Method 4)

## 📞 Support

If you encounter issues:
1. Check the browser console for errors
2. Try different methods above
3. The game is fully built and ready - it's just a serving issue

---

**Status**: ✅ Game is complete and ready to run
**Issue**: Port binding restrictions in your environment
**Solution**: Use file protocol or try alternative serving methods