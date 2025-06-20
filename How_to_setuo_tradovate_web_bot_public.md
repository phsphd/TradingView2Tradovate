## **📦 Complete Installation & Setup Guide**

### **🎯 Part 1: Installing tradovate-auto-trader.crx on Chrome**

#### **Step 1: Download the Extension**
- Download `tradovate-auto-trader.crx` to your computer
- Remember the download location (usually Downloads folder)

#### **Step 2: Enable Developer Mode**
1. Open **Google Chrome**
2. Go to `chrome://extensions/` (type this in address bar)
3. Toggle **"Developer mode"** ON (top-right corner)
4. You should see new buttons appear: "Load unpacked", "Pack extension", etc.

#### **Step 3: Install the CRX File**
**Method A: Drag & Drop (Easiest)**
1. Open **File Explorer** (Windows) or **Finder** (Mac)
2. Navigate to your **Downloads** folder
3. **Drag** `tradovate-auto-trader.crx` file
4. **Drop** it onto the Chrome Extensions page
5. Click **"Add extension"** when prompted

**Method B: If Drag & Drop Doesn't Work**
1. Right-click `tradovate-auto-trader.crx` → **"Open with"** → **Chrome**
2. Chrome will ask: **"Add extension?"** → Click **"Add extension"**

#### **Step 4: Verify Installation**
✅ Extension appears in your extensions list  
✅ Shows **"Inspect views service worker"** (means background is running)  
✅ Extension icon appears in Chrome toolbar  

---

### **🌐 Part 2: Setting Up WebSocket Connection**

#### **Step 1: Open Tradovate Platform**
1. Go to `https://trader.tradovate.com/`
2. **Log into** your Tradovate account
3. Make sure you're on the **trading interface**

#### **Step 2: Connect Extension to Server**
1. **Click** the Tradovate Auto Trader extension icon in Chrome toolbar
2. Extension popup opens showing "**Not connected**"
3. Click **"Connect to Server"** button
4. Status should change to **"Connected to server"** ✅
5. You'll see **"Connected"** with uptime counter

#### **Step 3: Verify Connection**
Check the popup shows:
- ✅ **Green status indicator**
- ✅ **"Connected to server"** message  
- ✅ **Uptime counter** running
- ✅ **WebSocket status: OPEN**

---

### **📊 Part 3: Setting Up TradingView JSON Alerts**

#### **Important Note About Signal Source:**
Your extension receives signals from **WebSocket server** (`wss://excellgen.com/websk`), **NOT directly from TradingView**. TradingView alerts need to be sent to your WebSocket server first.

#### **Step 1: TradingView Alert Setup**
1. **Open TradingView** → Go to your chart
2. **Right-click** on chart → **"Add Alert"**
3. **Configure your alert conditions** (price, indicators, etc.)

#### **Step 2: Alert Message Configuration**
In the **"Message"** field, use these JSON formats:

**For Tradovate-Only Signals:**
```json
{"type": "buy", "extension": "tradovate"}
```
```json
{"type": "sell", "extension": "tradovate"}
```

**For Common Signals (if you have multiple extensions):**
```json
{"type": "buy"}
```
```json
{"type": "sell"}
```

**For Advanced Signals:**
```json
{"type": "exit-mkt-cxl", "extension": "tradovate"}
```
```json
{"type": "cancel-all", "extension": "tradovate"}
```

#### **Step 3: Webhook Configuration**
⚠️ **Important:** Your TradingView alerts need to send to **your WebSocket server**, not directly to Chrome extension.

**Webhook URL Setup:**
- **URL:** Your server endpoint that forwards to `wss://excellgen.com/websk`
- **Method:** POST
- **Content-Type:** application/json

---

### **🔧 Part 4: Testing the Complete Setup**

 
1. **Create a simple TradingView alert** with small position
2. **Use test JSON:** `{"type": "buy", "extension": "tradovate"}`
3. **Verify execution** on Tradovate platform
 

---

### **📋 Part 5: Troubleshooting Guide**

#### **Extension Not Installing:**
- ✅ Make sure **Developer mode** is enabled
- ✅ Try **Method B** (right-click → open with Chrome)
- ✅ Check Chrome version (needs Chrome 88+)

#### **Service Worker Not Running:**
- ✅ Look for **"Inspect views service worker"** link
- ✅ If missing, reload extension: Extensions page → Reload button
- ✅ Check console for JavaScript errors

#### **WebSocket Connection Failed:**
- ✅ Check internet connection
- ✅ Verify server `wss://excellgen.com/websk` is accessible
- ✅ Try **Disconnect** → **Connect** in popup

#### **Signals Not Executing:**
- ✅ Verify **WebSocket connection** is active (green status)
- ✅ Check **signal format** matches extension filter
- ✅ Ensure you're on **trader.tradovate.com** page
- ✅ Look for **trading buttons** on Tradovate interface

---


### **📞 Support Checklist**

**Before asking for help, check:**
- ✅ Extension installed and service worker active
- ✅ Connected to WebSocket server (green status)  
- ✅ On trader.tradovate.com page
- ✅ Alert JSON format correct
- ✅ Console logs show signal received and processed

**This complete setup gives you automated trading from TradingView alerts through your WebSocket server to Tradovate execution!** 🚀