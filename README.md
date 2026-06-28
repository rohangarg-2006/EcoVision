# ♻️ Solid Waste Management Application

A full-stack web application for reporting and managing municipal solid waste requests.

## 🚀 Live Deployment

- 🌐 Deployed App: https://solid-waste-management-application-d0al.onrender.com

## 🛠️ Tech Stack

### ⚙️ Backend

- Node.js + Express.js for REST APIs
- MongoDB + Mongoose for database modeling
- JWT (`jsonwebtoken`) for authentication
- `bcryptjs` for password hashing
- `express-validator` for request validation
- `cors` and `dotenv` for middleware/config support

### 🎨 Frontend

- React.js (Vite)
- Tailwind CSS (`postcss`, `autoprefixer`)
- `react-router-dom` for routing and protected views
- `axios` for API communication

## 🤖 Special Mention: ML Waste Classification Model

This project also includes a dedicated machine learning module under `backend/ML_Model` for waste image classification (for example, Clean vs Dirty categories).

- Model training and experimentation notebook: `Model_Final.ipynb`
- Trained PyTorch model weights: `model.pth`
- Prediction service/scripts: `prediction_server.py`, `prediction.py`
- Dataset folders for training/testing are included under `Datasets/`

This ML component adds practical intelligence to the platform by enabling automated waste-type prediction workflows.

## ✅ Assignment Deliverables

- Backend project with MVC-style folder structure
- User registration and login
- Role-based access control (`citizen` and `manager`)
- CRUD APIs for waste requests
- ML-based waste image classification module included
- API versioning under `/api/v1`
- Validation for incoming request bodies
- Working React frontend with protected dashboard routes
- Postman API collection included
- Scalability and deployment notes

## 📁 Project Structure

```text
backend/
  config/
  controllers/
  middleware/
  models/
  routes/
  ML_Model/
frontend/
  src/
  public/
Waste-Management-API-Collection.json
```

## 🧪 Local Setup

### 1. 🔐 Configure Environment Variables

Create a `.env` file inside `backend/`:

```env
PORT=5000
MONGO_URI=your_mongodb_cluster_uri_here
JWT_SECRET=your_super_secret_jwt_string
```

### 2. 🧩 Run Backend

```bash
cd backend
npm install
npm run dev
```

Backend runs at `http://localhost:5000`.

### 3. 💻 Run Frontend

```bash
cd frontend
npm install
npm run dev
```

Frontend runs at `http://localhost:5173`.

## 📚 API Documentation

Import `Waste-Management-API-Collection.json` into Postman to test all endpoints, request bodies, and Bearer-token based authorization.

## 📈 Scalability Notes

- Split Auth and Waste Requests into independent services as usage grows
- Use asynchronous messaging (RabbitMQ/Kafka) for event-driven workflows (for example, pickup notifications)
- Containerize services with Docker and orchestrate with Kubernetes for scaling
- Add Redis caching for heavy read endpoints
- Apply database indexes to common query fields (for example, `status` and `citizenId`)
