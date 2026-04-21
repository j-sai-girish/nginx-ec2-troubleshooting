# 🚀 NGINX on EC2 - Troubleshooting Project

## 📌 Overview
This project demonstrates troubleshooting a real-world issue where an NGINX server was not accessible via public IP.

---

## ❌ Problem
Accessing:
http://public-ip

Resulted in a timeout error.

---

## 🔍 Investigation
- NGINX service was running
- Accessible via:
  http://public-ip:8080
- Port 80 was not allowed in Security Group
- NGINX was listening on port 8080

---

## 🧠 Root Cause
Mismatch between:
- NGINX configuration
- AWS Security Group rules
- Default HTTP port behavior

---

## ✅ Solution
1. Updated NGINX config:
   ```
   listen 80;
   ```

2. Allowed port 80 in Security Group

3. Restarted NGINX:
   ```
   sudo systemctl restart nginx
   ```

---

## 🎯 Result
Application accessible via:
http://public-ip

---

## 📸 Screenshots
See `/screenshots` folder:
- Failure case
- Working (8080)
- Security Group
- Config before/after
- Final output

---

## 💡 Key Learnings
- Importance of ports in networking
- Role of AWS Security Groups
- NGINX configuration basics
- Layered debugging approach

---

## 🛠️ Tools Used
- AWS EC2
- NGINX
- Linux (Ubuntu)

---

## 🔗 Author
J Sai Girish
