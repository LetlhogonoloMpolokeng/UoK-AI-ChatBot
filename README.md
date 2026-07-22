UoK AI ChatBot
An AI-powered chatbot built for University of Kimberley (UoK) prospective students — handles admissions FAQs, student enquiries, and appointment/service bookings through a web chat interface.
> **Group project note:** This started as a team project (forked from [FekSta/UoK-AI-ChatBot](https://github.com/FekSta/UoK-AI-ChatBot)). My contribution was the **frontend/UI** — see the ["Website UI" pull request](https://github.com/FekSta/UoK-AI-ChatBot/pull/1) merged into the original repo, and the later "Updating UI" commit on this fork.
What it does
Classifies user messages into intents (e.g. admissions questions, general enquiries) using a trained NLP model
Falls back to regex pattern matching when the model isn't confident
Tracks conversations per session in a SQLite database (users, sessions, messages)
Supports service/appointment bookings through the chat flow
Serves the whole thing through a Flask web app with an HTML/CSS/JS chat interface
Tech stack
Backend: Python, Flask
NLP/ML: TensorFlow, Keras, NLTK (intent classification model trained on `intents.json`)
Database: SQLite
Frontend: HTML, CSS, JavaScript (Jinja2 templates)
Project structure
```
Flask WebApp/
├── app.py              # Flask routes, DB setup, session/message handling
├── utils.py            # Model loading, prediction, response logic
├── model/              # Trained intent classification model
├── DataBase/            # Database-related files
├── templates/           # HTML templates (chat UI)
├── static/               # CSS/JS/assets
└── UoK.db                # SQLite database
Model_Prep/               # Model training/preparation scripts
```
Running it locally
```bash
cd "Flask WebApp"
pip install -r requirments.txt
python app.py
```
My contribution
I worked on the chat UI — the frontend the user actually interacts with, including the interface shown in the "Website UI" PR and later UI refinements. The NLP model, database schema, and Flask routing were built collaboratively with the rest of the team (FekSta, Artolog).
