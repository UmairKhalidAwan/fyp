# fyp
# 📝 Smart Notes — OCR Powered Note Taking Web Application

A web application that combines **Optical Character Recognition (OCR)** with a **Note Management System**. Users can upload images containing handwritten or printed text (including Urdu) and the system automatically extracts the text and saves it as a searchable note — eliminating the need for manual typing.

> **Final Year Project (FYP)** — Built using a custom trained OCR model (Shaheen OCR) integrated into a Flask web application with user authentication and note management.

---

## 💡 Core Idea

```
User uploads image
        ↓
Shaheen OCR processes it
        ↓
Text extracted automatically
        ↓
Saved as a note in the app
        ↓
User can view, manage & delete notes
```

---

## ✨ Features

- 🔐 User Registration & Login (Flask-Login)
- 🖼️ Upload images — handwritten, printed or Urdu text
- 🤖 Automatic text extraction using custom trained OCR model
- 📋 Extracted text saved directly as a note
- 🗑️ Delete notes
- 👤 Each user sees only their own notes
- 📱 Responsive web interface

---

## 🤖 Shaheen OCR Model

The OCR engine used in this project is **Shaheen OCR** — a custom trained model built specifically for this FYP. It supports:

| Capability | Status |
|---|---|
| Printed English text | ✅ Supported |
| Handwritten text | ✅ Supported |
| Urdu text recognition | ✅ Supported |

The model was trained on a **custom dataset** designed and collected by the team, making it capable of recognizing Urdu script — something standard OCR engines like Tesseract struggle with.

OCR preprocessing and model training pipeline is available in `SOCR_Preprocessing.ipynb`.

---

## 🏗️ Project Structure

```
fyp/
├── __init__.py          # Flask app factory & DB initialization
├── main.py              # App entry point
├── auth.py              # Login, signup, logout routes
├── views.py             # Notes routes (add, delete, home)
├── models.py            # Database models (User, Note)
│
├── model/               # Shaheen OCR model files
│   ├── fypsocr          # Trained OCR model
│   └── SOCR_Preprocessing.ipynb  # Model training & preprocessing
│
├── preprocessing.ipynb  # Data preprocessing notebook
│
├── templates/
│   ├── base.html        # Base layout
│   ├── home.html        # Notes dashboard
│   ├── login.html       # Login page
│   └── sign_up.html     # Registration page
│
├── static/
│   ├── login.css        # Styling
│   └── index.js         # Frontend interactions
│
├── database.db          # SQLite database
└── requirements.txt     # Dependencies
```

---

## 🗄️ Database Models

### User
| Field | Type | Description |
|---|---|---|
| id | Integer | Primary key |
| email | String | Unique user email |
| password | String | Hashed password |
| first_name | String | User's first name |
| notes | Relation | All notes by this user |

### Note
| Field | Type | Description |
|---|---|---|
| id | Integer | Primary key |
| data | String | Note text content |
| date | DateTime | Creation timestamp |
| user_id | Integer | Foreign key to User |

---

## 🚀 Getting Started

### 1. Install Dependencies
```bash
pip install flask flask-login flask-sqlalchemy
```

### 2. Run the App
```bash
python main.py
```

Open browser at `http://127.0.0.1:5000`

### 3. Register an Account
- Go to Sign Up page
- Create your account
- Start uploading images and saving notes!

---

## 👥 Team

| Member | Role | GitHub |
|---|---|---|
| Umair Khalid Awan | Notes App + Integration | [@UmairKhalidAwan](https://github.com/UmairKhalidAwan) |
| Abdullah | Shaheen OCR Model | [@ab069](https://github.com/ab069) |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Python, Flask |
| Authentication | Flask-Login |
| Database | SQLite, Flask-SQLAlchemy |
| OCR Engine | Shaheen OCR (Custom Trained) |
| Frontend | HTML, CSS, JavaScript |
| ML/Preprocessing | Jupyter Notebook, Python |

---

## 📄 License

This project is for academic and research purposes — Final Year Project submission.
