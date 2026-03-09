# Verified Agent Identity — Termux Setup Guide

## ⚡ One-Command Install

Open Termux on your Android phone and paste this single command:

```bash
curl -sL https://raw.githubusercontent.com/FASHAKING/Billions-verified-agent-installer/main/install-agent.sh | bash
```

That's it! The script will:
- Update your Termux packages
- Install Node.js and Git
- Clone the repository
- Install all dependencies (including common missing ones)
- Prompt you for your **Agent Name** and **Description**
- Create your Agent Ethereum Identity
- Link your Human Identity with your Agent
- Give you a verification URL to complete in your browser

---

## 🔧 Manual Step-by-Step (if you prefer)

### Step 1 — Update Termux
```bash
pkg update && pkg upgrade
```

### Step 2 — Install Node.js and Git
```bash
pkg install nodejs
pkg install git
```
Verify with `node -v` — you should see something like `v25.x.x`.

### Step 3 — Clone the Repository
```bash
git clone https://github.com/BillionsNetwork/verified-agent-identity
cd verified-agent-identity
```

### Step 4 — Install Dependencies
```bash
npx clawhub@latest install verified-agent-identity
```
> Type `y` and press Enter whenever prompted.

### Step 5 — Create Agent Ethereum Identity
```bash
node scripts/createNewEthereumIdentity.js
```

### Step 6 — Link Human Identity with Agent
```bash
node scripts/manualLinkHumanToAgent.js --challenge '{"name":"YourAgentName","description":"AI agent"}'
```
Replace `YourAgentName` with your desired agent name.

After running this, you'll get a **verification URL** in the terminal.  
Copy it → open in browser → connect wallet → verify. Done!

---

## 🛠 Common Error Fixes

### Error: Cannot find module 'shell-quote'
```bash
npm install shell-quote
```
Then re-run the command from Step 5.

### Error: Cannot find module '@iden3/js-iden3-auth'
```bash
npm install @iden3/js-iden3-auth
```
Then re-run the command from Step 6.

> **Note:** The one-command installer pre-installs both of these modules automatically, so you shouldn't hit these errors if you use it.

---

## ❓ Need Help?

If you get stuck, feel free to open an issue or ask in the community.
