INITIAL SETUP
.............................................................................................
🟢 STAGE 1 — FastAPI Setup & First Running API
🎯 Goal of Stage-1

By the end you should:

run FastAPI server

open it in browser

create one GET endpoint

see auto docs working

If these 4 work → setup done.

1️⃣ Install FastAPI (Environment Setup)
✅ Create virtual environment (inside repo)

Open terminal in VS Code:

python -m venv venv

Activate:

Windows
venv\Scripts\activate
Mac/Linux
source venv/bin/activate

👉 Why venv?

keeps project dependencies separate

real dev practice

avoids version conflicts

✅ Install packages
pip install fastapi uvicorn
What they do:

FastAPI → framework to build API
Uvicorn → server that runs your API

FastAPI alone cannot run — needs ASGI server like Uvicorn.

2️⃣ Create Your First FastAPI App

Create file:

main.py

Add:

from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "FastAPI is working"}
🧠 Understand this code
🔹 from fastapi import FastAPI

Imports the framework.

🔹 app = FastAPI()

Creates your API application object.

Think:

Flask → app = Flask()
FastAPI → app = FastAPI()

This app is the main server instance.

🔹 @app.get("/")

This is a route decorator.

Means:

When user visits "/"
Run this function

GET = HTTP method.

🔹 Function returns dictionary
return {"message": "FastAPI is working"}

FastAPI automatically converts it to JSON:

{"message": "FastAPI is working"}

No manual JSON conversion needed.

3️⃣ Run the Server

In terminal:

uvicorn main:app --reload
🧠 Understand this command
main     → filename main.py
app      → FastAPI object name
--reload → auto restart when code changes
4️⃣ Open in Browser
Root API
http://127.0.0.1:8000

You should see:

{"message":"FastAPI is working"}
Auto Documentation (VERY IMPORTANT)
http://127.0.0.1:8000/docs

FastAPI automatically creates:

Swagger UI

interactive API testing panel

This is one reason FastAPI is modern.
