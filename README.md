🎤 Pronunciation Analysis API with FastAPI
A machine learning-powered tool to detect correct/incorrect pronunciation

📌 Overview
This project provides a RESTful API that analyzes audio files and classifies pronunciation as either Correct or Incorrect using a pre-trained KNN model.

Built with:

FastAPI (Backend framework)

Librosa (Audio feature extraction)

JWT (Secure authentication)

🚀 Key Features
✅ User authentication via JWT (Login/Register)
✅ Audio file analysis (.wav) with classification:

Correct

Incorrect
✅ User management (Stores data in users.json)

⚙️ Requirements
Python 3.10+

Dependencies (listed in requirements.txt):

bash
Copy
Edit
pip install -r requirements.txt
🔧 Setup & Usage
Clone the repository:

bash
Copy
Edit
git clone https://github.com/youssefibrahim13/myfastapiproject .git
cd your-repo
Install dependencies:

bash
Copy
Edit
pip install -r requirements.txt
Run the server:

bash
Copy
Edit
uvicorn main:app --reload
Access interactive docs:

arduino
Copy
Edit
http://127.0.0.1:8000/docs
📂 Project Structure
graphql
Copy
Edit
project/
├── main.py              # Main API entry point
├── auth.py              # JWT authentication system
├── audio_processing.py  # Audio feature extraction
├── models/              # Pre-trained model (KNN_xbestx_model.pkl)
├── users.json           # User database (auto-generated)
├── requirements.txt     # Required libraries
└── README.md            # This file
🔐 API Endpoints
1. 🔑 Authentication

Method	Endpoint	Description
POST	/register	Register a new user
POST	/token	Login (get JWT)
2. 🎤 Audio Analysis

Method	Endpoint	Description
POST	/analyze/	Upload & analyze audio
📄 Example Requests
1. Register a new user:

bash
Copy
Edit
curl -X POST "http://127.0.0.1:8000/register" \
-H "Content-Type: application/json" \
-d '{"username": "user1", "full_name": "Test User", "password": "pass123"}'
2. Login (get JWT token):

bash
Copy
Edit
curl -X POST "http://127.0.0.1:8000/token" \
-H "Content-Type: application/x-www-form-urlencoded" \
-d "username=user1&password=pass123"
3. Analyze an audio file:

bash
Copy
Edit
curl -X POST "http://127.0.0.1:8000/analyze/" \
-H "Authorization: Bearer YOUR_TOKEN" \
-F "file=@test.wav"
