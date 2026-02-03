# College Exam Seat Planner

A web application to efficiently allocate classrooms for college exams using a greedy strategy that minimizes the number of rooms while prioritizing lower-floor classrooms.

---

## 🚀 Objective

The goal of this project is to:
- Allocate exam seats using the **minimum number of classrooms**
- **Prefer lower-floor classrooms first**
- Handle cases where **available capacity is insufficient**
- Provide a clean and usable UI with clear output

This project is built as part of a technical assignment to evaluate logical reasoning, optimization, and frontend–backend integration.

---

## 🧩 Features

- Add classroom details (name, floor, capacity)
- View all available classrooms
- Allocate exam seats based on total students
- Greedy allocation logic (optimized & deterministic)
- Error handling for invalid and insufficient inputs
- Data persistence using Supabase

---

## 🛠 Tech Stack

- **Frontend:** React + TypeScript + Vite
- **Styling:** Tailwind CSS
- **Backend / Database:** Supabase (PostgreSQL + RLS)
- **Deployment:** Vercel / Netlify
- **Version Control:** Git & GitHub

---

## 🗃 Data Model (Classroom)

| Field     | Type    | Description                      |
|----------|---------|----------------------------------|
| id       | UUID    | Unique classroom identifier      |
| name     | string  | Classroom name (e.g., NLT, A101) |
| floor    | number  | Floor number                     |
| capacity | number  | Seating capacity                 |
| created_at | timestamp | Auto-generated                 |

---

## 🧠 Allocation Logic (Core Idea)

1. Fetch all classrooms from the database
2. Sort classrooms by **floor number (ascending)**
3. Iteratively allocate classrooms until:
   - Total student requirement is met, or
   - Classrooms are exhausted
4. If total capacity < required students → show error

> Allocation is computed on the **frontend** because it is deterministic and does not require persistence.

---

## ❗ Error Handling

- Prevents adding classrooms with invalid inputs
- Displays error if no classrooms exist
- Displays message if seats are insufficient
- Handles Supabase insert/select errors gracefully

---

## 🌐 Live Demo

👉 **Live URL:** _(add your deployed link here)_

---

## 📦 Installation & Setup (Local)

```bash
git clone https://github.com/ankitsingh2022/SYMB-ASSIGNMENT.git
cd SYMB-ASSIGNMENT
npm install
npm run dev
