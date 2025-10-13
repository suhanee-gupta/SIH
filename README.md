# Certificate Verification System

A full-stack web application for secure certificate upload, OCR-based data extraction, and verification against government/official databases. Designed for scalability, security, and extensibility, with future plans for blockchain integration.

---

## 🚀 Features

- **User Authentication:** Secure signup/login with JWT.
- **Certificate Upload:** Users can upload certificates (PDF, image).
- **OCR Extraction:** Automatic extraction of key data from certificates using OCR.
- **Verification:** Matches extracted data against a verified database.
- **Multi-Database Architecture:**  
  - User data stored in `SIH-signup-login` database  
  - Certificate/keypoints data stored in `keypointsDb` database
- **Admin Portal:** Admins can add pre-verified certificates.
- **File Handling:** Supports large files (up to 20MB).

##  Tech Stack

**Frontend:**
- React (with TypeScript)
- JavaScript
- HTML
- CSS

**Backend:**
- Node.js
- Express.js
- MongoDB Atlas (cloud database)
- OCR service (custom/third-party)
- CORS

### Prerequisites

- Node.js (v18+ recommended)
- npm or bun
- MongoDB Atlas account

### Setup

1. **Clone the repository:**
   ```sh
   git clone <repo-url>
   cd SIH
   ```

2. **Backend Setup:**
   - Go to `backend/`
   - Create a `.env` file (see `.env.example` or below)
   - Install dependencies:
     ```sh
     npm install
     ```
   - Start the backend:
     ```sh
     npm start
     ```

3. **Frontend Setup:**
   - Go to `frontend/`
   - Create a `.env` file:
     ```
     VITE_API_BASE=http://localhost:5000
     ```
   - Install dependencies:
     ```sh
     npm install
     ```
   - Start the frontend:
     ```sh
     npm run dev
     ```

---

## 📝 Environment Variables

**Backend `.env` example:**
```
USER_MONGODB_URI=mongodb+srv://<user>:<pass>@cluster.mongodb.net/SIH-signup-login?retryWrites=true&w=majority
KEYPOINTS_MONGODB_URI=mongodb+srv://<user>:<pass>@cluster.mongodb.net/keypointsDb?retryWrites=true&w=majority
PORT=5000
JWT_SECRET=your_jwt_secret
CORS_ORIGINS=http://localhost:3000,http://localhost:8080
OCR_LANGUAGE=eng
MAX_FILE_SIZE=20971520
ALLOWED_FILE_TYPES=image/jpeg,image/png,application/pdf
NODE_ENV=development
```

## 🛣️ Future Development

- **Blockchain Integration:**  
  Store certificate hashes on blockchain for tamper-proof verification.
- **Role-based Access:**  
  More granular admin/user roles.
- **Advanced Analytics:**  
  Dashboard for certificate verification statistics.

