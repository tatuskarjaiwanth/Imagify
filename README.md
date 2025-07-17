# Imagify 🚀

Imagify is a full-stack MERN (MongoDB, Express, React, Node.js) application with a Vite-powered frontend and Vercel deployments. It enables users to generate AI-powered images from text prompts, manage credits, and view testimonials.

---

## 🔹 Live Demo

- **Link to website**: [https://imagify-sand-nu.vercel.app/](#)

---

## 🛠 Technologies Used

| Layer      | Tech Stack                                                |
| ---------- | --------------------------------------------------------- |
| Frontend   | React + Vite, Tailwind CSS, Framer Motion, React-Toastify |
| Backend    | Node.js, Express, Axios, FormData, JWT Authentication     |
| Database   | MongoDB (Atlas/Local)                                     |
| AI Image   | ClipDrop Text-to-Image API                                |
| Deployment | Vercel (Frontend & Backend)                               |

---

## 🚀 Features

- ✏️ **Text-to-Image Generation** using AI (powered by ClipDrop)
- 🔐 **User Authentication** with JWT
- 💰 **Credit Management**: users consume a credit for each generated image
- ⭐ **Testimonials** section showcasing user feedback
- 🎨 **Responsive UI**, animated entrance using Motion

---

## 🔧 Prerequisites

- Node.js & npm installed
- A MongoDB Atlas URI (or local MongoDB connection string)
- A valid `CLIPDROP_API` key from ClipDrop
- Vercel account (for deployment)

---

## 🧭 Getting Started (Local)

1. **Clone the repo**

   ```bash
   git clone https://github.com/tatuskarjaiwanth/Imagify.git
   cd Imagify
   ```

2. **Setup .env files**

   - **server/.env**
     ```env
     MONGODB_URI=your_mongodb_connection_string
     JWT_SECRET=your_jwt_secret
     CLIPDROP_API=your_clipdrop_api_key
     ```
   - **client/.env**

     ```env
     VITE_BACKEND_URL = 'http://localhost:4000'
     ```

3. **Install dependencies**

   - Backend:
     ```bash
     cd server
     npm install
     ```
   - Frontend:
     ```bash
     cd ../client
     npm install
     ```

4. **Run in development mode**

   - Start the server:
     ```bash
     cd server
     npm run server
     ```
   - Start the client:
     ```bash
     cd ../client
     npm run dev
     ```

   > Frontend typically runs on `http://localhost:5173` and backend on `http://localhost:4000`.

5. **Use API endpoints**

   - `POST /api/user/register` – Register
   - `POST /api/user/login` – Login
   - `POST /api/image/generate-image` – Generate image
     (requires `token` header and `prompt` body)
   - `GET /api/user/credits` – credits

---

## 🔐 Authentication Flow

1. User registers → JWT token received
2. JWT token stored in frontend (e.g., localStorage)
3. Each authenticated image request includes `token` in headers
4. Server middleware validates token and attaches `userId` to `req.body`
5. Image credit tracking and balance deduction per call

---

## 🏗 Deployment Structure

- Both `client/` and `server/` are deployed as **separate projects** on **Vercel**
- Environment variables configured in Vercel dashboards (prod/staging)
- Requests from React frontend are proxied to the backend Vercel domain

---

## 🧪 Testing & Topups

- Handle 402 / 422 API errors (e.g., no credits or moderation filter) with user-friendly feedback
- Admin routes for manual credit top-up functionality

---

## 📈 Future Enhancements

- 🧠 Add OpenAI moderation or safety filters
- 💳 Add paid credit top-up (Stripe / Razorpay integration)
- ✉️ Build email notifications (SendGrid / Nodemailer)
- 📦 Add Docker & Kubernetes setup for scalable deployment
- 🧪 Implement unit & integration tests (Jest / Supertest)

---

## ✅ Author

**Jaiwanth Tatuskar**  
📧 jaiwanthtatuskar@gmail.com
🔗 [GitHub](https://github.com/tatuskarjaiwanth)

---

Thank you for checking out **Imagify**! Let me know if you'd like any tweaks or additions.
