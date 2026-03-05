# 🚀 Newman UI Manager - Complete System

Comprehensive system documentation: Architecture, Functionality, and Technology Stack

---

# 📋 Table of Contents

- System Overview
- Technology Stack
- System Architecture
- Core Features
- Workflows
- Integrations
- Security & Secrets Management
- Deployment & Operations

---

# 🎯 System Overview

## What is Newman UI Manager?

Newman UI Manager is a **Full-Stack platform** that allows teams to execute and manage automated API tests using **Postman collections** through a modern web interface.

The system integrates multiple cloud services:

- AWS
- Jira / Zephyr
- Google Drive

It also supports **multiple projects with independent configurations**.

---

## Purpose

### Test Automation
Execute Postman collections without manual intervention.

### Multi-Project Management
Support multiple projects with independent configurations.

### Continuous Integration
Integrate with Jira/Zephyr for test cycle management.

### Advanced Reporting
Generate customized HTML reports with interactive dashboards.

### Security
Centralized secrets management using **AWS Secrets Manager**.

---

# 🏗️ Technology Stack

## Frontend

### Language & Framework

- **TypeScript 5.2.2** – Type safety and improved development experience
- **React 18.2.0** – UI library using functional components and Hooks
- **React DOM 18.2.0** – Browser rendering

### UI Framework

- **Material-UI (MUI) 5.14.20**
  - `@mui/material` – Core UI components
  - `@mui/icons-material` – Icon library
  - `@emotion/react`
  - `@emotion/styled`

### Development Tools

- **Vite 5.0.0** – Ultra-fast build tool with instant HMR
- `@vitejs/plugin-react 4.1.1`

### Communication

- **Axios 1.6.0** – HTTP client for REST APIs
- **Socket.io-client 4.7.4** – WebSocket communication for real-time updates

### Routing

- **React Router DOM 6.20.1**

### Testing

- **Vitest 1.0.0**
- **@testing-library/react**
- **@testing-library/jest-dom**
- **@testing-library/user-event**
- **jsdom**

### Linting

- **ESLint 8.53.0**
- **@typescript-eslint/eslint-plugin**
- **eslint-plugin-react-hooks**

---

# Backend

## Language & Runtime

- **TypeScript 5.2.2**
- **Node.js**

### Web Framework

- **Express 4.18.2**

### Middleware

- **CORS 2.8.5**
- **Multer 1.4.5**

### Communication

- **Socket.io 4.7.4**

### API Test Execution

- **Newman 6.2.1** – Official Postman CLI
- **newman-reporter-custom** – Custom HTML reporter

### Database

- **SQLite3 5.1.6** – Embedded database

### Utilities

- **dotenv**
- **uuid**

### Development Tools

- **tsx 4.6.0** – TypeScript runner with hot reload

### Testing

- **Vitest**
- **Supertest**
- **fast-check**

---

# Root Level Integrations

## AWS

AWS SDK 2.1692.0

Services used:

- **AWS Secrets Manager**

---

## Jira / Zephyr

Integration via **Axios**.

Capabilities:

- Integration with **Zephyr Scale**
- Upload of test results
- Test cycle management

---

## Google Drive

Using **googleapis 166.0.0**

Features:

- Automatic report upload
- OAuth 2.0 authentication
- Evidence sharing

---

# 🏛️ System Architecture

## General Architecture


User (Web Browser)
│
▼
Frontend (React + TypeScript)
Port 3000
│
HTTP / WebSocket
▼
Backend (Express + TypeScript)
Port 3004
│
▼
Newman (Postman CLI)
│
▼
External Integrations
AWS | Jira/Zephyr | Google Drive


---

## Multi-Project Architecture

The system supports multiple projects with independent configurations.


projects/
├── projectA
│ ├── .env
│ ├── postman/collections
│ ├── postman/data
│ └── postman/environments
├── projectB
│ ├── .env
│ ├── postman/collections
│ ├── postman/data
│ └── postman/environments


Each project contains:

- Independent configuration
- Dedicated Postman collections
- Project-specific CSV datasets
- Separate environments
- Isolated reporting structure

---

# ⚙️ Core Features

## Project Management

Features:

- Project selection from the UI
- Independent configuration per project
- Automatic configuration validation
- Dynamic project switching

Components:

- **ProjectManager (Backend)**
- **ProjectSelector (Frontend)**
- `/api/projects` API endpoints

---

## Collection Execution

### Standard Collections

Multiple sequential requests with shared variables.

Example:


