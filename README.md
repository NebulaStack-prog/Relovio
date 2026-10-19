# Relovio 

<img src="https://github.com/NebulaStack-prog/Relovio/raw/main/Relovio.png" width="200" height="230">

> **Moving without chaos.** A full-stack web application designed to digitize and organize your moving process. Track boxes, manage tasks, generate QR codes for physical labels, and never lose your essentials again.

[![React](https://img.shields.io/badge/React-19-blue?style=flat-square&logo=react)](https://react.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-3178C6?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
[![Vite](https://img.shields.io/badge/Vite-5.0-646CFF?style=flat-square&logo=vite)](https://vitejs.dev/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115-009688?style=flat-square&logo=fastapi)](https://fastapi.tiangolo.com/)
[![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=flat-square&logo=python)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)

## 📖 Overview

Moving is one of the most stressful events in life. Items get packed into dozens of identical boxes, and soon it becomes impossible to remember where the documents, chargers, or daily essentials are. 

**NESTIMS** solves this problem by providing a clean, minimalist interface to digitize the moving process. Users can create moving plans, assign items to specific boxes, and generate unique QR codes to print and stick on physical boxes. The system tracks the status of every box from packing to final unpacking.

## ✨ Key Features

### 1. Authentication & Security
*   **User Registration & Login:** Secure entry point with validation.
*   **JWT Authorization:** State-of-the-art token-based authentication. All API requests are protected.
*   **Password Hashing:** Passwords are never stored in plain text (secured via `bcrypt`).
*   **Multi-tenancy:** Each user has their own private workspace. Users can only see and manage their own moving plans (Sets).

### 2. Task Management (Tasks)
*   **Stage-based Planning:** Tasks are divided into three logical stages: *Before Moving*, *Moving Day*, and *After Moving*.
*   **Deadlines & Progress:** Set due dates and track overall completion percentage.
*   **Visual Feedback:** Newly created tasks highlight briefly to confirm successful creation.

### 3. Inventory & Boxes (Things)
*   **Box Creation:** Create boxes, assign them to specific rooms, and track their current status.
*   **Item Management:** Add items to boxes with specific tags: *Fragile*, *Essential (First Day)*, and *Owner* (e.g., "Mom's items").
*   **Smart Statuses:** The box status automatically updates to "Packed" when all items inside are marked as packed.
*   **Status Flow:** Manual status progression (Ready to Ship -> In Transit -> Delivered -> Unpacked).

### 4. QR Code Generation
*   **Unique Tokens:** Every box gets a unique `qr_token` upon creation.
*   **SVG Generation:** The backend generates crisp, scalable SVG QR codes on the fly.
*   **Print-Ready:** Users can open a modal to view, save, or print the QR code to stick on the physical box.

<img src="https://github.com/NebulaStack-prog/Relovio/raw/main/R13.jpg" width="300" height="404">

### 5. Checklist & Guides
*   **Room-based Checklist:** Automatically syncs packed items from boxes and allows adding custom manual checklist entries.
*   **Moving Guides:** Built-in tips for packing fragile items and a list of essentials to keep on hand.
*   **Notes:** A personal space to write down important contacts or moving day reminders.

## 🛠 Tech Stack & Architecture

### Frontend
*   **React 19 & TypeScript:** For a fast, type-safe, and component-driven UI.
*   **Vite:** Ultra-fast build tool and dev server.
*   **Pure CSS:** Custom, responsive, mobile-first design without heavy UI libraries.
*   **Lucide React:** Lightweight icon set.

### Backend
*   **Python 3.12 & FastAPI:** High-performance API with automatic Swagger documentation (`/docs`).
*   **Pydantic:** Strict data validation and serialization.
*   **Segno:** Local QR code generation (no external APIs needed).
*   **JSON File Storage:** Lightweight data storage (`moving_data.json`) perfect for MVP, with an architecture ready to migrate to PostgreSQL.

### Infrastructure & CI/CD
*   **GitLab CI:** Automated testing pipeline (Pytest for backend, Vitest for frontend) runs on every push.
*   **Nginx:** Reverse proxy and static file server for the frontend.
*   **Systemd:** Process manager ensuring the backend runs 24/7 and restarts on failure.

© NESTIMS & SoCrazYy
