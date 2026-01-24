# Jenkins CI/CD Pipeline using WSL & AWS EC2

## 📌 Project Overview
This project demonstrates a complete CI/CD pipeline using Jenkins installed on WSL (Ubuntu) that automatically deploys application code to an AWS EC2 server.

The pipeline continuously monitors a GitHub repository for changes and deploys the updated code to a live server using SSH.

---

## 🛠️ Technologies Used
- Jenkins
- WSL (Ubuntu)
- Git & GitHub
- AWS EC2
- SSH
- Linux
- Apache Web Server

---

## ⚙️ Architecture Flow
1. Developer pushes code to GitHub
2. Jenkins (running on WSL) polls SCM every minute
3. On detecting changes:
   - Jenkins pulls latest code
   - Transfers files to AWS EC2 via SSH
   - Executes deployment commands remotely
4. Application is deployed to `/var/www/html`

---

## 🔁 Jenkins Job Configuration
- **Trigger:** Poll SCM (`* * * * *`)
- **Build Steps:**
  - Git pull from repository
  - SSH file transfer to EC2
  - Remote command execution:
    ```bash
    sudo cp -r /home/ubuntu/deploy/* /var/www/html/
    sudo rm -rf deploy
    ```

---

## 🚀 Deployment Output
- Code successfully deployed on AWS EC2
- Web application accessible via EC2 public IP

---

## 🔐 Security Considerations
- SSH key-based authentication
- Jenkins credentials managed securely
- No secrets committed to repository

---

## 📸 Screenshots
(Add Jenkins job screenshots here)

---

## 🎯 Learning Outcomes
- Hands-on CI/CD pipeline implementation
- Jenkins automation using SCM polling
- Secure deployment using SSH
- Real-world DevOps workflow experience

---

## 👨‍💻 Author
**Sachin Jaiswal**  
Cloud Engineer | AWS Enthusiast | DevOps
📧 djsachin9511@gmail.com 
🔗 https://www.linkedin.com/in/djsachin

