
# 🚀 CodeXcel – Online Judge System

CodeXcel is a full-stack **Online Judge (OJ)** platform designed to provide a seamless competitive programming experience.  
It allows users to submit code for problems, evaluates them in a sandboxed environment, and displays results in a leaderboard-style format.  
Built using the **MERN stack (MongoDB, Express.js, React.js, Node.js)** and containerized with **Docker**, CodeXcel provides a scalable and efficient solution for managing competitive coding environments.

---

## 🎯 Objective

Build an efficient, scalable, and secure platform that mimics real-world competitive coding platforms like Codeforces or LeetCode, focusing on learning system design, containerization, and multi-language code evaluation.

---

## 🏗 Architecture

```plaintext
+----------------+      +----------------+      +--------------------+
|    React.js    | <--> |  Express.js    | <--> |  MongoDB Database  |
|   Frontend UI  |      |   REST APIs    |      | (Problems, Users,  |
+----------------+      +----------------+      | Submissions, etc.) |
        |                         |             +--------------------+
        |                         |
        |                         |    +---------------------+
        |                         +--> | Code Execution       |
        |                              | Service (Dockerized) |
        |                              +---------------------+
        |                                      |
        |                                      |
        |                              +----------------+
        |                              | AWS ECR & EC2  |
        |                              | (Deployment)   |
        |                              +----------------+
```

---

## ⚡ Technology Stack

- **Frontend:** React.js, TailwindCSS, HTML, CSS  
- **Backend:** Node.js, Express.js (REST APIs)  
- **Database:** MongoDB  
- **Authentication:** JWT (JSON Web Tokens)  
- **Code Execution:** Custom compiler running inside Docker containers  
- **Deployment:**  
  - AWS EC2 for hosting backend & compiler services  
  - AWS ECR for storing Docker images  

---

## ✅ Key Features

- User Authentication (Sign-up, Login)  
- Problem Listing, Searching, and Filtering by Difficulty or Tags  
- Problem CRUD Operations (for Admins)  
- Code Submission in Multiple Languages (C, C++, JavaScript)  
- Secure and Isolated Code Execution using Docker  
- Real-Time Result Evaluation (Accepted, Wrong Answer, Time Limit Exceeded, Runtime Error)  
- Leaderboard System showing top coders  
- Scalable handling of concurrent submissions (100+ simultaneous users)  

---

## ⚙ Workflow

### 1️⃣ Problem Management  
- Admins add new problems via REST API with test cases stored in the database.  
- Each problem has constraints, sample inputs/outputs, and multiple test cases.

---

### 2️⃣ User Interaction  
- Users browse problems and submit code solutions via the frontend interface.  
- Submissions are sent to the backend via REST API.

---

### 3️⃣ Code Execution  
- The backend receives the code and pushes it to a **Dockerized custom compiler service**.  
- Code runs inside an isolated Docker container.  
- Input is fed from stored test cases; output is captured.

---

### 4️⃣ Output Validation  
- The user’s program output is compared to the **expected output** stored for that test case:  
    - For exact-match problems: Trimmed string comparison.  
    - For flexible problems (e.g., permutations): Custom checker scripts.  
- Based on the result, the submission is labeled:  
    ✅ Accepted (AC) | ❌ Wrong Answer (WA) | ⏱ Time Limit Exceeded (TLE) | ⚠ Runtime Error (RE).

---

### 5️⃣ Leaderboard Update  
- Accepted submissions increment the user's score.  
- Real-time leaderboard updates show rankings based on problems solved and submission time.

---

## 📦 Docker Usage

- Docker & Docker Compose are used for:
    - Isolated code execution environments.
    - Easy deployment of backend + compiler services.
  
- Images stored in AWS ECR and deployed to AWS EC2 for scalability.

---

## 🚀 Deployment

- AWS EC2 hosts backend and compiler services.  
- AWS ECR stores Docker images.  
- Autoscaling is supported through Docker Compose for handling more simultaneous submissions.

---

## 📚 Future Improvements

- Implement microservices architecture for independent scaling of services.  
- Support more programming languages (Go, Rust,JavaScript..).  
- Add real-time notifications for submission results.  
- Add contest management system.  

---

## 📞 Contact

Aditya Kumar  
📧 aditya767718@gmail.com  
🔗 [GitHub – CodeXcel](https://github.com/spidycoder/CodeXcel)  
🔗 [Demo Video](https://www.loom.com/share/bd68e69294ae4b4abc636cba0a6cc01e)  

---

## ⚡ License

This project is open-sourced for educational purposes.
