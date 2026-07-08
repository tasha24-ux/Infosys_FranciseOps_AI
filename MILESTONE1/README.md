Infosys Springboard Internship 7.0 – Milestone 1
Secure User Authentication & Intelligent Analytics Portal
📋 Project Overview
Milestone 1 focuses on designing and deploying a secure, production-ready User Authentication Module integrated with a high-fidelity data visualization dashboard. Built as a Single-Page Application (SPA) using Streamlit, this architecture incorporates industry-standard security protocols, stateless session tracking, server-side validation rules, and an asynchronous multi-route identity recovery system.

The application runs seamlessly in a cloud environment (Google Colab), securely utilizing hidden environment secrets and exposing the local instance to a public URL for evaluation.

🚀 Core Features Built
Secure Registration (Signup Page)

Collects unique username, email, password, and security question mappings.
Enforces field sanitization and strict complexity checks using Regex patterns.
Saves records using salted cryptography to prevent data exposure.
Multi-Class Authentication (Login Page)

Features dedicated authorization channels for Standard Users and Administrators.
Applies strict protection boundaries, utilizing generic error tracking to prevent account enumeration attacks.
Issues a stateless session token upon a successful cryptographic handshake.
Multi-Route Identity Recovery (Forgot Password Page)

Route A (Deterministic Challenge): Validates a normalized user response against a hashed answer matching a preset security question.
Route B (Asynchronous SMTP Token): Generates a random 6-digit OTP code on the fly and dispatches it over secure Google mail relays using automated SMTP connection handshakes.
Role-Based Post-Auth Dashboards

User Viewport: Displays key performance indicators, document tracking matrices, and interactive system status gauge tracking powered by Plotly charts.
Admin Console (infosys@ai): Bypasses standard telemetry data to grant privileged access to the core database user ledger for administrative monitoring.
Stateless Session Guarding

Implements JSON Web Tokens (JWT) to safely preserve state across client requests without overloading storage variables or dropping verification records upon browser reloads.
💻 Tech Stack Used
Frontend Interface: Streamlit (Configured with a custom neutral corporate theme focusing on Slate and Blue palettes).
Database Engine: SQLite3 (Relational persistent storage architecture).
Cryptographic Security: bcrypt (Salted cryptographic password hashing) & PyJWT (HS256 Session Signing).
Communication Infrastructure: Python smtplib & email.mime (Gmail SMTP Relay Network).
Data Visualization: Plotly Graph Objects (Dynamic metric interfaces).
Environment Isolation: Google Colab Secrets Engine (google.colab.userdata).
⚙️ How to Setup and Run the Notebook
To execute the code and launch the web server successfully, follow these deployment guidelines:

Phase 1: Configure Environment Secrets
Before opening the notebook, click on the Secrets (Key Icon) sidebar inside Google Colab and add the following keys exactly as specified below. Ensure the Notebook access toggle switch is flipped ON for all three:

Secret Name	Description / Value Requirement
JWT_SECRET	A long, secure, random alphanumeric string used to cryptographically sign session tokens.
EMAIL_ADDRESS	The host Gmail address used to dispatch verification OTPs (e.g., your-email@gmail.com).
EMAIL_PASSWORD	A 16-digit Google App Password (generated from Google Account Security settings, not your regular login password).
Phase 2: Execution Workflow
Open the primary project notebook inside Google Colab.
Run the initial configuration cells to install the mandatory external dependency packages (pyjwt, bcrypt, streamlit-option-menu, plotly).
Execute the %%writefile app.py cell block to compile the frontend interface logic, database initializations, and layout definitions into a local script.
Run the background terminal activation block (streamlit run app.py &) alongside your network tunnel configurations (such as ngrok or alternative secure tunneling tools) to generate a public proxy domain url.
Click on the generated public link to enter and test the portal environment.
📸 Screenshots
The visual proof of operational execution across all core terminal views is captured and documented below:

Login Viewport
Signup Interface
Forgot Password (Security Question Route)
Forgot Password (SMTP Mail OTP Verification Engine)
Received OTP Notification Email
Standard User Analytics Portal
Administrative Privileged Console Ledger
