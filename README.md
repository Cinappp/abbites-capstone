# 🍽️ ABbites - Nutrition Tracker for College Campuses

## 📌 Project Introduction

ABbites is a full-stack mobile application designed to help college students make healthier food decisions by providing restaurant menus with detailed nutritional information. The app addresses the common challenge of not knowing what’s in your food—especially on campus—by offering meal tracking, customization, and a calendar view to log daily nutrition.

---

## ✅ Functional and Non-Functional Requirements

### Functional Requirements:
- JWT-secured Login and Registration (Spring Boot backend + React Native frontend)
- View restaurant menus from MongoDB (Subway currently implemented)
- Customize sub orders (size → bread → meat → cheese, extras, veggies, sauces)
- Nutrition calculator that adds up daily meals
- Save meals to the calendar by selecting a specific date
- View daily meal logs under the user’s account (via calendar view)
- RESTful API integration using `axios` in the frontend and Spring Boot controllers in the backend
- Global state management with React Context (`AuthContext`, `CalculatorContext`)
- Clean mobile navigation using Expo Router with tabbed layout

### Non-Functional Requirements:
- Passwords are securely hashed using BCrypt in the backend before storage
- Fully responsive mobile interface designed using React Native + Expo
- Secure token storage using `expo-secure-store` for JWT persistence
- Backend is deployed on AWS EC2; MongoDB is hosted on MongoDB Atlas
- Logging and monitoring handled through Spring AOP (`Tracer` and `AopConfiguration`)
- Organized backend architecture using controller, service, model, and repository layers

---

## 🧠 Technology Stack & Best Practices

- **Frontend:** React Native (with Expo), Expo Router, Context API, Secure Store
- **Backend:** Spring Boot 3 (Java 17), JWT Authentication, BCrypt, SLF4J Logging
- **Database:** MongoDB (hosted on MongoDB Atlas)
- **DevOps & Deployment:**
  - Hosted on AWS EC2 for backend
  - GitHub for source control and versioning
  - API testing performed using Postman
  - Modular file structure and clean code architecture

---

## 🚀 New Technologies Learned

- **React Native with Expo Router** for seamless navigation in mobile apps
- **React Context API** for globally shared state (user auth & nutrition calculator)
- **Spring Boot AOP** for custom tracing and centralized request logging
- **MongoDB schema design** with embedded sub-documents for nutrient storage
- **SecureStore from Expo** for persistent JWT sessions on mobile

---

## 🛠️ Technical Approach & Architecture

### Frontend Flow:
- Tabs: Home | Search | Calculator | Account
- Screens: 
  - Subway Menu → Item → Customize → Nutrition Summary
  - Calculator screen → Add Meals → Add to Calendar
  - Account screen → Calendar View → Show meals per date

### Backend Structure:
- Modularized folders by domain: `controllers/`, `models/`, `services/`, `repository/`
- Each restaurant (e.g. Subway) has its own substructure (e.g. `models/subway/`, `controllers/subway/`)
- Nutrition calculator receives user selections and returns full nutrient summary

### Design Diagrams:
- Class diagrams for models like `UserModel`, `SubwayOrderModel`, and `NutrientModel`
- Sequence diagrams to explain:
  - Login and JWT flow
  - Calendar meal saving and lookup flow
  - Subway customization request and response logic

---

## ⚠️ Risks and Challenges

### Challenges Faced:
- MongoDB connection issues due to IP whitelisting
- JWT user state not updating across screens in Expo
- `NullPointerException` in nutrition calculator when data was incomplete

### Solutions:
- Resolved MongoDB IP issues by properly configuring MongoDB Atlas access
- Migrated local state to global `AuthContext` and `CalculatorContext`
- Added data validation and fallback logic in backend services for null-safe nutrition summaries

### Risk Management:
- Used GitHub version control to manage features in branches
- Tested all API endpoints using Postman before frontend integration
- Implemented logging using SLF4J + Spring AOP to catch edge-case failures

---

## 🧩 Outstanding Issues

- Only Subway is fully implemented; additional restaurants (Taco Bell, Chick-fil-a) are planned
- Calendar view supports one-day-at-a-time view; weekly/monthly summaries are future enhancements
- No visual charts in the calculator yet (e.g. pie chart of nutrients)
- Search screen currently only filters by item name; additional filters coming soon

---

## 💡 Project Summary

ABbites is a feature-rich, production-ready mobile app demonstrating full-stack development with a focus on nutrition tracking. From JWT-secured login and cloud-hosted backend services to nutrient calculation and calendar logging, this app showcases secure design, modular architecture, and mobile UX. It is suitable for showcasing at interviews, capstone presentations, and as a launch-ready MVP.

---

## 📚 Resources Used
- MongoDB Atlas Docs – https://www.mongodb.com/docs/atlas/
- Spring Boot AOP Guide – https://www.baeldung.com/spring-aop-annotation
- Expo Secure Store – https://docs.expo.dev/versions/latest/sdk/securestore/
