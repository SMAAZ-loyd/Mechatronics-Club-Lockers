# Mechatronics Club Locker Portal

A lightweight, dark-mode web application designed for the Mechatronics Club to manage locker assignments, track monthly membership fees (300 PKR), and maintain a secure inventory of items stored by members. 

The portal features a public registration form for students and a password-protected Core Team Dashboard backed by a private Google Sheet for 24/7 real-time synchronization.

---

## Features

* **Public Student Portal:** Simple submission form capturing student details, locker selection, payment reference, and a mandatory itemized inventory of hardware/components stored inside.
* **Core Team Dashboard:** Password-protected executive view to inspect all active locker assignments, view sensitive item inventories, and export records.
* **Google Sheets Backend:** Automatically logs submissions 24/7 without requiring a dedicated server or paid database hosting.
* **Data Export:** Built-in CSV export tool for easy auditing by the club treasurer and executive body.

---

## Tech Stack

* **Frontend:** HTML5, CSS3, Vanilla JavaScript (Single-file architecture)
* **Backend / Database:** Google Apps Script & Google Sheets
* **Hosting:** GitHub Pages

---

## Setup & Deployment Guide

### 1. Google Sheets & Apps Script Setup
1. Create a new **Google Sheet** and share it exclusively with your core team members.
2. Name the columns in Row 1: `Timestamp`, `Locker`, `Name`, `RollNo`, `Phone`, `Payment`, `Contents`.
3. In the top menu, go to **Extensions > Apps Script**.
4. Paste the backend script code (configured with your secret core access key) and save.
5. Click **Deploy > New deployment**, select **Web app**, set execution to **Me**, access to **Anyone**, and deploy. Copy the generated Web App URL.

### 2. Frontend Configuration
1. Open `index.html` in a text editor.
2. Locate the `SCRIPT_URL` variable at the top of the script block:
   ```javascript
   const SCRIPT_URL = "https://script.google.com/macros/s/AKfycby8kGes2bFoDjudsVtUAmZePzyZSYhIThstYf5He48B3XXOqi6CjQ-i8p0vE48S42FDbw/exec";
