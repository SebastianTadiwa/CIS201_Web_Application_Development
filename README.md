# Leave Management and Real-Time Availability (FFIMS Module F4.2)

## Overview
The **Leave Management and Real-Time Availability** submodule is a critical component of the Fleet and Facilities Integrated Management System (FFIMS). It replaces Africa University’s manual, paper-based leave request system with a digital, mobile-responsive workflow. The module provides supervisors with live visibility into driver status to ensure the **5-in/5-out rotation** remains fully staffed and to manage sudden gaps caused by illness or emergencies.

## Key Features
*   **Digital Leave Workflow:** Enables drivers to submit leave applications (Personal, Medical, etc.) with automated routing to supervisors for approval or rejection via centralized cards.
*   **Real-Time Availability Board:** A dynamic dashboard displaying every driver's current status: **On Duty, Standby, On Leave, Off Duty, or Unavailable**.
*   **One-Tap Status Updates:** A simplified interface for drivers to update their status instantly, minimizing the need for manual phone calls.
*   **Accrual and Balance Tracking:** Automatically tracks monthly leave accruals versus used days, providing transparency for both staff and HR.
*   **WebSocket Notifications:** Uses real-time bidirectional communication to alert standby personnel immediately when a gap is detected in the roster.
*   **Predictive Analytics:** Implements machine learning models to analyze historical patterns and predict potential future availability challenges.

## Technical Architecture
*   **Frontend:** **React.js** with **Redux** for state management and **Material-UI** for responsive, mobile-first design.
*   **Backend:** **Node.js** and **Express.js** handling API requests and business logic.
*   **Real-Time Engine:** **Socket.io (WebSockets)** for instant availability updates across the system.
*   **Database:** **PostgreSQL** with **Sequelize ORM** for relational data persistence.
*   **AI/ML:** **Python (scikit-learn)** for predicting leave patterns and availability challenges.

## Relational Database Design
The module relies on the following relational tables:
*   **Leave_Requests:** Stores dates, reasons, and status (Pending, Approved, Rejected).
*   **Leave_Balances:** Tracks accrued and used days per employee.
*   **RealTime_Availability:** Logs current worker status for the dashboard board.
*   **Audit_Trail:** Tracks who made status changes or approvals for accountability.

## UI/UX Standards
*   **Mobile-First Design:** Optimized for drivers using smartphones on limited network conditions (low-bandwidth friendly).
*   **Shared UI Components:** Strictly uses components from `src/components/ui/` such as **Cards, Badges, and Buttons** for design consistency.
*   **Color-Coded Status:** Uses standard badges (e.g., Green for On Duty, Yellow for Standby, Red for Unavailable) to reduce cognitive load.

## Git Workflow Fundamentals
Contributors must follow the team's standard version control process:
1.  **Clone** the repository to your local machine.
2.  **Pull** the latest changes from `origin master` before starting.
3.  **Create a feature branch** for specific tasks (e.g., `git checkout -b feature-leave-validation`).
4.  **Stage and Commit** changes with descriptive messages.
5.  **Push** to GitHub and create a **Pull Request** for peer review before merging into the main branch.

## Installation
1.  Clone the repository.
2.  Run `npm install` to load dependencies (including `socket.io-client` and `material-ui`).
3.  Configure your environment variables in `.env` for PostgreSQL connectivity.
4.  Launch the development server: `npm run dev`.
