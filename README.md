# 📰 Outline Kerala – Online News Platform (Backend)

Outline Kerala is a modern digital **news publishing platform** built using **Python, Django, and GraphQL**.  
It provides a scalable backend for managing news, categories, user roles, media uploads, and delivering content to mobile & web applications.

---

## 🚀 Key Features

### 🔐 Authentication & User Roles
- JWT Authentication
- Roles:
  - **Admin**
  - **Editor**
  - **Reporter**
  - **User / Reader**
- Editors approve/reject articles

### 📝 News Management
- Create, edit, delete articles
- Rich-text descriptions
- SEO-friendly slugs
- Category & tag-based organization
- Breaking news support
- Schedule publish times

### 📡 GraphQL API
- GraphQL endpoint: `/graphql`
- Queries:
  - Latest news
  - News by category
  - Trending topics
  - Author-wise articles
- Mutations:
  - Create news
  - Update news
  - Manage categories, users
- Supports pagination and filtering

### 📸 Media Handling
- Image upload for news
- Media stored inside `/media/` directory

### 🗄 Database
- Uses **SQLite (dev)** / PostgreSQL (production)
- Models include:
  - User
  - News
  - Categories
  - Tags
  - Media files

---

## 🏗 Tech Stack

| Component | Technology |
|----------|------------|
| Backend Framework | Django 5 |
| API Layer | GraphQL (Strawberry/Graphene) |
| Language | Python 3.12 |
| Database | SQLite / PostgreSQL |
| Auth | JWT |
| Deployment | Railway / Render / VPS |
| File Storage | Local or Cloud |

---

## 📂 Project Structure

```
## 📂 Project Structure
outlinekerala/
│── admin_app/              # Admin panel APIs, authentication, user roles, GraphQL mutations & queries
│── user_app/               # Public news APIs, reporters, categories, GraphQL schema for readers
│── outlinekerala/          # Main Django project: settings, URLs, GraphQL router, ASGI/WSGI config
│── media/                  # Uploaded news images, reporter uploads, category icons
│── staticfiles/            # Collected static assets (CSS/JS/images)
│── manage.py               # Django management entry point
│── requirements.txt        # Python dependencies
│── README.md               # Project documentation
│── db.sqlite3              # Dev database

```


---

## ⚙️ Installation Guide

### 1️⃣ Clone the project
```sh
git clone https://github.com/corusinfo-tech/outlinekerala-app.git
```
```
cd outlinekerala
```

### 2️⃣ Create virtual environment

``` 
python -m venv venv
venv\Scripts\activate
```

### 3️⃣ Install dependencies
```
pip install -r requirements.txt
```

### 4️⃣ Apply migrations
```
python manage.py migrate
```

### 5️⃣ Run development server

```
python manage.py runserver
```

## 🔧 GraphQL Endpoint

### After running the server:
```
http://127.0.0.1:8000/graphql

```
Use the GraphQL Playground to run queries and mutations.

### 🧪 Sample GraphQL Queries
Get Latest News
```
query {
  latestNews {
    id
    title
    slug
    createdAt
    category {
      name
    }
  }
}
```

Get News by Category
```
query {
  newsByCategory(categorySlug: "kerala") {
    title
    description
  }
}
```

Create News (Mutation)
```
mutation {
  createNews(
    title: "New Update",
    categoryId: 1,
    description: "Full description here",
    authorId: 2
  ) {
    news {
      id
      title
    }
  }
}
```

## 📜 License

### MIT License


---

If you want:

✅ **README for frontend (React / React Native)**  
or  
✅ **Developer API documentation (Postman style)**  
or  
✅ **Tester documentation (test cases + flows)**  

Just tell me — I’ll generate it.


