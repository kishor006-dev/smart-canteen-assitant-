# smart-canteen-assitant
AI-based Smart Canteen Assistant Project
# 🍴 Smart Canteen AI Assistant
**Subtitle:** AI-powered Smart Canteen Assistant for students and staff with real-time chat, menu management, and order tracking.  



## Overview
**Smart Canteen AI** is a web-based application that allows students to interact with a virtual canteen assistant powered by AI (Groq + LLaMA 3.1 70B). Students can view the menu, place orders, receive recommendations, and manage order history. Staff can manage the menu, set daily specials, and track pending orders.

**Features:**  
- **Student Panel:** Login/Signup, chat with AI assistant, place/cancel orders, view order history.  
- **Staff Panel:** Login/Signup, manage menu items, set daily specials, mark orders as ready.  
- AI-powered recommendations & conversational interface.  
- Real-time notifications via WebSockets.  

---

## Project Structure
Smart-Canteen-AI/
│
├─ backend/
│ ├─ main.py # FastAPI backend
│ └─ requirements.txt # Python dependencies
│
├─ student/
│ ├─ student.html # Student frontend
│ ├─ student.css
│ └─ student.js
│
├─ staff/
│ ├─ staff.html # Staff frontend
│ ├─ staff.css
│ └─ staff.js
│
├─ assets/
│ ├─ canteen.jpg # Student background image
│ └─ staffside.jpg # Staff background image
│
└─ README.md


## Prerequisites
- Python 3.10+  
- Node.js (optional, for running frontend via server)  
- MongoDB running locally on default port `27017`  
- Groq API Key for AI functionality (set as environment variable `GROQ_API_KEY`)  

---

## Database setup
Here is a clean, step-by-step **Local MongoDB Installation Guide** formatted for your README — covering **Windows, Mac, and Linux**:

---

## 🗄️ Local MongoDB Installation Guide

If you prefer running MongoDB locally instead of using MongoDB Atlas, follow the steps based on your operating system.

---

### 🪟 **Windows Installation**

#### 1️⃣ Download MongoDB Community Server

Search: **"MongoDB Community Server Download"**
Download from the official website and run the installer.

#### 2️⃣ During installation, select:

✔ **Complete Installation**
✔ **Install MongoDB as a Service**
✔ **Include MongoDB Compass (optional)**

#### 3️⃣ Start MongoDB Service (if not running automatically):

Open **Command Prompt as Administrator**:

net start MongoDB


#### 4️⃣ Verify Installation

mongosh


If you see:


test>


MongoDB is running successfully 🎉


### 🍎 **Mac Installation (Intel / M1 / M2)**

> Requires **Homebrew**. If not installed, run:

/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"


#### 1️⃣ Install MongoDB

brew tap mongodb/brew
brew install mongodb-community


#### 2️⃣ Start MongoDB Service

brew services start mongodb-community


#### 3️⃣ Verify

mongosh


If the Mongo shell starts, setup is complete 🎉


### 🐧 **Linux (Ubuntu / Debian)**

#### 1️⃣ Update System

sudo apt update


#### 2️⃣ Install MongoDB

sudo apt install -y mongodb


#### 3️⃣ Start Service


sudo systemctl start mongodb


#### 4️⃣ Enable Auto-Start


sudo systemctl enable mongodb


#### 5️⃣ Check Status

sudo systemctl status mongodb

#### 6️⃣ Verify

mongosh

If you see a database shell prompt (`>`) — you're ready 🎉


### 🔗 Default Local Database Connection

After installation, the default MongoDB connection string for your project is:

mongodb://localhost:27017

### ⚠️ Common Issue: "mongosh not found"

Install mongosh manually:

npm install -g mongosh

 ## Backend setup

1.Create and activate a virtual environment:

   python -m venv venv
# Linux/Mac
   source venv/bin/activate
# Windows
   venv\Scripts\activate
   
2.move to path

   cd Smart-Canteen-Assistant 

3. Install dependencies:

   pip install -r backend/requirements.txt

4.set a API key

   see environment variables below

5.Start the backend server:

   uvicorn backend.main:app --reload

## Frontend Setup

Open `student/student.html` and `staff/staff.html` in your browser.

Ensure backend server is running at `http://localhost:8000` for API calls.

**Student Panel:**

* Login with seeded user: `student1 / 123`
* Interact with AI assistant, view menu, place orders

**Staff Panel:**

* Login with seeded user: `staff1 / admin`
* Manage menu, set daily specials, view pending orders

## Environment Variables

GROQ_API_KEY – API key for Groq AI.

**Linux/Mac:**

export GROQ_API_KEY="your_api_key_here"

**Windows PowerShell:**

setx GROQ_API_KEY "your_api_key_here"

 **command prompt**
 set GROQ_API_KEY="your_api_key_here"

## Notes

* Student chat uses WebSockets for real-time notifications.
* Daily specials and combo suggestions are AI-powered.
* Orders are stored in MongoDB and persist across sessions.


## Future Improvements

* Integrate payment gateway for online orders.
* Add analytics dashboard for staff.
* Improve AI recommendations with personalized history.





