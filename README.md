# 🚀 AritraEats – Food Platform Backend System

## 🧠 Overview

AritraEats is a full-stack food platform backend system that simulates real-world applications like Swiggy/Zomato.

It uses:
- ⚡ FastAPI → Backend APIs
- 🖥 Django → Frontend templates
- 🗄 MySQL → Database
- 🎨 Tailwind CSS → UI styling

---

## 🧩 Architecture

Frontend (Django Templates)
↓
FastAPI Backend APIs
↓
MySQL Database

---

## 📁 Project Structure

food_platform/
│
├── fastapi_service/
│   └── app.py
│
├── templates/
│   ├── signup/
│   ├── payload/
│   └── dashboard/
│
├── sql/
│   ├── schema.sql
│   ├── seed.sql
│
├── config/
│   └── settings.py
│
├── setup_database.py
├── .env
└── manage.py

---

## ⚙️ Setup Instructions

### 1. Install Dependencies
pip install -r requirements.txt

---

### 2. Configure Environment (.env)

DB_HOST=127.0.0.1  
DB_PORT=3306  
DB_USER=root  
DB_PASSWORD=root  
DB_NAME=food_platform_db  

---

### 3. Initialize Database

python setup_database.py

---

### 4. Run Servers

Django (Frontend):
python manage.py runserver  

Open:
http://127.0.0.1:8000/

FastAPI (Backend):
uvicorn fastapi_service.app:app --port 9000  

Swagger Docs:
http://127.0.0.1:9000/docs

---

## 🔐 Core Features

### ✅ Signup API
POST /api/auth/signup/

---

### ✅ Payload API (Complex JSON)
POST /api/payload/ingest/

Example:
{
  "restaurant": {
    "owner_id": 1,
    "name": "Cafe Demo",
    "description": "Test",
    "address": "Gurgaon",
    "latitude": 28.45,
    "longitude": 77.02
  },
  "menu": [
    {
      "category_name": "Breakfast",
      "items": [
        {"name": "Tea", "price": 20},
        {"name": "Toast", "price": 50}
      ]
    }
  ]
}

---

### ✅ Order APIs
POST /api/orders/place/  
GET /api/orders/history/  

---

### ✅ Menu API
GET /api/restaurants/{id}/menu/

---

## 🗄 Database Tables

users  
restaurants  
menu_items  
orders  
order_items  

---

## 🔄 Data Flow

UI → FastAPI → MySQL

---

## 🧠 Key Concept

Nested JSON → Relational Mapping

menu → categories → items  
→ stored in menu_items table

---

## 🖥 UI Pages

/signup/  
/payload/  
/dashboard/  
/login/  

---

## 🧪 Testing

Run:
SELECT * FROM restaurants;  
SELECT * FROM menu_items;  
SELECT * FROM orders;  

---

## ⚠️ Common Issues

### CORS Error
Fix:
allow_origins=["http://127.0.0.1:8000"]

---

### SQLAlchemy Error
Wrap queries:
from sqlalchemy import text

---

### 422 Error
Fix payload schema mismatch

---

### Button Not Working
Bind event:
document.getElementById("send-btn").addEventListener("click", sendPayload);

---

### Duplicate FastAPI app
Only keep ONE:
app = FastAPI()

---

## ⚡ Performance

- Indexed queries
- Foreign key constraints
- JSON mapping optimized

---

## 🔐 Security

- Password hashing
- Input validation (Pydantic)
- Token-ready APIs

---

## 🚀 Future Improvements

- JWT Authentication
- Analytics Dashboard
- Multi-restaurant support
- CRUD APIs
- Cloud Deployment

---

## 🎯 Summary

AritraEats is a production-style backend system demonstrating:

- API design
- Database modeling
- Complex JSON ingestion
- Full-stack integration

---


