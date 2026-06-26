# ✦ Motivational Quote Maker AI

An AI-powered full-stack web application that generates personalized motivational quotes based on your mood and category.

![Python](https://img.shields.io/badge/Python-3.13-blue)
![Flask](https://img.shields.io/badge/Flask-3.0-green)
![MySQL](https://img.shields.io/badge/MySQL-8.0-orange)
![HuggingFace](https://img.shields.io/badge/AI-HuggingFace-yellow)

## 🚀 Features

- 🤖 AI Quote Generator using HuggingFace API
- 🎨 Quote Image Creator with 6 beautiful templates
- 🔐 User Authentication with secure password hashing
- 🌍 Quote Translation in 8 languages
- 🔊 Voice Reading of quotes
- ⭐ Save Favorite quotes
- 📊 Quote History with search and filter
- ⚙️ Admin Panel for user management
- 🌙 Dark / Light Mode
- 📱 Fully Responsive Design

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| Backend | Python, Flask |
| Database | MySQL |
| AI | HuggingFace API |
| Auth | Flask-Login, Bcrypt |
| Images | Pillow |
| Frontend | HTML, CSS, JavaScript |

## 📁 Project Structure

```
motivational_quote_maker/
├── app.py
├── config.py
├── extensions.py
├── models/
│   ├── user.py
│   ├── quote.py
│   └── favorite.py
├── routes/
│   ├── auth.py
│   ├── dashboard.py
│   ├── api.py
│   └── admin.py
├── utils/
│   ├── ai_generator.py
│   └── image_generator.py
├── templates/
│   ├── base.html
│   ├── index.html
│   ├── login.html
│   ├── register.html
│   ├── dashboard.html
│   ├── history.html
│   ├── favorites.html
│   ├── admin.html
│   └── admin_users.html
└── static/
    ├── css/
    │   └── main.css
    └── js/
        ├── main.js
        └── dashboard.js
```

## ⚡ Quick Start

```bash
# Clone the repo
git clone https://github.com/Harsharn2007/motivational-quote-maker

# Go into folder
cd motivational-quote-maker

# Create virtual environment
python -m venv venv
venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Setup environment
copy .env.example .env
# Fill in your MySQL and HuggingFace credentials in .env file

# Create database in MySQL
mysql -u root -p
CREATE DATABASE motivational_quotes_db;
exit

# Run the app
python app.py
```

Open your browser and go to:
```
http://localhost:5000
```

## ⚙️ Environment Variables

Create a `.env` file and add these:

```
SECRET_KEY=your-secret-key
DEBUG=True
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=your_mysql_password
MYSQL_DB=motivational_quotes_db
USE_AI_PROVIDER=huggingface
HUGGINGFACE_API_KEY=your_huggingface_token
OPENAI_API_KEY=
ADMIN_EMAIL=admin@quotemakerapp.com
```

## 🔌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | /api/generate-quote | Generate AI quotes |
| GET | /api/quotes | Get user quotes |
| POST | /api/favorite | Save favorite |
| DELETE | /api/favorite | Remove favorite |
| DELETE | /api/quotes/<id> | Delete quote |
| POST | /api/generate-image | Create quote card PNG |
| POST | /api/translate-quote | Translate quote |
| POST | /api/rewrite-quote | Rewrite in new style |
| GET | /api/daily-quote | Get daily quote |

## 🗄️ Database Schema

Three core tables:

```sql
-- Users table
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(150) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    is_admin TINYINT(1) DEFAULT 0,
    is_active TINYINT(1) DEFAULT 1,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

-- Quotes table
CREATE TABLE quotes (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    category VARCHAR(50) NOT NULL,
    mood VARCHAR(50) NOT NULL,
    keywords VARCHAR(255),
    quote_text TEXT NOT NULL,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);

-- Favorites table
CREATE TABLE favorites (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    quote_id INT NOT NULL,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

## 👤 Default Admin Login

```
Email: admin@quotemakerapp.com
Password: admin123
```

> Change this password immediately after first login!

## 🎨 Quote Image Templates

6 beautiful templates available:
- Gradient Dark
- Sunrise
- Ocean
- Forest
- Midnight
- Rose Gold

## 🌍 Supported Translation Languages

- Spanish
- French
- German
- Hindi
- Arabic
- Chinese
- Japanese
- Portuguese

## 📸 Screenshots

> Add your screenshots here

## 🙏 Acknowledgements

- HuggingFace for free AI API
- Flask community
- Pillow library for image generation
- deep-translator for translations

## 📝 License

MIT License — free to use, modify and share!

## 👩‍💻 Author

**Harsharn Kaur**
