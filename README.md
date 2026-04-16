# Banking API Node.js/Express

A secure, observable, and highly robust Backend API tailored for banking operations. Built from scratch with Express.js and fully optimized for Serverless deployments like Vercel.

## Architecture & Features

- **Runtime**: Node.js & Express.js
- **Database**: MongoDB (via Mongoose)
- **Authentication**: JWT-based session management using `jsonwebtoken` and `argon2` for high-security password hashing.
- **Observability**: Production-grade central logging utilizing `winston`. Automatically manages log persistence locally and scales securely via console streams in serverless architectures.
- **Security**: Granular request rate limiting powered by `rate-limiter-flexible`.

## Prerequisites

Before you begin, ensure you have met the following requirements:
* You have installed [Node.js](https://nodejs.org/en/)
* You have installed [pnpm](https://pnpm.io/)
* You have a locally running instance of MongoDB or a cloud connection string from [MongoDB Atlas](https://www.mongodb.com/atlas/database)

## Local Development Setup

1. **Clone the repository:**
   bash
   git clone https://github.com/Pritesh23-P/24BDA70006-8b-Pritesh-Kumar-Pandey.git
   cd 24BDA70006-8b-Pritesh-Kumar-Pandey/backend

2. **Install all dependencies:**
   bash
   pnpm install

3. **Configure Environment Variables:**
   Create a `.env` file in the root of the directory and specify the required values:
   env
   MONGO_URI=mongodb://localhost:27017/banking
   PORT=3000
   LOG_LEVEL=info
   JWT_SECRET=your_super_secret_key
   JWT_REFRESH_SECRET=your_refresh_secret
   JWT_EXPIRES_IN=5m

4. **Start the development server:**
   bash
   pnpm dev

The API will now be running on `http://localhost:3000`. Success logs will automatically appear in `logs/combined.log` and application errors mapped inside `logs/error.log`.

## Available API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/auth/register` | Registers a new user with `email` and `password`. |
| `POST` | `/api/auth/login` | Authenticates an existing user and returns a signed JWT Token. |

*(Use tools like Postman or Thunder Client to interact with these HTTP routes).*

## Vercel Deployment

This project includes a customized `vercel.json` and a serverless-ready `index.js`, making it **100% Vercel compatible**!

1. Upload the repository to GitHub.
2. Link the repository to your Vercel Dashboard.
3. During setup, navigate to Settings > Environment Variables, and add all variables exactly as they exist in your `.env` file. 
4. **Important**: Since Vercel is in the cloud, change your `MONGO_URI` to a MongoDB Atlas connection string instead of local storage.
5. Deploy!
