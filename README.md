Student Tracker – React + Firebase

This is your React project from `student-tracker.zip`.

```markdown
# Student Tracker – React + Firebase (Vite)

A simple **React** application that demonstrates a basic **Create + Read (CR)** workflow using **Firebase Firestore** as the backend.

The app allows you to:
- Add new students with a name and course
- Save them to a Firestore collection
- Load and display the list of students on demand

Built with **React 18**, **Vite**, and **Firebase v10 modular SDK**.

---

## ✨ Features

### 📝 Create – Student Form
- Controlled form built with React hooks (`useState`)
- Fields:
  - `name`
  - `course`
- On submit:
  - Writes a new document to a Firestore collection (e.g., `students`)
  - Attaches a `createdAt` field using `serverTimestamp()`
- UI feedback:
  - Shows loading state while submitting
  - Displays success message on save
  - Displays error message if something goes wrong

### 📖 Read – Student List
- Fetches students from Firestore only when the user clicks **"Load Students"**
- Uses Firestore **queries**:
  - `collection(...)`
  - `orderBy('createdAt', 'desc')`
- Displays data in a simple table:
  - Student name
  - Course
- Handles:
  - Loading state (e.g., “Loading students…”)
  - Error state (API or network issues)
  - Empty state (e.g., “No students found.”)

### ☁️ Firebase Integration
- Uses **Firebase v10 modular SDK**
- Firestore initialized in a dedicated `firebase.js` module
- Environment variables stored in a `.env` file and loaded via **Vite** (`import.meta.env`)

---

## 🧰 Tech Stack

- **React 18**
- **Vite**
- **Firebase (Firestore)**
- **JavaScript (ES Modules)**
- **CSS (App.css / index.css)**

Key files:

- `src/App.jsx`  
  - Composes `<StudentForm />` and `<StudentList />` into the main layout
- `src/components/StudentForm.jsx`  
  - Handles the **Create** operation using Firestore `addDoc` and `serverTimestamp`
- `src/components/StudentList.jsx`  
  - Handles the **Read** operation using Firestore `getDocs`, `collection`, and `orderBy`
- `src/firebase.js`  
  - Initializes Firebase and exports the Firestore instance (`db`)
- `vite.config.js`, `main.jsx`, `App.css`, `index.css`

---

## 📁 Project Structure

```text
student-tracker/
├── index.html
├── vite.config.js
├── package.json
├── package-lock.json
├── .env.example        # you can create this file for sample config
└── src/
    ├── main.jsx
    ├── App.jsx
    ├── App.css
    ├── index.css
    ├── firebase.js
    └── components/
        ├── StudentForm.jsx
        └── StudentList.jsx

---

## 🔧 Getting Started
1. Clone the repository
2. Install dependencies (npm install)
3. Configure Firebase

Create a .env file in the root of the project (same level as package.json) with:
VITE_FIREBASE_API_KEY=your_api_key
VITE_FIREBASE_AUTH_DOMAIN=your_auth_domain
VITE_FIREBASE_PROJECT_ID=your_project_id
VITE_FIREBASE_STORAGE_BUCKET=your_storage_bucket
VITE_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
VITE_FIREBASE_APP_ID=your_app_id

4. Run the app in development

---

## 🧠 What I Learned
Setting up a React + Vite application
Integrating Firebase Firestore using the v10 modular SDK
Using controlled components and useState for form handling
Implementing Create (addDoc) and Read (getDocs) operations
Working with Firestore queries and orderBy for sorting
Managing loading, error, and success states in the UI
Keeping secrets out of source control using .env and Vite’s import.meta.env

---

## 🚀 Possible Future Enhancements
Add Update and Delete to complete full CRUD
Add search or filter by course or name
Add pagination or infinite scroll for large datasets
Add authentication so only signed-in users can add or view students
Improve styling using a UI framework (Tailwind, MUI, etc.)
Add unit tests or integration tests for key components

---

## 📄 License
This project is available for educational and portfolio use.
