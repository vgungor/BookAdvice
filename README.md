# 📚 BARA – Book Advice / Recommendation App

> A lightweight PHP-based web application for collaboratively suggesting and managing book recommendations in a shared digital library.

![PHP](https://img.shields.io/badge/PHP-7.4%2B-blue)
![Bootstrap](https://img.shields.io/badge/Bootstrap-4-purple)
![License](https://img.shields.io/badge/License-Educational-lightgrey)

---

## ✨ Features

- 🔐 User authentication (email & password)
- 🗂 View books in **Card** or **Table** layout
- 📱 Fully responsive (desktop, tablet, mobile)
- 🔍 Real-time search by title or author
- ➕ Book suggestion with duplicate prevention
- 🛡 Admin-only book deletion

---

## 👥 User Roles

### Standard User

- Login
- View & search books
- Suggest new books

### Admin User

- All standard permissions
- Delete any book entry

---

## 🛠 Tech Stack

- **Backend:** PHP 7.4+
- **Frontend:** HTML5, CSS3, Bootstrap 4, FontAwesome 5
- **Storage:** Flat-file JSON (`books.json`)

---

## 🔐 Security

- `password_verify()` for secure authentication
- CSRF protection on all POST requests
- Session fixation prevention
- Input sanitization
- File locking (`LOCK_EX`) during write operations
- Admin-only protected routes

---

## 📄 Data Model (`books.json`)

```json
{
  "id": "Integer",
  "title": "String",
  "author": "String",
  "advicer": "User Email",
  "genre": "Optional",
  "year": "Optional"
}
```

---

## 🚀 Getting Started

```bash
# Requirements
PHP >= 7.4
```

1. Deploy the project on a PHP-compatible web server
2. Ensure **write permission** for `books.json`
3. Open the application in your browser
4. Log in with a registered account

> ℹ️ No database setup is required.

---

## 🧑‍💼 Admin Actions

- Delete books using the 🗑️ trash icon
- Deletion requires confirmation

---

## 📌 Notes

- Search bar appears automatically when the library exceeds **10 books**
- Duplicate entries (same title + author) are blocked

---

## 📜 License

This project is intended for **educational or internal use**. Add a license file if you plan to distribute or open-source the project.

---

## ⭐ Contributing

Pull requests and suggestions are welcome if this project is extended or adapted.
