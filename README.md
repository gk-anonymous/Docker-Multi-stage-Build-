# 🚀 Flask Docker Multi-Stage Build

## 📌 Project Overview
This project demonstrates a **Docker multi-stage build** for a Flask application. It helps to create lightweight and optimized Docker images for deployment.

## 📂 Project Structure
```
📦 flask-docker-app
├── 📄 app.py          # Flask application
├── 📄 run.py          # Entry point for running the Flask app
├── 📄 requirements.txt # Dependencies
├── 📄 Dockerfile      # Multi-stage build setup
└── 📄 README.md       # Project documentation
```

---

## 🛠️ Setup Instructions
### 1️⃣ Clone the Repository
```sh
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO
```

### 2️⃣ Install Dependencies (For Local Testing)
```sh
pip install -r requirements.txt
```

### 3️⃣ Run the Flask Application Locally
```sh
python run.py
```

---

## 🐳 Docker Instructions
### 4️⃣ Build Docker Image
```sh
docker build -t flask-docker-app .
```

### 5️⃣ Run the Docker Container
```sh
docker run -p 5000:5000 flask-docker-app
```

### 6️⃣ Access the Application
Open your browser and go to:
```
http://localhost:5000
```

---

## 📌 Dockerfile Explanation
This project uses a **multi-stage build** for optimizing the final image.
```dockerfile
# Stage 1: Builder
FROM python:3.7 AS builder
WORKDIR /app
COPY requirements.txt .
RUN pip install --prefix=/install -r requirements.txt

# Stage 2: Production Image
FROM python:3.7-slim
WORKDIR /app
COPY --from=builder /install /usr/local
COPY . .
ENTRYPOINT ["python", "run.py"]
```

### ✅ **Benefits of Multi-Stage Build:**
- **Reduces Image Size** 🚀
- **Improves Security** 🔒
- **Optimizes Build Process** ⚡

---

## 📜 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🤝 Contributing
Feel free to **fork** this repo, submit **issues**, or make **pull requests**. Contributions are always welcome! 😊

---

## 📞 Contact
- **Author:**Gaurav KAMBLE
- **GitHub:** (https://github.com/gk-anonymous)
- **Email:** gauravkamble9112@gmail.com

Happy Coding! 🚀🔥

