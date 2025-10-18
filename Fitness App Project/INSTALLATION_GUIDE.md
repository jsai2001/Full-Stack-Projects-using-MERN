# Complete Installation Guide - Fitness App

## 🚀 Quick Setup Process

### Phase 1: Prerequisites & Installation
1. **Install Node.js** from https://nodejs.org/ (LTS version)
2. **Install VS Code** from https://code.visualstudio.com/
3. **Get API Keys**:
   - ExerciseDB: https://rapidapi.com/justin-WFnsXH_t6/api/exercisedb
   - YouTube API: https://console.developers.google.com/

### Phase 2: Project Setup
```bash
cd "/Users/jeevasai/Desktop/Personal/Full-Stack-Projects-using-MERN/Fitness App Project"

# Frontend
npx create-react-app client

# Backend
mkdir server && cd server
npm init -y
npm install express cors dotenv axios
npm install -D nodemon
```

### Phase 3: Environment Configuration
- Create `.env` files in both client and server
- Add your API keys
- Setup basic server structure

---

## Prerequisites Installation

### 1. Install Node.js and npm
```bash
# Check if already installed
node --version
npm --version

# If not installed, download from: https://nodejs.org/
# Choose LTS version (recommended)
```

### 2. Install Git (if not already installed)
```bash
# Check if installed
git --version

# If not installed, download from: https://git-scm.com/
```

### 3. Install Code Editor
- **VS Code** (recommended): https://code.visualstudio.com/
- Install React extensions: ES7+ React/Redux/React-Native snippets

## Project Setup

### Step 1: Navigate to Project Directory
```bash
cd "/Users/jeevasai/Desktop/Personal/Full-Stack-Projects-using-MERN/Fitness App Project"
```

### Step 2: Create React Frontend
```bash
# Create React app
npx create-react-app client

# Navigate to client directory
cd client

# Verify installation
npm start
# Should open http://localhost:3000 with React logo
# Press Ctrl+C to stop
```

### Step 3: Setup Backend Structure
```bash
# Go back to project root
cd ..

# Create server directory
mkdir server
cd server

# Initialize Node.js project
npm init -y

# Install backend dependencies
npm install express cors dotenv axios
npm install -D nodemon

# Create basic files
touch server.js
mkdir routes controllers middleware
```

### Step 4: Create Environment Files
```bash
# In server directory
touch .env

# In client directory
cd ../client
touch .env
```

## API Keys Setup

### 1. ExerciseDB API Key
1. Go to: https://rapidapi.com/justin-WFnsXH_t6/api/exercisedb
2. Sign up/Login
3. Subscribe to free plan
4. Copy API key

### 2. YouTube API Key
1. Go to: https://console.developers.google.com/
2. Create new project or select existing
3. Enable YouTube Data API v3
4. Create credentials (API key)
5. Copy API key

### 3. Add Keys to Environment Files
```bash
# server/.env
EXERCISEDB_API_KEY=your_exercisedb_api_key_here
YOUTUBE_API_KEY=your_youtube_api_key_here
PORT=5000

# client/.env
REACT_APP_BACKEND_URL=http://localhost:5000
```

## Project Structure Creation

### Complete Directory Structure
```
Fitness App Project/
├── client/                 # React frontend
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── App.js
│   │   ├── App.css
│   │   └── index.js
│   ├── .env
│   └── package.json
├── server/                 # Express backend
│   ├── routes/
│   ├── controllers/
│   ├── middleware/
│   ├── server.js
│   ├── .env
│   └── package.json
├── INSTALLATION_GUIDE.md
├── IMPLEMENTATION_PLAN.md
├── PART1_IMPLEMENTATION.md
└── README.md
```

## Verification Steps

### 1. Test React Frontend
```bash
cd client
npm start
# Should open http://localhost:3000
```

### 2. Test Backend Setup
```bash
cd ../server
# Create basic server.js content first (see below)
npm run dev
# Should show "Server running on port 5000"
```

### 3. Basic server.js for Testing
```javascript
const express = require('express');
const cors = require('cors');
require('dotenv').config();

const app = express();
const PORT = process.env.PORT || 5000;

app.use(cors());
app.use(express.json());

app.get('/', (req, res) => {
  res.json({ message: 'Fitness App Backend Running!' });
});

app.listen(PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
```

### 4. Update server/package.json scripts
```json
{
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js"
  }
}
```

## Installation Verification Checklist

- [ ] Node.js and npm installed
- [ ] React app created and runs on localhost:3000
- [ ] Express server setup and runs on localhost:5000
- [ ] Environment files created
- [ ] API keys obtained (ExerciseDB, YouTube)
- [ ] Project structure matches requirements
- [ ] Both frontend and backend start without errors

## Common Installation Issues

### Issue: "npx: command not found"
**Solution**: Reinstall Node.js from official website

### Issue: "Permission denied" on macOS/Linux
**Solution**: Use `sudo` or fix npm permissions:
```bash
sudo chown -R $(whoami) ~/.npm
```

### Issue: Port already in use
**Solution**: Kill process or change port:
```bash
# Kill process on port 3000/5000
lsof -ti:3000 | xargs kill -9
lsof -ti:5000 | xargs kill -9
```

### Issue: React app won't start
**Solution**: 
```bash
cd client
rm -rf node_modules package-lock.json
npm install
npm start
```

## Next Steps After Installation

1. Follow PART1_IMPLEMENTATION.md for React UI
2. Implement backend in Part 2
3. Test API integrations
4. Deploy when complete

## Development Workflow

```bash
# Terminal 1 - Frontend
cd client
npm start

# Terminal 2 - Backend
cd server
npm run dev
```

Both should run simultaneously during development.