🏋️ **Welcome to the Fitness App project!**

In this project, you’ll build a complete fitness web app that helps users explore exercises based on their selected body part.

By the end of all four parts, you’ll have a full-stack application that:

- Lets users search workouts by muscle group (like *legs*, *chest*, or *back*).
- Fetches exercise data from a real API.
- Displays workout demonstration GIFs and related YouTube videos.
- Integrates both frontend (**React**) and backend (**Express**) seamlessly.

---

### **Project Breakdown**

This project is divided into four key parts:

1. **Part 1:** Build the React UI for Exercise Display
2. **Part 2:** Connect Express Backend with ExerciseDB API
3. **Part 3:** Add YouTube Video Display in React UI
4. **Part 4:** Integrate YouTube API for Related Workout Videos

---

## **Part 1: Build the React UI for Exercise and Equipment Display**
✨ **Build the Core Workout Search Experience!**

In this first part, you’ll focus on building the React frontend UI that allows users to search for exercises by body part and view the related workout images.
The structure and layout of the component are already provided—you’ll just need to complete the missing logic.

---

### **Starter Setup**

Your starter code already includes:

- A main **App** component with an input field, button, and display areas for exercises and equipment.
- Comments and placeholders showing exactly where you need to fill in the missing logic.
- All required libraries are already installed; there’s no need to install anything. You can simply focus on completing the functionality.
- The styling file *App.css* is already provided for you. You don’t need to modify or implement it.

---

### **What the App Should Do**

By the end of this part, your app should:

- Accept a body part input from the user (e.g., *“Upper legs”*, *“chest”*, *“waist”*).
- Fetch related exercises from the backend (to be connected in Part 2).
- Display each exercise as an image (using its `gifUrl` property).

---

### **Your Tasks**

**1. Initialize State Variables**
   - Initialize `bodyPart` as an empty string.
   - Initialize `exercises` as an empty array.
   - *Docs*: React useState Hook

**2. Handle Input Validation**
   - When the “Search” button is clicked:
     - If the input is empty, show an alert:  
       `"Please enter a body part"`
     - Otherwise, fetch data from the backend using `fetch()`.
   - *Docs*: Event Handling in React

**3. Fetch and Update State**
   - Use the backend domain helper function to get the correct backend URL.
   - Fetch exercise data for the entered body part.
   - Parse the response and update the state variables for exercises accordingly.
   - *Docs*: Fetch API

**4. Render the Data in the UI**
   - Display exercise images and names under the “Exercises” section.
   - Show clear messages like *“No exercises found”* when no data is available.
   - *Docs*: Display lists in React

---

### **Expected Behaviour**

> **Note:** For now, you won’t see any actual exercise GIFs appear when searching—the backend that provides this data will be implemented in Part 2.