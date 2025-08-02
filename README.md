# 🔗 Elementor to Google Sheets Connector

A lightweight and fast Google Apps Script to capture Elementor Pro form submissions and store them directly into **Google Sheets** — no third-party plugin required.

---

## ✍️ Developed By

**Fingvo**  
*Full Stack Developer*  
GitHub: [@fingvo]https://github.com/fingvo

---

## 📌 Overview

This script acts as a **webhook listener** and connects Elementor Pro form submissions directly to a Google Sheet. It's designed to be flexible, customizable, and easy to maintain.

Features:

- ✅ Dynamic sheet and column creation
- ✅ Exclude meta/unwanted fields (IP, User Agent, etc.)
- ✅ Optional email notifications
- ✅ Support for custom field ordering
- ✅ Fast, lightweight, and serverless

---

## 🛠️ How It Works

1. Deploy the script as a **Web App** via Google Apps Script.
2. Add the Web App URL as a **Webhook** in your Elementor form.
3. On form submission, data is flattened, sanitized, and inserted as a new row in your Google Sheet.
4. Sheet and headers are auto-created based on submission fields.

---

## 🚀 Setup Instructions

### 1. Copy the Script

Open your target **Google Sheet**, then go to:

> `Extensions` → `Apps Script` → Paste the code from [code.gs](code.gs)

---

### 2. Deploy as Web App

- Click `Deploy` → `New deployment`
- Select `Web App`
- Set:
  - **Execute as**: `Me`
  - **Who has access**: `Anyone`
- Click `Deploy`
- Copy the **Web App URL**

---

### 3. Configure Elementor

In your Elementor Form:

- Add a new **Webhook** action
- Paste the copied Web App URL into the **Webhook URL** field
- Done! 🎉

---

## 🧩 Optional Hidden Fields

| Field | Purpose |
|-------|---------|
| `e_gs_SheetName` | Sheet name where data will be saved |
| `e_gs_order` | Comma-separated list of fields to define column order |
| `e_gs_exclude` | Comma-separated list of fields to exclude from submission |

**Example:**  
```html
<input type="hidden" name="e_gs_SheetName" value="Contact Form">
<input type="hidden" name="e_gs_order" value="name,email,message">
<input type="hidden" name="e_gs_exclude" value="user_ip,form_url">
