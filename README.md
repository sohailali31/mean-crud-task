## README.md


## MEAN Stack Deployment with Docker, Jenkins CI/CD, and Nginx

This repository documents the deployment process for a MEAN (MongoDB, Express, Angular, Node.js) application using Docker, Jenkins CI/CD, and Nginx on an AWS EC2 instance.


## 1. Push Project to GitHub

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<username>/<repo>.git
git push -u origin main
````

---

## 2. Login to Docker Hub

```bash
docker login -u <dockerhub-username>
```

---

## 3. Build & Push Backend Docker Image

```bash
cd backend
docker build -t <dockerhub-username>/mean-backend .
docker push <dockerhub-username>/mean-backend
```

---

## 4. Build & Push Frontend Docker Image

```bash
cd frontend
docker build -t <dockerhub-username>/mean-frontend .
docker push <dockerhub-username>/mean-frontend
```

---

## 5. Connect to AWS EC2

```bash
ssh -i key.pem ubuntu@<EC2_PUBLIC_IP>
```

---

## 6. Install Docker and Docker Compose

```bash
sudo apt update && sudo apt install docker.io -y
sudo systemctl enable docker
sudo usermod -aG docker ubuntu
sudo apt install docker-compose -y
```

---

## 7. Run Application Using Docker Compose

```bash
docker-compose up -d
docker ps
```

---

## 8. Install Nginx

```bash
sudo apt install nginx -y
sudo nano /etc/nginx/sites-enabled/default
sudo nginx -t
sudo systemctl restart nginx
```

---


---

## 9. Jenkins Deployment Commands (Used in Pipeline)

```bash
docker-compose pull
docker-compose down
docker-compose up -d
docker ps
```

---

## 10. Verify Application

Open in browser:

```
http://<EC2_PUBLIC_IP>:4200
```

---

## 11. Validation Checklist

```txt
✔ Code pushed to GitHub
✔ Docker images built and pushed
✔ Docker Compose running on EC2
✔ Nginx reverse proxy configured
✔ Jenkins CI/CD pipeline working
✔ Application accessible in browser
```

---

## Author

```txt
Mohammad Sohail Ali
Cloud & DevOps Engineer
```

```

---

Would you like me to:

- Convert this to a **PDF**?
- Add **screenshots placeholders**?
- Add a **simple diagram**?

Just tell me: **PDF**, **Screenshots**, or **Diagram**.
```
