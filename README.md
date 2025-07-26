#  E-Commerce AI Chatbot

A full-stack Conversational AI Chatbot for an E-commerce Clothing Platform built with **React**, **FastAPI**, and **PostgreSQL**. This chatbot can:

- Answer queries like:
  - “What are the top 5 most sold products?”
  - “Show me the status of order ID 12345.”
  - “How many Classic T-Shirts are left in stock?”
- Handle conversation history.
- Integrate with an LLM (Groq) for follow-ups and clarifying questions.
- Store data in a structured relational DB.

---

##  Project Structure

```
chat-bot/
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   ├── routes.py
│   │   ├── services.py
│   │   └── utils.py
│   ├── requirements.txt
│   └── Dockerfile
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── App.js
│   │   ├── index.js
│   │   └── api.js
│   ├── package.json
│   └── Dockerfile
│
├── docker-compose.yml
├── README.md
└── data/ (contains CSV files)
```

---

## Running the Project

### Option 1: Run Locally

> Make sure Python, Node.js, and PostgreSQL are installed locally.

**Backend (FastAPI)**

```bash
cd backend
pip install -r requirements.txt
uvicorn app.main:app --reload
```

**Frontend (React)**

```bash
cd frontend
npm install
npm start
```

**Database**

- Use PostgreSQL
- Create DB: `chatbot_db`
- Add credentials in `docker-compose.yml` or `.env`

---

### Option 2: Using Docker (Recommended)

> No need to install Python, Node.js, or PostgreSQL locally.

```bash
docker-compose up --build
```

**Access:**

- Frontend → http://localhost:3000
- Backend API → http://localhost:8000/docs

---

##  API Endpoints (FastAPI)

| Method | Endpoint                     | Description                                |
|--------|------------------------------|--------------------------------------------|
| GET    | `/top-products`              | Top 5 most sold products                   |
| GET    | `/order-status/{order_id}`   | Status of a specific order                 |
| GET    | `/product-stock/{name}`      | Inventory left for a given product         |
| POST   | `/query`                     | Accepts user query & returns AI response   |

---

## Tech Stack

| Layer      | Tech                 |
|------------|----------------------|
| Frontend   | React.js, TailwindCSS|
| Backend    | FastAPI, Python      |
| Database   | PostgreSQL           |
| AI/LLM     | Groq API (optional)  |
| DevOps     | Docker, Docker Compose|

---

##  Sample Query (Frontend)

```json
POST /query
{
  "query": "What are the top 5 most sold products?"
}
```

---
