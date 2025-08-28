# 🛠️ Phase 1: Basic Prototype Setup (1-2 Weeks)

## 1. Azure Account Setup
- Create a free account at [portal.azure.com](https://portal.azure.com).
- Required for deploying virtual machines and networking resources.

## 2. Basic Web Portal
- Technologies: HTML, CSS, JavaScript (React.js recommended).
- Build a simple web page with:
  - Login button (using Azure AD).
  - "Launch Ransomware Scenario" button.

## 3. Backend API
- Technology: Node.js + Express.
- Create an API to trigger Azure deployments using ARM templates.

---

# 🚀 Phase 2: Core Cyber Range Logic

## 4. ARM Template
- Create a JSON template to automatically deploy 3 virtual machines and networking in Azure.

## 5. Simple Scoring Engine
- Implement a function to track and display Blue Team actions and scores.

---

# 🧪 Phase 3: Testing & Demo

## 6. Test Scenario: Ransomware Attack
- Red Team: Simulate a phishing email and a fake ransomware script.
- Blue Team: Install Azure Sentinel, detect the attack, and increase the score.

## 7. Demo Preparation
- Prepare a video showing:
  - Login
  - Scenario launch
  - Red Team attack
  - Blue Team defense
  - Score display

---

# 💰 Estimated Cost for Prototype

| Item                      | Cost (Approx)           |
|---------------------------|-------------------------|
| Azure Credits (Free Tier) | ₹0 (First ₹17,000 free) |
| Domain Name               | ₹500/year               |
| Developer Time (2 weeks)  | ₹0 (If you code yourself)|
| **Total**                 | **₹500**                |

---

# ✅ Final Output - Prototype Demo

A working prototype where:
- User logs in
- Clicks a button
- 3 VMs are automatically created in Azure
- Red Team simulates an attack
- Blue Team defends
- Score is displayed