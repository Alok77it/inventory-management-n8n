# 📦 Inventory Management System with n8n

This project automates IT asset inventory management using [n8n](https://n8n.io/). It connects a Telegram group for updates, reads and writes to Google Sheets, and handles duplicate checks with alerting functionality.

---

## 🧠 Features

- 📩 Triggered by messages from Telegram group
- 🔍 Parses messages to extract:
  - Asset Name
  - Serial Number
  - MAC Address
  - Employee Name & ID
  - OS Info
- 📊 Interacts with Google Sheets:
  - Checks for existing asset
  - Updates existing records
  - Appends new entries
- 🚨 Alerts sent via Telegram if:
  - Duplicate Serial Number/MAC Address exists
  - Serial or MAC is mismatched with asset or employee
- ✅ Fully automated with conditional logic (IF nodes)

---

## 🔧 Tech Stack

- [n8n](https://n8n.io/) – Workflow automation
- [Google Sheets](https://www.google.com/sheets/about/) – Inventory database
- [Telegram Bot](https://core.telegram.org/bots) – Trigger + Alerts

---

## 🖼 Workflow Overview

![Workflow Architecture](./images/workflow-architecture.png)

---

## 🧩 Workflow Logic

1. **Trigger:** Telegram message
2. **Parse Node:** Extract structured data
3. **Google Sheets:** Read current inventory
4. **Check Logic:**
   - IF Serial Exists but different Asset → 🔔 Alert
   - IF MAC Exists but different Asset → 🔔 Alert
   - IF Serial Exists but different Employee ID → 🔔 Alert
5. **Actions:**
   - Update sheet if valid match
   - Append sheet if new asset
   - Telegram alert if mismatch or duplicate

---

## 🚀 Message Format Examples

