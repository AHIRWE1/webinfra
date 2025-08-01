# FitPlanner 🏋️‍♀️🥗

**FitPlanner** is a minimal, responsive web application that generates personalized daily fitness plans using external APIs. Users input their weight, height, goal weight, body fat percentage, and available ingredients — and the app responds with:

- 🎯 3 suggested meals based on ingredients (via Tasty API)
- 🏋️ 3 random exercise suggestions (via ExerciseDB API)
- 💬 A motivational quote to boost their mood (via ZenQuotes)

---

## 🚀 Installation & Setup (Docker + Load Balancer)

> Make sure Docker is installed on your system.

```bash
# Clone the repository
git clone <repo-url>
cd webinfra

# Build and start the app containers
docker compose up -d --build

# Visit the app in your browser
http://localhost:8082
🔁 Load Balancer Test
Use this command to verify that the HAProxy load balancer is alternating responses between the two backend containers:

bash
Copy
Edit
curl -I http://localhost:8082
You should see alternating server IPs or Docker container IDs in the response headers or slight content differences.

💡 How FitPlanner Works
User Input:
The user provides their physical data and available kitchen ingredients via a simple form.

Meal Suggestions:
FitPlanner queries the Tasty API for 3 meal suggestions based on the entered ingredients. It displays meal titles and brief descriptions.

Exercise Generator:
It fetches 3 random workouts from the ExerciseDB API to guide the user's daily movement.

Motivational Boost:
The app fetches a motivational quote from ZenQuotes to encourage the user.

Local Storage:
All input data is saved in localStorage, making the app stateful and extendable.

📦 APIs Used
Tasty API (RapidAPI)

ExerciseDB API (RapidAPI)

ZenQuotes API

🔐 API Key Handling
⚠️ In development, API keys are included in the frontend for simplicity.
In production, always use a secure method such as environment variables or backend proxies to hide sensitive credentials.

Technologies Used
HTML, CSS, JavaScript (Vanilla)

Docker + Nginx (Static Serving)

HAProxy (Load Balancer)

RapidAPI integrations

📸 Demo Video
Here is the link to video.
https://youtu.be/pNjrQdwkuTw


Author
Gabriella Ange Ahirwe

© 2025 FitPlanner — Built with care and purpose 💙