Request 1 → Create resource
Request 2 → Validate resource
Request 3 → Update resource
Request 4 → Delete resource


---

### Runner Collections (CSV)

One request executed multiple times using CSV data.

Example:


Row 1 → Iteration 1
Row 2 → Iteration 2
Row N → Iteration N

---

# Reporting System

Custom HTML reports include:

- Interactive dashboards
- Execution statistics
- Test summary tables
- Detailed request logs
- Request/response body visualization
- Script execution results
- Assertion results
- Syntax highlighting for JSON
- Sensitive data masking
- Copy-to-clipboard utilities

---

### Metrics include

- Total requests
- Total iterations
- Total assertions
- Execution time
- Average response time
- Success rate

---

# Real-Time Communication

WebSocket events:

- `execution:log`
- `execution:progress`
- `execution:complete`
- `execution:error`

Benefits:

- Real-time monitoring
- Immediate feedback
- Reduced server load
- No polling required

---

# 🔄 Workflows

## Basic Execution Workflow


User selects project
→ Selects collection
→ Selects environment
→ Configures parameters
→ Executes tests
→ Backend runs Newman
→ Real-time logs via WebSocket
→ Reports generated
→ Results displayed


---

## CSV Execution Workflow


User selects project
→ Selects runner collection
→ Selects CSV
→ Preview data
→ Execute tests
→ Newman iterates through rows
→ Real-time progress updates
→ Consolidated report generated


---

## Full Integration Workflow


Test execution (Newman)
↓
HTML report generation
↓
Upload to Google Drive
↓
Link generated
↓
Upload results to Zephyr
↓
Attach evidence link
↓
Execution completed


---

# 🔌 Integrations

## AWS Secrets Manager

Purpose:

Secure centralized storage of sensitive credentials.

Examples:

- API tokens
- OAuth credentials
- External service API keys

Benefits:

- Encryption at rest
- Access control via IAM
- Secret rotation
- Full audit trail

---

## Jira / Zephyr Scale

Capabilities:

- Automatic test cycle creation
- Upload execution results
- Update test cases
- Add evidence links
- Track testing metrics

---

## Google Drive

Used for:

- Automatic report uploads
- Evidence storage
- Shareable report links
- OAuth authentication

---

# 🔐 Security & Secrets Management

## Hybrid Secrets System

Sources:

1️⃣ **AWS Secrets Manager (Primary)**  
2️⃣ **Environment Variables (.env)**  
3️⃣ **Temporary Cache**


.temp-secrets.json


---

## Security Components

### SecretsManager

Responsibilities:

- Retrieve secrets
- Validate secrets
- Cache secrets in memory

---

### SecretsScanner

Detects secrets in code:

- Prevents leaks
- Pre-commit validation
- Security reports

---

### AuditLogger

Logs secret access events **without exposing values**.

---

# 🚀 Deployment & Operations

## System Requirements

### Software

- Node.js ≥ 18
- npm ≥ 9
- AWS CLI configured
- Git

### Supported Browsers

- Chrome
- Firefox
- Safari
- Edge

---

# 📊 System Advantages

### 1. Full Type Safety

TypeScript across frontend and backend.

### 2. Fast Development

- Vite HMR
- Backend hot reload
- Instant feedback

### 3. Modern UI

Material UI design system.

### 4. Real-Time Updates

WebSocket event streaming.

### 5. Robust Testing

- Unit testing
- Integration testing
- Property-based testing

### 6. Scalability

Modular architecture with separated services.

### 7. Multi-Project Support

Independent configuration and isolation.

### 8. Security

- AWS Secrets Manager
- Audit logging
- Sensitive data masking

---

# 📚 Additional Documentation

External Resources:

- React
- TypeScript
- Material UI
- Express
- Socket.io
- Newman
- Vite
- AWS SDK

---

# 🎯 Executive Summary

**Newman UI Manager** is a modern Full-Stack platform for **API test automation using Postman collections**.

It supports:

- Multi-project environments
- Cloud integrations (AWS, Jira/Zephyr, Google Drive)
- Advanced reporting
- Secure secrets management

---

## Core Technologies

### Frontend

React + TypeScript + Material UI + Vite

### Backend

Express + TypeScript + Newman + Socket.io

### Integrations

AWS SDK + Jira API + Google APIs

---

## Key Benefits

- Full automation of API testing workflows
- Reduced manual execution time
- Complete test result traceability
- Integration with test management tools
- Secure secret management
- Scalable architecture for multiple projects and teams