# 📚 AI‑Assisted Library Backend System  
### *Implicit & Explicit Access Control using FastAPI in Google Colab*

This project implements an **AI‑powered library backend assistant** that simulates real‑world information‑access boundaries through two modes: **Implicit** (public catalog data only) and **Explicit** (full metadata with user consent). The entire backend runs inside **Google Colab**, eliminating local environment issues and tunneling requirements.

---

## 🚀 Features

- **Dual Access Modes**
  - **Implicit Mode:** Returns only public catalog information  
  - **Explicit Mode:** Provides full private metadata when explicit consent is given  
- **FastAPI Backend** running seamlessly in Google Colab  
- **Reasoning Logic Engine** for mode detection and controlled responses  
- **REST Endpoints** for `/ask` and `/prompts`  
- **Async Execution** using `uvicorn` + `nest_asyncio`  
- **Tested via HTTP requests** directly inside Colab  

---

## 🏗️ System Architecture

**Flow:**  
`Client Request → Mode Detection → Reasoning Logic → JSON Response`

Core components include:

- FastAPI server  
- Uvicorn ASGI runtime  
- Pydantic models for request/response validation  
- Background thread execution  
- Structured system prompts controlling AI behavior  

---

## 📦 Technologies Used

| Component | Purpose |
|----------|---------|
| **FastAPI** | Backend API framework |
| **Uvicorn** | ASGI server |
| **nest_asyncio** | Enables async server inside Colab |
| **Pydantic** | Input/output validation |
| **Requests** | API testing |
| **Threading** | Background server execution |

---

## 💡 Why Google Colab?

- No local hosting or tunneling required  
- Avoids ngrok/localtunnel token issues  
- No OS‑level dependency conflicts  
- Supports async FastAPI execution  
- Ideal for demos, academic work, and lightweight backend prototypes  

---

## ⚠️ Why Flask Was Not Used

Flask blocks cell execution in Colab, preventing additional code from running.  
FastAPI + Uvicorn supports **non‑blocking async execution**, which was essential for this project.

---

## 🧪 Demo Outputs

### ✔️ Implicit Mode  
Returns public catalog information only.

Example:  
> “Yes, we have the following book(s) in our catalog… I cannot show detailed inventory in this mode.”

### ✔️ Explicit Mode  
Returns full metadata only with explicit consent.

Example:  
> “I could not find that book in the catalog.”

Both modes return structured JSON with metadata and flags indicating whether private data was accessed.

---

## 🔌 API Endpoints

### **POST /ask**  
Handles user queries in implicit or explicit mode.

### **GET /prompts**  
Returns the system prompts that define AI behavior.

---

## 🧪 Testing

All endpoints were tested using Python `requests` inside Colab:

- `POST /ask` (implicit mode)  
- `POST /ask` (explicit mode)  
- `GET /prompts`  

All returned **200 OK**, confirming full backend functionality.

---

## 📘 Lessons Learned

- Differences between public and private metadata handling  
- How structured prompts control AI behavior  
- Running async servers inside Google Colab  
- Challenges with tunneling tools (ngrok/localtunnel)  
- Building a fully functional backend without local setup  

---

## ✅ Conclusion

This project demonstrates a fully functional **AI‑assisted library backend** with controlled access modes, built entirely in Google Colab using FastAPI. It is tested, reliable, and ready for academic or professional presentation.

