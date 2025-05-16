

```markdown
# Lab8 - JSDoc and OpenAPI Specification

This project is a continuation of the RESTful API development using **Koa.js + TypeScript + PostgreSQL**, with a focus on generating and documenting API specifications using **JSON Schema**, **OpenAPI YAML**, and **ReDoc**.

---

## 📁 Project Structure

```

Lab8/
├── app.ts
├── config.ts
├── routes/
│   ├── users.ts
│   ├── articles.ts
│   ├── private.ts
│   ├── public.ts
│   └── special.ts
├── controllers/
│   ├── auth.ts
│   └── validation.ts
├── models/
│   ├── users.ts
│   └── articles.ts
├── schemas/                # JSON Schema for validation
│   ├── userSchema.ts
│   └── articleSchema.ts
├── docs/
│   └── yaml/
│       ├── openapi.yaml         # OpenAPI YAML spec
│       └── lab8\_redoc\_api.html  # HTML visual API docs using ReDoc

````

---

## 🚀 How to Run

```bash
npm install
npx ts-node app.ts
````

> 📍 Server will run on: `http://localhost:3000`

Make sure PostgreSQL is running and the database connection is correct.

---

## 🔌 API Endpoints Overview

### 👤 Users

| Method | Endpoint     | Description         |
| ------ | ------------ | ------------------- |
| GET    | `/users`     | Get all users       |
| GET    | `/users/:id` | Get user by ID      |
| POST   | `/users`     | Create a new user   |
| PUT    | `/users/:id` | Update a user by ID |
| DELETE | `/users/:id` | Delete a user by ID |

### 📝 Articles

| Method | Endpoint        | Description             |
| ------ | --------------- | ----------------------- |
| GET    | `/articles`     | Get all articles        |
| GET    | `/articles/:id` | Get article by ID       |
| POST   | `/articles`     | Create a new article    |
| PUT    | `/articles/:id` | Update an article by ID |
| DELETE | `/articles/:id` | Delete an article by ID |

---

## 📖 API Documentation (OpenAPI + ReDoc)

OpenAPI spec is located at:
📄 `docs/yaml/openapi.yaml`

To view the documentation:

```bash
Open docs/yaml/lab8_redoc_api.html in your browser
```

Ensure the HTML contains the following:

```html
<script src="https://cdn.redoc.ly/redoc/latest/bundles/redoc.standalone.js"></script>
<script>
  Redoc.init('./openapi.yaml', {}, document.getElementById('redoc-container'));
</script>
```

---

## ✅ Validation & Schema

* Uses `Ajv` for runtime JSON Schema validation
* All request bodies conform to `openapi.yaml` → `components.schemas`
* No external `$ref` JSON files are used — everything is embedded into `openapi.yaml`

---

## 📅 Submission Info

Created for: **Lab 8 – JSDoc and OpenAPI**
Student: EchoCheung
Date: 2025/05/16

