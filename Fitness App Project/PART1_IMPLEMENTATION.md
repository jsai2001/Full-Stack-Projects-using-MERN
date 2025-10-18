# Part 1: React UI Implementation Guide

## Objective
Build the React frontend UI for exercise search and display functionality.

## Prerequisites
⚠️ **IMPORTANT**: Complete the [INSTALLATION_GUIDE.md](./INSTALLATION_GUIDE.md) first if starting from scratch.

## Step-by-Step Implementation

### Step 1: Project Setup (if not done via installation guide)
```bash
# Navigate to Fitness App Project directory
cd "Fitness App Project"

# Create React app (skip if already done)
npx create-react-app client
cd client

# Install additional dependencies (if needed)
npm install
```

### Step 2: Create App.js Structure
```javascript
import React, { useState } from 'react';
import './App.css';

function App() {
  // Step 2.1: Initialize State Variables
  const [bodyPart, setBodyPart] = useState('');
  const [exercises, setExercises] = useState([]);

  // Step 2.2: Handle Input Validation
  const handleSearch = () => {
    if (!bodyPart.trim()) {
      alert("Please enter a body part");
      return;
    }
    fetchExercises();
  };

  // Step 2.3: Fetch Function (placeholder for now)
  const fetchExercises = async () => {
    try {
      // Backend URL will be added in Part 2
      console.log(`Searching for: ${bodyPart}`);
      // Temporary: Set empty array until backend is ready
      setExercises([]);
    } catch (error) {
      console.error('Error fetching exercises:', error);
    }
  };

  return (
    <div className="App">
      <header className="App-header">
        <h1>Fitness Exercise Finder</h1>
        
        {/* Search Section */}
        <div className="search-section">
          <input
            type="text"
            value={bodyPart}
            onChange={(e) => setBodyPart(e.target.value)}
            placeholder="Enter body part (e.g., chest, legs)"
            className="search-input"
          />
          <button onClick={handleSearch} className="search-button">
            Search
          </button>
        </div>

        {/* Exercises Display Section */}
        <div className="exercises-section">
          <h2>Exercises</h2>
          {exercises.length > 0 ? (
            <div className="exercises-grid">
              {exercises.map((exercise, index) => (
                <div key={index} className="exercise-card">
                  <img 
                    src={exercise.gifUrl} 
                    alt={exercise.name}
                    className="exercise-gif"
                  />
                  <h3>{exercise.name}</h3>
                </div>
              ))}
            </div>
          ) : (
            <p>No exercises found. Try searching for a body part!</p>
          )}
        </div>
      </header>
    </div>
  );
}

export default App;
```

### Step 3: Update App.css (Basic Styling)
```css
.App {
  text-align: center;
}

.App-header {
  background-color: #282c34;
  padding: 20px;
  color: white;
  min-height: 100vh;
}

.search-section {
  margin: 20px 0;
}

.search-input {
  padding: 10px;
  margin-right: 10px;
  border: none;
  border-radius: 5px;
  width: 300px;
}

.search-button {
  padding: 10px 20px;
  background-color: #61dafb;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-weight: bold;
}

.search-button:hover {
  background-color: #21a9c7;
}

.exercises-section {
  margin-top: 40px;
}

.exercises-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 20px;
  margin-top: 20px;
}

.exercise-card {
  background-color: white;
  color: black;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

.exercise-gif {
  width: 100%;
  max-width: 250px;
  height: auto;
  border-radius: 5px;
}
```

### Step 4: Test the Implementation

1. **Start the React app**:
   ```bash
   npm start
   ```

2. **Test the functionality**:
   - Enter a body part in the search field
   - Click "Search" button
   - Verify alert shows for empty input
   - Check console for search log

### Step 5: Verification Checklist

- [ ] State variables initialized correctly
- [ ] Input validation works (shows alert for empty input)
- [ ] Search function logs the body part to console
- [ ] UI displays "No exercises found" message
- [ ] Styling looks clean and responsive

## Expected Behavior at This Stage

- ✅ User can type in search input
- ✅ Empty input shows validation alert
- ✅ Valid input logs to console
- ❌ No actual exercises display (backend needed)
- ✅ Clean, responsive UI

## Next Steps

After completing Part 1:
1. Move to Part 2: Express Backend setup
2. Connect ExerciseDB API
3. Update fetch function to call backend
4. Test with real exercise data

## Common Issues & Solutions

**Issue**: React app won't start
**Solution**: Ensure Node.js is installed, run `npm install` first

**Issue**: Styling not applied
**Solution**: Verify App.css is imported in App.js

**Issue**: State not updating
**Solution**: Check useState import and proper state setter usage