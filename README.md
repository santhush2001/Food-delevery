
# Full-Stack food delevery Web App: React + Django


A modern full-stack web application built with **React** on the frontend and **Django** on the backend. This monorepo structure makes it easy to manage, develop, and deploy both services together.

---

## 📁 Project Structure

```
my-webapp/
├── frontend/         # React app (Vite or CRA)
├── backend/          # Django app (REST API)
├── .gitignore
├── LICENSE
└── README.md
```

---

## 🚀 Getting Started

### 🖼️ Frontend (React)

> Located in the `/frontend` directory

#### 🔧 Prerequisites

- [Node.js](https://nodejs.org/) (v16+ recommended)
- npm or yarn

#### 🛠️ Installation & Development

```bash
cd frontend
npm install           # or yarn
npm run dev           # or npm start
```

#### 🌐 Default URL:

```
http://localhost:5173/
```

> You can update the port or API endpoint in `.env` and `vite.config.js`.

---

### 🧩 Backend (Django)

> Located in the `/backend` directory

#### 🔧 Prerequisites

- Python 3.9+
- pip
- Virtualenv (recommended)

#### 🛠️ Installation & Development

```bash
cd backend
python -m venv venv
source venv/bin/activate       # Windows: venv\Scripts\activate
pip install -r requirements.txt

# Setup environment variables
cp .env.example .env           # Then edit .env as needed

# Run migrations
python manage.py migrate

# Start the development server
python manage.py runserver
```

#### 🌐 Default URL:

```
http://127.0.0.1:8000/
```

---

## 🔁 Connecting Frontend to Backend

Make sure the frontend can communicate with the Django backend.

1. In `/frontend/.env`, add:

```env
VITE_API_URL=http://127.0.0.1:8000/api/
```

2. Install CORS middleware in Django:

```bash
pip install django-cors-headers
```

3. Update `backend/settings.py`:

```python
INSTALLED_APPS += ['corsheaders']
MIDDLEWARE.insert(0, 'corsheaders.middleware.CorsMiddleware')
CORS_ALLOWED_ORIGINS = [
    "http://localhost:5173",
]
```

---

## 🧪 Tech Stack

| Layer      | Technology                    |
|------------|-------------------------------|
| Frontend   | React, Vite (or Create React App), Axios |
| Backend    | Django, Django REST Framework |
| Styling    | Tailwind CSS or plain CSS     |
| Database   | SQLite (default), PostgreSQL (optional) |
| Auth       | Django built-in or JWT        |

---

## ⚙️ Environment Variables

### Frontend (`frontend/.env`)
```env
VITE_API_URL=http://127.0.0.1:8000/api/
```

### Backend (`backend/.env`)
```env
DEBUG=True
SECRET_KEY=your-secret-key
DATABASE_URL=sqlite:///db.sqlite3
```

---

## 📦 Deployment Tips

- **Frontend** can be deployed on [Vercel](https://vercel.com/), [Netlify](https://netlify.com/), or [Firebase Hosting](https://firebase.google.com/).
- **Backend** can be deployed on [Render](https://render.com/), [Railway](https://railway.app/), or Docker/Heroku setups.
- Make sure to set up environment variables and allowed hosts accordingly.


