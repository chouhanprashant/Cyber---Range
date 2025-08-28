# 🛠️ Phase 1: Basic Prototype Setup (1-2 हफ्ते)

## 1. Azure Account Setup (क्लाउड की दुकान खोलो)
**करना क्या है:** [portal.azure.com](https://portal.azure.com) पर जाकर Free Account बनाओ।  
**क्यों:** हमें VMs, Network, और दूसरे resources चाहिए।

## 2. Basic Web Portal (दिखने वाला हिस्सा)
**टेक्नोलॉजी:** HTML, CSS, JavaScript (React.js अगर आसान लगे)

**करना क्या है:** एक simple page बनाओ जहाँ:
- Login Button हो (Azure AD के साथ)
- "Launch Ransomware Scenario" नाम का एक बटन हो

## 3. Backend API (दिमाग वाला हिस्सा)
**टेक्नोलॉजी:** Node.js + Express

**करना क्या है:** एक API बनाओ जो ARM Template deploy करे।

```javascript
// server.js
const express = require('express');
const app = express();

app.post('/launch-scenario', (req, res) => {
  // Azure ARM Template deploy करने का code
  res.json({ message: 'Scenario launched!' });
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

---

# 🚀 Phase 2: Core Cyber Range Logic

## 4. ARM Template (Azure में lab बनाने का नक्शा)
**करना क्या है:** एक JSON file बनाओ जो Azure को बताएगी कि 3 VMs कैसे बनानी हैं।

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
  "contentVersion": "1.0.0.0",
  "resources": [
    {
      "type": "Microsoft.Network/virtualNetworks",
      "apiVersion": "2020-11-01",
      "name": "cyber-range-vnet",
      "location": "centralindia",
      "properties": { "addressSpace": { "addressPrefixes": ["10.0.0.0/16"] } }
    },
    {
      "type": "Microsoft.Compute/virtualMachines",
      "apiVersion": "2021-03-01",
      "name": "red-team-vm",
      "location": "centralindia",
      "properties": {
        "hardwareProfile": { "vmSize": "Standard_B2s" },
        "storageProfile": { /* OS Disk Details */ },
        "networkProfile": { /* Network Interface */ }
      }
    }
  ]
}
```

## 5. Simple Scoring Engine (नंबर देने वाला)
**करना क्या है:** एक function लिखो जो Blue Team के actions को track करे।

```javascript
let blueTeamScore = 0;

function detectAttack() {
  blueTeamScore += 10;
  console.log("Good job! Score: " + blueTeamScore);
}
```

---

# 🧪 Phase 3: Testing & Demo

## 6. Test Scenario: Ransomware Attack

**Red Team (Attack)**
- Red VM से एक phishing email भेजो।
- एक fake ransomware script चलाओ। (`echo "Files Encrypted!"`)

**Blue Team (Defend)**
- Blue VM पर Azure Sentinel Install करो।
- Alert आने पर score बढ़ाओ।

## 7. Demo Preparation
एक video बनाओ जो दिखाए:
- Login करना
- Scenario launch करना
- Red Team attack करना
- Blue Team defend करना
- Score show होना

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

एक working prototype जहाँ:
- User login करेगा
- एक button click करेगा
- Azure में 3 VMs automatically बन जाएंगी
- Red Team attack simulate करेगी
- Blue Team