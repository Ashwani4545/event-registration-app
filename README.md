# Event Registration & Ticket Management Platform

A full-stack event management platform that allows organizers to create events, manage registrations, generate QR-based tickets, and validate entries through a mobile scanning system.

The platform is designed to support **secure ticket generation, payment integration, automated email delivery, and QR-based validation at entry points**.

---

# Table of Contents

1. Project Overview
2. Key Features
3. System Architecture
4. Tech Stack
5. Repository Structure
6. Installation Guide
7. Environment Setup
8. Running the Application
9. Docker Setup
10. Git Workflow for Team Development
11. API Overview
12. Database Schema Overview
13. QR Ticket Validation Flow
14. Deployment
15. Future Improvements
16. Contributing
17. License

---

# 1. Project Overview

The Event Registration Platform provides a **complete solution for managing events digitally**, including attendee registration, ticket generation, QR scanning, and analytics.

This system is intended for:

* Colleges
* Conferences
* Workshops
* Tech events
* Festivals
* Ticketed meetups

The platform eliminates manual ticket management and enables **real-time validation using QR codes**.

---

# 2. Key Features

## Event Management

* Create and manage events
* Add event description, date, and venue
* Manage ticket capacity

## Registration System

* Custom registration forms
* Single or multiple attendee registration
* Automated data collection

## Payment Integration

* Secure payment processing
* Payment verification
* Transaction tracking

## Ticket Generation

* Unique ticket IDs
* QR code generation
* PDF ticket generation
* Email delivery of tickets

## QR Ticket Validation

* Real-time scanning
* Entry verification
* Duplicate ticket prevention

## Admin Dashboard

* Manage events
* Track registrations
* Monitor QR scan logs
* Export analytics

---

# 3. System Architecture

The system follows a **modern client-server architecture**.

Mobile App / Web App
↓
API Server
↓
Database + Storage

Components include:

* Mobile Application
* Backend API
* Database
* Payment Gateway
* Email Service
* QR Validation System

---

# 4. Tech Stack

## Frontend

* React Native (Mobile App)
* Next.js (Admin Dashboard)
* TailwindCSS

## Backend

* Node.js
* TypeScript
* NestJS Framework

## Database

* PostgreSQL
* Prisma ORM

## Infrastructure

* Docker
* AWS / Cloud Hosting

## Authentication

* JWT Authentication

## Payment Gateway

* Razorpay

## Notifications

* Firebase Cloud Messaging

## Storage

* AWS S3 / Cloud Storage

---

# 5. Repository Structure

```
event-registration-platform

backend/
│
├── src
│   ├── auth
│   ├── users
│   ├── events
│   ├── registrations
│   ├── tickets
│   ├── payments
│   └── qr-validation
│
├── prisma
├── docker
└── config

mobile-app/
│
├── screens
├── components
├── navigation
└── services

admin-dashboard/
│
├── pages
├── components
└── analytics

docs/
README.md
```

---

# 6. Installation Guide

Clone the repository

```
git clone https://github.com/yourusername/event-registration-platform.git
```

Move into the project directory

```
cd event-registration-platform
```

Install dependencies

```
npm install
```

---

# 7. Environment Setup

Create a `.env` file inside the backend folder.

Example:

```
DATABASE_URL=postgresql://user:password@localhost:5432/eventdb

JWT_SECRET=your_secret_key

RAZORPAY_KEY=your_key

EMAIL_SERVICE_API_KEY=your_email_service_key

AWS_ACCESS_KEY=your_aws_access_key
AWS_SECRET_KEY=your_aws_secret
```

---

# 8. Running the Application

Start backend server

```
npm run start:dev
```

Start mobile app

```
npm run mobile
```

Start admin dashboard

```
npm run dashboard
```

---

# 9. Docker Setup

Build containers

```
docker-compose build
```

Start services

```
docker-compose up
```

Containers include:

* Backend API
* PostgreSQL database
* Redis cache
* Nginx proxy

---

# 10. Git Workflow for Team Development

We follow a **feature branch workflow**.

Main branches:

```
main
develop
```

Developers create feature branches:

```
feature-authentication
feature-event-creation
feature-payment
feature-ticket-generation
feature-qr-scanner
```

Development process:

1. Create feature branch
2. Implement feature
3. Commit changes
4. Push branch
5. Create Pull Request
6. Code review
7. Merge into develop

---

# 11. API Overview

Example endpoints:

### Authentication

POST /auth/register
POST /auth/login

### Events

GET /events
POST /events
PUT /events/:id
DELETE /events/:id

### Registrations

POST /register
GET /registrations/:eventId

### Tickets

GET /ticket/:ticketId
POST /ticket/generate

### QR Validation

POST /scan-ticket

---

# 12. Database Schema Overview

Main database tables include:

Users
Events
Registrations
Tickets
Payments
ScanLogs

Relationships:

User → Registers → Event
Event → Generates → Tickets
Ticket → Validated by → QR Scanner

---

# 13. QR Ticket Validation Flow

Ticket generation:

User registers
↓
Payment verification
↓
Unique ticket ID created
↓
QR code generated
↓
Ticket emailed to user

Event entry validation:

Scanner scans QR
↓
Ticket ID sent to API
↓
Database verification
↓
Response returned

Valid
Invalid
Already Used

---

# 14. Deployment

Recommended infrastructure:

Frontend
Vercel

Backend
AWS EC2

Database
AWS RDS / Supabase

Storage
AWS S3

---

# 15. Future Improvements

* AI-based fraud detection
* Multi-event analytics dashboard
* Organizer mobile app
* Dynamic ticket pricing
* Blockchain ticket verification

---

# 16. Contributing

Steps to contribute:

1. Fork the repository
2. Create feature branch
3. Commit changes
4. Push branch
5. Create Pull Request

Please ensure:

* Code follows project standards
* Tests pass
* Documentation is updated

---

# 17. License

This project is licensed under the MIT License.

---

# Authors

Project developed by the Event Platform Development Team.
