# Tech Stack Overview

This document outlines the complete technology stack used in the **Blogging Application**, covering frontend, backend, database, tools, and hosting setup.

---

## Frontend

**Framework:** React (Vite)  
**Styling:** Tailwind CSS  
**Routing:** React Router  
**State Management :** Context API  
**Form Handling:** React Hook Form  
**HTTP Client:** Fetch API   
**Build & Deployment:** Vite build → Deployed on **Vercel**

**Key Features**
- Fast development and build via Vite
- Responsive UI with Tailwind CSS
- Reusable component-based architecture
- Easy deployment pipeline with GitHub → Vercel integration

---

## Backend

**Runtime Environment:** Node.js  
**Framework:** Express.js  
**Authentication:** JSON Web Tokens (JWT) + bcrypt for password hashing   
**Environment Management:** dotenv  
**Error Handling:** Centralized middleware  
**Testing Framework:** Jest
**Deployment:** Hosted on **AWS EC2 instance**

**Key Features**
- RESTful API design
- Secure authentication and authorization using JWT
- Input validation and error handling middleware
- Environment-based configurations

---

## Database

**Database:** MongoDB  
**Cloud Service:** MongoDB Atlas  
**ODM (Object Data Modeling):** Mongoose  
**Indexes & Optimization:** Managed via Atlas tools  

**Key Features**
- Cloud-hosted, secure, and scalable database
- Schema-driven modeling with Mongoose
- Seamless integration with Node.js backend

---

## DevOps & Tools

**Version Control:** Git  
**Repository Management:** GitHub  
**Branching Strategy:** Feature-based branches with pull requests  
**API Testing:** Postman   
**Documentation:** MkDocs 

**Key Features**
- Efficient version control with Git
- Collaboration via GitHub
- Continuous integration and deployment setup
- Automated documentation generation

---


## Summary

This stack ensures:
- Fast, responsive, and scalable web application
- Clean separation of frontend and backend
- Secure authentication and database integration
- Cloud-native hosting and deployment
- Easy maintainability and developer collaboration

---

**Tech Stack Summary**

| Layer | Technology | Purpose |
|--------|-------------|----------|
| Frontend | React (Vite) + CSS | UI development |
| Backend | Node.js + Express | API layer |
| Database | MongoDB (Atlas) | Data storage |
| Version Control | Git + GitHub | Code management |
| Hosting | Vercel / AWS EC2 | Deployment |
| Cloud Database | MongoDB Atlas | Managed DB hosting |

---


