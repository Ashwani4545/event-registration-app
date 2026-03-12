
# Event Registration & Ticket Management App

A cross-platform mobile application that enables organizers to create events, manage registrations, generate QR-based tickets, and validate entries through QR scanning.

The system simplifies the entire event lifecycle — from event creation to entry validation — and supports Android and iOS using Flutter with a Spring Boot backend and PostgreSQL database.

---

## Table of Contents

- Project Overview
- Features
- System Architecture
- Tech Stack
- Project Structure
- Installation & Setup
- Database Design
- API Overview
- Development Workflow
- Deployment
- Security
- Future Improvements

---

## Project Overview

The Event Registration & Ticket Management App helps event organizers manage:

- Event creation
- Participant registration
- Payment collection
- QR ticket generation
- Entry validation
- Event promotion

It replaces manual event registration systems with a digital automated solution.

---

## Features

### Event Creation
Organizers can create events with:
- Event title
- Description
- Venue
- Date and time
- Ticket price
- Participant limit

### Registration System
Participants can register via:
- Direct registration
- Registration links

Supports:
- Single participant form
- Multiple participant form

### Payment Integration
- Secure payment gateway
- Automatic confirmation after payment success

### Ticket Generation
After successful registration and payment:
- Unique ticket ID
- QR code ticket
- Confirmation message/email

### QR Ticket Validation
At the event:
1. Staff scans QR code
2. Backend verifies ticket
3. Entry status updated

### Event Marketing
Events can be shared through:
- WhatsApp
- Instagram
- Direct registration links

### Organizer Dashboard
Organizers can manage:
- Events
- Participants
- Payments
- Ticket validation
- Event analytics

---

## System Architecture

Flutter Mobile App
↓
Spring Boot REST API
↓
PostgreSQL Database
↓
External Services (Payments, Notifications)

---

## Tech Stack

### Mobile
- Flutter
- Dart

### Backend
- Java
- Spring Boot
- Spring Security
- JWT Authentication

### Database
- PostgreSQL
- Hibernate / JPA

### Tools
- GitHub
- Docker
- Swagger
- Postman
- Firebase
- Razorpay / Stripe

---

## Project Structure

event-registration-app

backend/
controllers/
services/
repositories/
models/

mobile_app/
screens/
widgets/
services/

database/
schema.sql

docs/
architecture.md

README.md

---

## Installation

### Clone Repository

git clone https://github.com/your-repository/event-registration-app.git

cd event-registration-app

### Backend Setup

cd backend

mvn spring-boot:run

Server runs at:
http://localhost:8080

### Database Setup

Create database:

CREATE DATABASE event_app;

Update application.properties:

spring.datasource.url=jdbc:postgresql://localhost:5432/event_app

spring.datasource.username=postgres

spring.datasource.password=yourpassword

### Mobile App Setup

cd mobile_app

flutter pub get

flutter run

---

## Database Design

### Users
id
name
email
phone
role

### Events
event_id
event_name
description
event_date
venue
organizer_id

### Registrations
registration_id
user_id
event_id
payment_status
registration_date

### Tickets
ticket_id
registration_id
qr_code
entry_status

---

## API Overview

### Event APIs
- Create Event
- Update Event
- Delete Event
- Get Event

### Registration APIs
- Register Participant
- Generate Registration Link

### Ticket APIs
- Generate Ticket
- Fetch Ticket

### Validation APIs
- Scan QR
- Validate Ticket

---

## Development Workflow

Branches:

main

develop

feature/*

bugfix/*

Steps:
1. Create feature branch
2. Implement feature
3. Push code
4. Create pull request
5. Review and merge

---

## Deployment

Backend:
- AWS
- DigitalOcean
- Google Cloud

Database:
- PostgreSQL Managed Server

Mobile:
- Google Play Store
- Apple App Store

---

## Security

- JWT authentication
- Secure payment verification
- API rate limiting
- Encrypted QR codes

---

## Future Improvements

- Offline QR validation
- Event analytics dashboard
- Multi-event ticket wallet
- AI-based event recommendation
- Multi-language support

---

## License

MIT License
