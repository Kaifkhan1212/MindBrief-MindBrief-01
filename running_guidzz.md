# 🚀 MindBrief - Running Guide

A complete guide to set up and run the MindBrief AI Summarizer project.

---

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** 18.0.0 or higher
- **npm** (Node Package Manager)
- A **Google Gemini API Key** (Free tier available at [Google AI Studio](https://makersuite.google.com/app/apikey))
- A **Firebase Project** (for authentication)

---

## 🔧 Step 1: Clone the Repository

```bash
git clone https://github.com/Kaifkhan1212/MindBrief-MindBrief-01.git
cd MindBrief-MindBrief-01
```

---

## 🔐 Step 2: Set Up Firebase

### 2.1 Create a Firebase Project

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Click "Add project" and follow the setup wizard
3. Once created, go to **Project Settings** → **General** → **Your apps**
4. Click the web icon (`</>`) to add a web app
5. Copy the Firebase config values

### 2.2 Enable Authentication

1. In Firebase Console, go to **Authentication** → **Sign-in method**
2. Enable **Email/Password** provider
3. Enable **Google** provider (set a support email)
4. Go to **Settings** → **Authorized domains** and ensure `localhost` is listed

---

## ⚙️ Step 3: Configure Environment Variables

### 3.1 Backend Configuration

Create a `.env` file in the `backend` folder:

```bash
cd backend
```

Create `.env` with the following content:

```env
PORT=5000
FRONTEND_URL=http://localhost:3000
GEMINI_API_KEY=your_gemini_api_key_here
```

> 💡 **Get your Gemini API Key**: Visit [Google AI Studio](https://makersuite.google.com/app/apikey) to generate a free API key.

### 3.2 Frontend Configuration

Create a `.env.local` file in the `frontend` folder:

```bash
cd ../frontend
```

Create `.env.local` with the following content:

```env
NEXT_PUBLIC_API_URL=http://127.0.0.1:5000

NEXT_PUBLIC_FIREBASE_API_KEY=your_firebase_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=your_project.firebasestorage.app
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=your_sender_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id
```

> 💡 **Get Firebase config**: Go to Firebase Console → Project Settings → Your apps → Config

---

## 📦 Step 4: Install Dependencies

### 4.1 Install Backend Dependencies

```bash
cd backend
npm install
```

### 4.2 Install Frontend Dependencies

```bash
cd ../frontend
npm install
```

---

## 🚀 Step 5: Run the Application

You need to run **two terminals simultaneously**.

### Terminal 1: Start Backend

```bash
cd backend
npm run dev
```

The backend will start on `http://localhost:5000`

### Terminal 2: Start Frontend

```bash
cd frontend
npm run dev
```

The frontend will start on `http://localhost:3000`

---

## ✅ Step 6: Access the Application

1. Open your browser and go to: **http://localhost:3000**
2. You'll be redirected to the login page
3. Create a new account or sign in with Google
4. Start researching and summarizing!

---

## 🎯 Features

| Feature | Description |
|---------|-------------|
| 🔍 **Deep Web Search** | Search for any topic using integrated search |
| 📄 **Smart Extraction** | Mozilla Readability extracts clean article content |
| 🤖 **AI Summarization** | Google Gemini 2.0 Flash generates comprehensive summaries |
| 💾 **Personal Vault** | Save your summaries for later access |
| 📥 **Export Options** | Download as Markdown (.md) or Text (.txt) |

---

## ⚠️ Troubleshooting

### "Cannot connect to backend server"
- Ensure backend is running on port 5000
- Check `NEXT_PUBLIC_API_URL` in frontend `.env.local`
- Try using `http://127.0.0.1:5000` instead of `localhost`

### "Firebase Auth Error"
- Ensure Email/Password and Google providers are enabled in Firebase Console
- Check that `localhost` is in authorized domains
- Verify all Firebase config values are correct

### "Gemini API Error"
- Verify your Gemini API key is valid
- Check if you've exceeded API quota (free tier limits)
- Get a new key from [Google AI Studio](https://makersuite.google.com/app/apikey)

### "Port 5000 already in use"
- Windows: `netstat -ano | findstr :5000` then `taskkill /PID <PID> /F`
- Mac/Linux: `lsof -i :5000` then `kill -9 <PID>`

---

## 📁 Project Structure

```
MindBrief-MindBrief-01/
├── backend/
│   ├── src/
│   │   ├── routes/
│   │   │   ├── auth.js
│   │   │   ├── search.js
│   │   │   ├── summarize.js
│   │   │   └── vault.js
│   │   └── server.js
│   ├── .env (create this)
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── app/
│   │   │   ├── dashboard/
│   │   │   ├── login/
│   │   │   └── layout.tsx
│   │   ├── components/
│   │   └── lib/
│   ├── .env.local (create this)
│   └── package.json
└── README.md
```

---

## 🛠️ Tech Stack

- **Frontend**: Next.js 15, React 19, TypeScript, Tailwind CSS
- **Backend**: Node.js, Express.js
- **AI**: Google Gemini 2.0 Flash
- **Auth/Storage**: Firebase (Auth + Firestore)
- **Scraping**: Axios, Cheerio, Mozilla Readability

---

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.

---

Built with ❤️ by [Kaif Khan](https://github.com/Kaifkhan1212)
