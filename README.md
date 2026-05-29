# 📊 SMV — Social Media Visualizer

<div align="center">

![Android](https://img.shields.io/badge/Platform-Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-1.9-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-Backend-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![Material Design](https://img.shields.io/badge/Material%20Design%203-UI-757575?style=for-the-badge&logo=material-design&logoColor=white)
![License](https://img.shields.io/badge/Type-Client%20Project-FF4444?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Delivered-brightgreen?style=for-the-badge)

**An AI-driven social media analytics Android app that helps users understand their social appeal.**  
Upload photos, receive engagement predictions, collect community feedback, and make data-driven content decisions.

> ⚠️ **Confidential Client Project** — Source code is not publicly available.  
> This repository serves as a professional portfolio showcase.

</div>

---

## 📖 About

**SMV (Social Media Visualizer)** is a native Android app built for a client who wanted a platform where users could upload photos and instantly understand their social media potential — before posting publicly.

I was brought in as the **sole developer** to build the entire Android application from scratch — from architecture decisions and Firebase setup to UI implementation and deployment.

The app uses **Firebase** as a complete backend (Auth, Firestore, Storage, Cloud Functions) and follows **MVVM architecture** with clean Kotlin code throughout.

---

## 🎯 Project Context

| | |
|---|---|
| **Project Type** | Freelance / Client Delivery |
| **Platform** | Android (Native) |
| **Language** | Kotlin |
| **My Role** | Solo Android Developer — Full App |
| **Backend** | Firebase (Auth + Firestore + Storage + Cloud Functions) |
| **Status** | Delivered & in production |

---

## 🚀 Core Features

| Feature | Description |
|---|---|
| 📸 **Photo Upload & Analysis** | Users upload images directly from gallery or camera for structured feedback |
| 🤖 **AI-Powered Insights** | Advanced algorithms analyze uploaded photos for engagement potential |
| 👥 **Community Feedback** | Get votes, ratings, and comments from real users on uploaded content |
| 📈 **Engagement Prediction** | Predict social media performance using ML-based analytics |
| 💡 **Personalized Recommendations** | AI-driven suggestions to improve content before publishing |
| 📊 **Real-Time Analytics** | Detailed insights on photo performance and audience engagement |
| 🔐 **Secure Authentication** | OAuth 2.0 — Google, Facebook, and Email/Password login via Firebase Auth |
| ☁️ **Cloud Storage** | Firebase Storage for efficient, scalable image hosting |

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|---|---|---|
| Language | Kotlin | Core Android development |
| Architecture | MVVM | Clean separation of UI, logic, and data |
| State Management | LiveData + ViewModel | Reactive UI updates |
| Authentication | Firebase Auth | Google, Facebook, Email OAuth 2.0 |
| Database | Firebase Firestore | Real-time NoSQL cloud database |
| File Storage | Firebase Storage | Image upload and retrieval |
| Serverless Logic | Firebase Cloud Functions | Backend processing without a server |
| Networking | Retrofit + OkHttp | REST API calls |
| Image Loading | Glide | Smooth image loading and caching |
| UI | Material Design 3 | Modern, consistent Android UI |
| Async | Kotlin Coroutines | Non-blocking background operations |

---

## 🏗️ Architecture — MVVM

```
┌─────────────────────────────────────────────┐
│                   VIEW                       │
│       Activities / Fragments / XML           │
│   Observes LiveData · Sends user events      │
└──────────────────┬──────────────────────────┘
                   │
┌──────────────────▼──────────────────────────┐
│               VIEW MODEL                     │
│   LiveData · Business Logic · State          │
│   Calls Repository · Exposes UI state        │
└──────────────────┬──────────────────────────┘
                   │
┌──────────────────▼──────────────────────────┐
│               REPOSITORY                     │
│   Single source of truth for data           │
│   Abstracts Firebase from ViewModel         │
└──────────────────┬──────────────────────────┘
                   │
┌──────────────────▼──────────────────────────┐
│            FIREBASE BACKEND                  │
│  Auth · Firestore · Storage · Functions      │
└─────────────────────────────────────────────┘
```

---

## 🔐 Authentication Flow

```
User opens app
      │
      ▼
Firebase Auth check ──► Already logged in? ──► Home Screen
      │
      ▼ (Not logged in)
Login Screen
      │
      ├──► Google Sign-In (OAuth 2.0)
      ├──► Facebook Login (OAuth 2.0)
      └──► Email / Password
                   │
                   ▼
          Firebase Auth SDK
                   │
                   ▼
          Firestore — create/fetch user profile
                   │
                   ▼
              Home Screen
```

---

## 📸 Screenshots

<div align="center">

<img src="https://github.com/user-attachments/assets/4c42234a-36fa-4e92-befa-15e54d05ff04" width="24%">
<img src="https://github.com/user-attachments/assets/61804e47-be8d-46f6-bfbb-21dc3cca6ae9" width="24%">
<img src="https://github.com/user-attachments/assets/3e8a89bf-be6b-4a4b-9adc-10d40389c79a" width="24%">
<img src="https://github.com/user-attachments/assets/b8f4ef8a-9c07-4f5e-b19d-89d665427b40" width="24%">

<img src="https://github.com/user-attachments/assets/dd145a4e-4d4f-4807-9b0a-173164f50703" width="24%">
<img src="https://github.com/user-attachments/assets/8d17f621-3d83-46ac-9d36-12a7f6438b3c" width="24%">
<img src="https://github.com/user-attachments/assets/600de028-74a7-4951-a78e-295b1dae5bcd" width="24%">

</div>

---

## 📁 Project Structure

```
app/
├── data/
│   ├── model/              # Kotlin data classes (User, Post, Analytics)
│   ├── repository/         # Firebase abstraction layer
│   └── remote/
│       ├── FirebaseAuthSource.kt
│       ├── FirestoreSource.kt
│       └── StorageSource.kt
│
├── domain/
│   └── usecase/            # Business logic use cases
│
├── ui/
│   ├── auth/               # Login, Register screens
│   ├── home/               # Feed, photo upload
│   ├── analytics/          # Insights & engagement dashboard
│   ├── profile/            # User profile & stats
│   └── components/         # Reusable UI components
│
├── utils/                  # Extensions, constants, helpers
└── MainActivity.kt
```

---

## 📄 License

This project is proprietary software. All rights reserved by the client.  
Source code is not available for redistribution or reuse.

---

## 👨‍💻 Developer

**Ahsan Ali Shah** — Android & Flutter Mobile Developer

I build production-grade mobile apps with clean architecture, Firebase integration, and polished UIs — delivered on time as a solo developer.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Ahsan%20Ali%20Shah-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/ahsanalishah4105)

[![Fiverr](https://img.shields.io/badge/Fiverr-Work%20With%20Me-1DBF73?style=for-the-badge&logo=fiverr&logoColor=white)](https://www.fiverr.com/ahsanshahkazm)

[![GitHub](https://img.shields.io/badge/GitHub-ahsanshah4105-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ahsanshah4105)

---

<div align="center">

*Built with Kotlin · MVVM · Firebase · Material Design 3*

**Interested in working together? Feel free to reach out!**

</div>
