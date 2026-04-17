# Development Guide for Qodrat Card Game

## 🎮 About the Project

Qodrat Card Game is a sophisticated educational card game designed for Saudi high school students preparing for Qiyas exams. The game features strategic gameplay based on knowledge rather than luck, with two main game modes: Koutchina and Poker.

## 🚀 How to Run

### Option 1: Using Vite (Recommended)
```bash
# Install dependencies
npm install

# Build the project
npm run build

# The build outputs to /dist folder
# You can serve the dist folder using any static server
```

### Option 2: Static Server
Since there are permission issues with binding to ports in your environment, you can use any static file server:

```bash
# Using Python (if available)
python -m http.server 8000 -d dist

# Or use Node.js http-server (install first)
npm install -g http-server
http-server dist -p 8000

# Or use serve (install first)
npm install -g serve
serve dist
```

### Option 3: Open Directly
You can also open `dist/index.html` directly in your browser (though some features might not work due to CORS).

## 🛠️ Development Scripts

- `npm run dev` - Start development server (currently not working due to port permissions)
- `npm run build` - Build for production ✅
- `npm run lint` - Run ESLint (if configured)

## 📁 Project Structure

```
src/
├── components/     # React components
├── hooks/         # Custom React hooks
├── pages/          # Page components
├── store/         # Zustand state management
├── types/          # TypeScript interfaces
├── utils.ts        # Utility functions
└── App.tsx         # Main app component
```

## 🎯 Key Features

### Game Modes
1. **Koutchia Mode** - Choose 5 cards and bid on expected points
2. **Poker Mode** - Build the best poker hand with 5 cards

### Card Types
- ♠ Spades - Verbal questions (deep)
- ♥ Hearts - Quantitative questions (strong)
- ♦ Diamonds - Contextual questions (tricky)
- ♣ Clubs - Statistical questions (psychological pressure)

### Technical Stack
- React 18 + TypeScript
- Zustand for state management
- Framer Motion for animations
- Tailwind CSS for styling
- Vite for build tool

## 🏗️ Build Output

The build creates a `dist/` folder with:
- `index.html` - Main HTML file
- `assets/` - JavaScript, CSS, and other assets
- `images/` - Static images
- `sounds/` - Audio files

## 🐛 Known Issues

1. **Port Binding**: Development server can't bind to ports due to permission restrictions
2. **Static Assets**: All assets are properly included in the build

## ✅ Current Status

- ✅ TypeScript compilation successful
- ✅ Build completes without errors
- ✅ All components and pages implemented
- ✅ State management working
- ✅ RTL layout implemented
- ✅ Question bank populated
- ⚠️ Development server requires port workaround