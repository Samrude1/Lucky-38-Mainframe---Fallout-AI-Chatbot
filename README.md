# 🎰 Lucky 38 Mainframe - Matrix AI Chatbot

<div align="center">

![Lucky 38 Mainframe Interface](./public/Näyttökuva%202026-02-08%20105459.png)

**An immersive, retro-futuristic AI chatbot experience themed after Fallout: New Vegas**

[![TypeScript](https://img.shields.io/badge/TypeScript-5.8-blue?logo=typescript)](https://www.typescriptlang.org/)
[![React](https://img.shields.io/badge/React-19.2-61dafb?logo=react)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-6.2-646cff?logo=vite)](https://vitejs.dev/)
[![Google Gemini](https://img.shields.io/badge/Google_Gemini-AI-4285f4?logo=google)](https://ai.google.dev/)

*Experience authentic Pip-Boy aesthetics with CRT effects, dynamic AI responses, and live system metrics*

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Screenshots & Demo](#-screenshots--demo)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Getting Started](#-getting-started)
- [Configuration](#-configuration)
- [Development](#-development)
- [Deployment](#-deployment)
- [Customization](#-customization)
- [Project Structure](#-project-structure)
- [API Reference](#-api-reference)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

**Lucky 38 Mainframe AI Chatbot** is a sophisticated web application that brings the iconic Mr. House character from Fallout: New Vegas to life through Google's Gemini AI. The application features a meticulously crafted retro-futuristic interface with authentic Pip-Boy aesthetics, complete with CRT screen effects, dynamic emotional states, and real-time system metrics.

### Key Highlights

- 🎭 **Immersive AI Persona**: Fully in-character responses as Robert House with dynamic emotional states
- 🖥️ **Authentic Retro Design**: CRT effects, scanlines, phosphor glow, and terminal aesthetics
- 📊 **Live System Metrics**: Real-time session tracking, memory usage, and reactor power monitoring
- 🎨 **Premium UX**: Smooth animations, responsive design, and accessibility-focused implementation
- ⚡ **Modern Tech Stack**: Built with React 19, TypeScript, and Vite for optimal performance

---

## ✨ Features

### 🎭 AI Persona System

- **Character-Driven Responses**: AI embodies Robert House, CEO of RobCo Industries
- **Dynamic Emotional States**: Four distinct moods (NEUTRAL, AMUSED, ANNOYED, CALCULATING)
- **Context-Aware Dialogue**: Maintains character consistency across conversations
- **Mood Detection**: Automatic parsing of emotional state from AI responses
- **Visual Feedback**: Portrait expressions change based on current mood

### 🖥️ Retro-Futuristic Interface

#### CRT Screen Effects
- **Scanlines**: Authentic CRT monitor horizontal lines
- **Phosphor Glow**: Green text bloom effect mimicking old monitors
- **Chromatic Aberration**: Subtle RGB color separation
- **Screen Flicker**: Realistic power fluctuation animation
- **Vignette Effect**: Darkened corners for depth

#### Typography & Colors
- **Monospaced Font**: Share Tech Mono from Google Fonts
- **Vibrant Green**: Primary color `#1aff1a` (Pip-Boy green)
- **High Contrast**: Black background `#0a0a0a` for readability
- **Custom Scrollbars**: Themed scrollbars matching the aesthetic

### 🤖 Interactive Portrait System

- **Pixelated Art Style**: Retro-styled Mr. House portrait
- **Dynamic Expressions**: Visual mood changes synchronized with AI responses
- **Responsive Layout**: 
  - Desktop: Sidebar placement with system metrics
  - Mobile: Top placement for optimal viewing
- **Smooth Transitions**: Animated mood changes

### 📊 Live System Metrics

Real-time dashboard displaying:

| Metric | Description | Update Frequency |
|--------|-------------|------------------|
| **Session Uptime** | HH:MM:SS format timer | Every second |
| **Memory Usage** | Dynamic calculation (messages × 64 KB) | Per message |
| **Reactor Power** | Fluctuating 98-100% | Every 2 seconds |
| **Current Mood** | Visual mood indicator | Per AI response |

### 🎨 Premium Design Elements

- **Smooth Animations**: CSS transitions and keyframe animations
- **Hover Effects**: Interactive feedback on all clickable elements
- **Responsive Design**: Mobile-first approach with breakpoints
- **Accessibility**: 
  - Semantic HTML5 elements
  - ARIA labels where appropriate
  - Keyboard navigation support
- **Performance Optimized**: Lazy loading and efficient re-renders

---

## 📸 Screenshots & Demo

### Desktop View
![Desktop Interface](./public/Näyttökuva%202026-02-08%20105459.png)

### Key Interface Elements

1. **Header**: Lucky 38 Mainframe title with text bloom effect
2. **Sidebar** (Desktop): Mr. House portrait + system metrics
3. **Chat Area**: Message history with user/AI distinction
4. **Input Field**: Terminal-style input with send button
5. **Status Indicators**: Real-time mood and system status

---

## 🛠️ Tech Stack

### Core Technologies

| Technology | Version | Purpose |
|------------|---------|---------|
| **React** | 19.2.0 | UI framework with latest features |
| **TypeScript** | 5.8.2 | Type-safe development |
| **Vite** | 6.2.0 | Lightning-fast build tool |
| **Google Gemini AI** | 1.30.0 | Advanced AI conversation engine |

### Styling & UI

- **Tailwind CSS** (CDN): Utility-first CSS framework
- **Custom CSS**: CRT effects and animations
- **Google Fonts**: Share Tech Mono for terminal aesthetic

### Development Tools

- **@vitejs/plugin-react**: React Fast Refresh support
- **@types/node**: Node.js type definitions
- **ES2022**: Modern JavaScript features

---

## 🏗️ Architecture

### Component Hierarchy

```
App.tsx
└── ChatWindow.tsx (Main Container)
    ├── MrHousePortrait.tsx (Mood Display)
    ├── ChatMessage.tsx (Message Renderer)
    └── ChatInput.tsx (User Input)
```

### State Management

**ChatWindow.tsx** manages all application state:

- `messages`: Message history array
- `isLoading`: AI response loading state
- `error`: Error message display
- `currentMood`: AI emotional state
- `uptime`: Session timer
- `powerLevel`: Reactor fluctuation
- `chatRef`: Gemini AI chat instance

### Data Flow

```
User Input → ChatInput → ChatWindow (handleSendMessage)
    ↓
Gemini AI API Request
    ↓
Response Processing (Mood Parsing)
    ↓
State Updates (messages, currentMood)
    ↓
UI Re-render (ChatMessage, MrHousePortrait)
```

### AI Integration

**Gemini AI Configuration:**
- Model: `gemini-2.0-flash-exp`
- System Instruction: Mr. House persona with mood tagging
- Chat History: Maintained via `chatRef`
- Mood Detection: Regex parsing of `[MOOD: STATE]` tags

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have:

- **Node.js** (v16.0.0 or higher) - [Download](https://nodejs.org/)
- **npm** (comes with Node.js) or **yarn**
- **Gemini API Key** - [Get one free](https://aistudio.google.com/apikey)

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/Samrude1/Lucky-38-Mainframe---Matrix-AI-Chatbot.git
cd fallout-ai-chatbot
```

2. **Install dependencies**

```bash
npm install
```

3. **Configure environment variables**

Create a `.env.local` file in the project root:

```env
# Gemini API Configuration
GEMINI_API_KEY=your_actual_api_key_here
API_KEY=your_actual_api_key_here
```

> **Note**: Both `GEMINI_API_KEY` and `API_KEY` are required due to Vite configuration

4. **Start the development server**

```bash
npm run dev
```

5. **Open in browser**

Navigate to `http://localhost:3000` (configured in `vite.config.ts`)

### Verification

You should see:
- ✅ Lucky 38 Mainframe header
- ✅ Mr. House portrait with NEUTRAL mood
- ✅ Initial greeting message
- ✅ System metrics updating
- ✅ Input field ready for messages

---

## ⚙️ Configuration

### Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `GEMINI_API_KEY` | Yes | Your Google Gemini API key |
| `API_KEY` | Yes | Alias for Gemini API key (Vite compatibility) |

### Vite Configuration

**vite.config.ts** includes:

```typescript
server: {
  port: 3000,
  host: '0.0.0.0', // Allows network access
}
```

**Environment Variable Mapping:**
```typescript
define: {
  'process.env.API_KEY': JSON.stringify(env.GEMINI_API_KEY),
  'process.env.GEMINI_API_KEY': JSON.stringify(env.GEMINI_API_KEY)
}
```

### TypeScript Configuration

**tsconfig.json** highlights:
- Target: ES2022
- Module: ESNext
- JSX: react-jsx (React 19 automatic runtime)
- Path alias: `@/*` for root imports

---

## 💻 Development

### Available Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server (port 3000) |
| `npm run build` | Build production bundle |
| `npm run preview` | Preview production build locally |

### Development Workflow

1. **Start dev server**: `npm run dev`
2. **Make changes**: Edit files in `components/`, `hooks/`, or root
3. **Hot reload**: Vite automatically refreshes on save
4. **Test**: Interact with the chatbot in browser
5. **Build**: `npm run build` before deployment

### Code Style Guidelines

- **TypeScript**: Use strict typing, avoid `any`
- **React**: Functional components with hooks
- **CSS**: Tailwind utilities + custom CSS for effects
- **Naming**: 
  - Components: PascalCase (`ChatWindow.tsx`)
  - Hooks: camelCase with `use` prefix (`useSoundEffects.ts`)
  - Constants: UPPER_SNAKE_CASE

### Debugging

**Common Issues:**

1. **API Key Error**
   - Check `.env.local` exists and contains valid key
   - Restart dev server after changing `.env.local`

2. **Build Errors**
   - Clear `node_modules` and reinstall: `rm -rf node_modules && npm install`
   - Check TypeScript errors: `npx tsc --noEmit`

3. **CRT Effects Not Showing**
   - Ensure `index.css` is imported in `index.html`
   - Check browser DevTools for CSS errors

---

## 🌐 Deployment

### Build for Production

```bash
npm run build
```

This creates an optimized bundle in the `dist/` directory.

### Deployment Platforms

#### Vercel (Recommended)

1. Install Vercel CLI: `npm i -g vercel`
2. Run: `vercel`
3. Add environment variable `GEMINI_API_KEY` in Vercel dashboard

#### Netlify

1. Build command: `npm run build`
2. Publish directory: `dist`
3. Add environment variable in Netlify settings

#### GitHub Pages

1. Update `vite.config.ts` with base path:
   ```typescript
   export default defineConfig({
     base: '/repository-name/',
     // ... rest of config
   })
   ```
2. Build and deploy `dist/` folder

### Environment Variables in Production

Ensure your deployment platform has:
- `GEMINI_API_KEY` set to your API key
- Build command includes environment variable loading

---

## 🎨 Customization

### Change AI Personality

Edit `components/ChatWindow.tsx` (line 62):

```typescript
systemInstruction: 'You are Robert House...' // Replace with your persona
```

**Example Alternative Personas:**
- Vault-Tec Representative
- Brotherhood of Steel Scribe
- NCR Ranger

### Modify Color Scheme

Edit `index.css` root variables:

```css
:root {
  --pip-green: #1aff1a;      /* Primary color */
  --pip-green-dim: #00b300;  /* Dimmed variant */
  --pip-bg: #0a0a0a;         /* Background */
}
```

**Alternative Color Schemes:**
- **Amber Terminal**: `#ffb000` (classic amber monitors)
- **Blue Screen**: `#00aaff` (IBM terminal blue)
- **Red Alert**: `#ff0000` (danger/warning theme)

### Adjust CRT Effects

In `index.css`, modify:

```css
/* Scanline intensity */
.crt::before {
  background: linear-gradient(
    rgba(18, 16, 16, 0) 50%,
    rgba(0, 0, 0, 0.25) 50% /* Adjust opacity */
  );
}

/* Flicker animation */
@keyframes flicker {
  0%, 100% { opacity: 0.98; }
  50% { opacity: 1; } /* Adjust flicker range */
}
```

### Add Custom Moods

1. Update `types.ts`:
   ```typescript
   export type Mood = 'NEUTRAL' | 'AMUSED' | 'ANNOYED' | 'CALCULATING' | 'EXCITED';
   ```

2. Update AI system instruction to include new mood

3. Add visual representation in `MrHousePortrait.tsx`

### Modify System Metrics

Edit `ChatWindow.tsx` calculations:

```typescript
// Memory calculation (line 155)
<span>{messages.length * 64} KB</span> // Change multiplier

// Reactor fluctuation (line 38)
const change = (Math.random() - 0.5) * 0.2; // Adjust range
```

---

## 📁 Project Structure

```
fallout-ai-chatbot/
│
├── components/                 # React components
│   ├── ChatWindow.tsx         # Main container (215 lines)
│   │   ├── State management
│   │   ├── AI integration
│   │   ├── System metrics
│   │   └── Layout orchestration
│   │
│   ├── ChatMessage.tsx        # Message bubble renderer
│   │   ├── User/AI distinction
│   │   └── Styling variants
│   │
│   ├── ChatInput.tsx          # User input field
│   │   ├── Send button
│   │   ├── Enter key handler
│   │   └── Loading state
│   │
│   └── MrHousePortrait.tsx    # Dynamic portrait
│       ├── Mood-based rendering
│       └── Pixel art styling
│
├── hooks/                      # Custom React hooks
│   └── useSoundEffects.ts     # Audio effects (future feature)
│
├── public/                     # Static assets
│   └── Näyttökuva...png       # Screenshot
│
├── App.tsx                     # Root component
├── index.tsx                   # React entry point
├── index.css                   # Global styles + CRT effects
├── types.ts                    # TypeScript definitions
├── constants.ts                # App configuration
│
├── vite.config.ts              # Vite configuration
├── tsconfig.json               # TypeScript configuration
├── package.json                # Dependencies
├── .gitignore                  # Git ignore rules
├── .env.local                  # Environment variables (not in Git)
└── README.md                   # This file
```

### Key Files Explained

| File | Lines | Purpose |
|------|-------|---------|
| `ChatWindow.tsx` | 215 | Core application logic and state |
| `index.css` | ~220 | CRT effects and global styles |
| `MrHousePortrait.tsx` | ~150 | Dynamic portrait rendering |
| `ChatMessage.tsx` | ~80 | Message display component |
| `ChatInput.tsx` | ~70 | User input handling |

---

## 📚 API Reference

### Gemini AI Integration

**Initialization:**
```typescript
const ai = new GoogleGenAI({ apiKey: process.env.API_KEY });
const chat = ai.chats.create({
  model: 'gemini-2.0-flash-exp',
  config: { systemInstruction: '...' }
});
```

**Sending Messages:**
```typescript
const response = await chat.sendMessage({ message: userText });
const aiText = response.text;
```

**Mood Parsing:**
```typescript
const moodMatch = responseText.match(/\[MOOD:\s*(NEUTRAL|AMUSED|ANNOYED|CALCULATING)\]/i);
const mood = moodMatch ? moodMatch[1].toUpperCase() : 'NEUTRAL';
```

### Component Props

**ChatMessage:**
```typescript
interface ChatMessageProps {
  message: {
    id: string;
    text: string;
    author: 'user' | 'ai';
  };
}
```

**MrHousePortrait:**
```typescript
interface MrHousePortraitProps {
  mood: 'NEUTRAL' | 'AMUSED' | 'ANNOYED' | 'CALCULATING';
}
```

**ChatInput:**
```typescript
interface ChatInputProps {
  onSendMessage: (text: string) => void;
  isLoading: boolean;
}
```

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

### How to Contribute

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Make your changes**
4. **Test thoroughly**
5. **Commit with clear messages**: `git commit -m 'Add amazing feature'`
6. **Push to your fork**: `git push origin feature/amazing-feature`
7. **Open a Pull Request**

### Contribution Ideas

- 🎨 Additional CRT effect presets
- 🔊 Sound effects integration
- 🌐 Internationalization (i18n)
- 📱 Mobile app version (React Native)
- 🎭 More Fallout character personas
- 📊 Advanced analytics dashboard
- 🎮 Easter eggs and hidden features

### Code Review Process

All PRs will be reviewed for:
- Code quality and TypeScript compliance
- UI/UX consistency
- Performance impact
- Documentation updates

---

## 📝 License

This project is created for **educational and demonstration purposes**.

### Third-Party Assets

- **Fallout Universe**: Inspired by Bethesda's Fallout: New Vegas
- **Google Gemini**: AI powered by Google
- **Fonts**: Share Tech Mono (Open Font License)

### Disclaimer

This is a fan project and is not affiliated with or endorsed by Bethesda Softworks or Obsidian Entertainment.

---

## 🙏 Acknowledgments

### Inspiration

- **Fallout: New Vegas** - For the iconic Mr. House character and Lucky 38 casino
- **Pip-Boy Interface** - For the retro-futuristic design language
- **CRT Monitors** - For authentic terminal aesthetics

### Technologies

- **Google Gemini AI** - Advanced conversational AI capabilities
- **React Team** - For the excellent React 19 framework
- **Vite Team** - For lightning-fast development experience
- **Tailwind CSS** - For utility-first styling approach

### Community

Special thanks to:
- Fallout community for keeping the franchise alive
- Open source contributors
- Beta testers and early users

---

## 📞 Contact & Support

- **GitHub Issues**: [Report bugs or request features](https://github.com/Samrude1/Lucky-38-Mainframe---Matrix-AI-Chatbot/issues)
- **Discussions**: [Join the conversation](https://github.com/Samrude1/Lucky-38-Mainframe---Matrix-AI-Chatbot/discussions)

---

<div align="center">

**Built with ❤️ and ☢️ by the Wasteland**

*"The game was rigged from the start."* - Mr. House

</div>
