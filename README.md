# Blankify.io - AI-Powered Background Remover

---

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Environment Variables](#environment-variables)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [API Documentation](#api-documentation)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## 🎯 About

**Blankify.io** is a modern, full-stack SaaS application that leverages AI technology to remove backgrounds from images with precision and speed. Built with React and Node.js, it offers a seamless user experience with secure authentication, payment processing, and a robust API backend.

Whether you're an e-commerce seller, content creator, or designer, Blankify.io simplifies the background removal process, saving you time and effort.

---

## ✨ Features

- 🤖 **AI-Powered Background Removal** - Remove backgrounds from images instantly
- 🔐 **Secure Authentication** - Clerk-based user authentication and management
- 💳 **Payment Integration** - Razorpay payment gateway for premium features
- 🚀 **Fast & Responsive** - Built with Vite for lightning-fast performance
- 🎨 **Modern UI** - Clean, intuitive interface with Tailwind CSS
- 📱 **Fully Responsive** - Works seamlessly on desktop, tablet, and mobile
- 🔒 **Rate Limiting** - API protection with express-rate-limit
- 📦 **File Upload** - Efficient image upload with Multer
- 🗄️ **Database Management** - MongoDB with Mongoose ODM
- 🔔 **Toast Notifications** - Real-time user feedback with React Toastify

---

## 🛠️ Tech Stack

### Frontend
- **Framework:** React 18.3.1
- **Build Tool:** Vite 6.0.5
- **Routing:** React Router DOM v7
- **Styling:** Tailwind CSS
- **Authentication:** Clerk React
- **HTTP Client:** Axios
- **Icons:** Lucide React
- **Notifications:** React Toastify

### Backend
- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB
- **ODM:** Mongoose
- **Authentication:** JWT & Clerk Webhooks (Svix)
- **Payment:** Razorpay
- **File Upload:** Multer
- **Security:** CORS, Express Rate Limit
- **Development:** Nodemon

### Deployment
- **Platform:** Vercel
- **CI/CD:** Automated deployments

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- Node.js (v16 or higher)
- npm or yarn
- MongoDB (local or Atlas)
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/MasirJafri1/Blankify.io-BG-Remover.git
   cd Blankify.io-BG-Remover
   ```

2. **Install Client Dependencies**
   ```bash
   cd Client
   npm install
   ```

3. **Install Server Dependencies**
   ```bash
   cd ../Server
   npm install
   ```

### Environment Variables

#### Client (.env)
Create a `.env` file in the `Client` directory:

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_API_URL=http://localhost:5000
```

#### Server (.env)
Create a `.env` file in the `Server` directory:

```env
# Database
MONGODB_URI=your_mongodb_connection_string

# Clerk
CLERK_WEBHOOK_SECRET=your_clerk_webhook_secret

# JWT
JWT_SECRET=your_jwt_secret

# Razorpay
RAZORPAY_KEY_ID=your_razorpay_key_id
RAZORPAY_KEY_SECRET=your_razorpay_key_secret

# Server
PORT=5000
NODE_ENV=development

# CORS
ALLOWED_ORIGINS=http://localhost:5173

# Background Removal API (external service)
BG_REMOVAL_API_KEY=your_api_key
```

---

## 💻 Usage

### Development Mode

1. **Start the Server**
   ```bash
   cd Server
   npm run dev
   ```
   Server will run on `http://localhost:5000`

2. **Start the Client**
   ```bash
   cd Client
   npm run dev
   ```
   Client will run on `http://localhost:5173`

### Production Build

1. **Build the Client**
   ```bash
   cd Client
   npm run build
   ```

2. **Start the Server**
   ```bash
   cd Server
   npm start
   ```

---

## 📁 Project Structure

```
Blankify.io-BG-Remover/
├── Client/                    # Frontend React Application
│   ├── public/               # Static assets
│   ├── src/                  # Source files
│   │   ├── components/       # React components
│   │   ├── pages/           # Page components
│   │   ├── utils/           # Utility functions
│   │   ├── App.jsx          # Main App component
│   │   └── main.jsx         # Entry point
│   ├── index.html           # HTML template
│   ├── package.json         # Client dependencies
│   ├── tailwind.config.js   # Tailwind configuration
│   ├── vite.config.js       # Vite configuration
│   └── vercel.json          # Vercel deployment config
│
├── Server/                   # Backend Node.js Application
│   ├── Configs/             # Configuration files
│   ├── Controllers/         # Business logic
│   ├── MiddleWares/         # Custom middleware
│   ├── Models/              # Mongoose models
│   ├── Routes/              # API routes
│   ├── Server.js            # Entry point
│   ├── package.json         # Server dependencies
│   └── vercel.json          # Vercel deployment config
│
├── .gitignore               # Git ignore file
└── README.md                # Project documentation
```

---

## 📡 API Documentation

### Base URL
```
Development: http://localhost:5000/api
Production: https://your-domain.com/api
```

### Endpoints

#### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `POST /api/webhook/clerk` - Clerk webhook handler

#### Background Removal
- `POST /api/remove-bg` - Upload and remove background
- `GET /api/images/:id` - Get processed image
- `GET /api/images/user/:userId` - Get user's images

#### Payment
- `POST /api/payment/create-order` - Create Razorpay order
- `POST /api/payment/verify` - Verify payment

#### User
- `GET /api/user/profile` - Get user profile
- `PATCH /api/user/profile` - Update user profile
- `GET /api/user/credits` - Get user credits

---

## 🌐 Deployment

### Vercel Deployment

Both client and server are configured for Vercel deployment.

#### Deploy Client
```bash
cd Client
vercel --prod
```

#### Deploy Server
```bash
cd Server
vercel --prod
```

### Environment Variables on Vercel
Add all required environment variables in your Vercel project settings.

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 👨‍💻 Contact

**Masir Jafri**

- GitHub: [@MasirJafri1](https://github.com/MasirJafri1)
- Email: masirjafri1@gmail.com
- Website: [https://www.masirjafri.in](https://www.masirjafri.in)
- LinkedIn: [Masir Jafri](https://www.linkedin.com/in/masir-jafri)

---

<div align="center">
  Made with ❤️ by Masir Jafri
  
  ⭐ Star this repository if you find it helpful!
</div>
