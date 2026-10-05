# iParhai – Recommendation Service

The recommendation API behind **iParhai**, an AI-based adaptive learning platform built as my final year project at FAST NUCES. Students practise exam questions, and this service works out which topics they're weak in and what they should practise next.

## Endpoints

| Method | Route | What it does |
|---|---|---|
| GET | `/questions/{count}` | Returns a set of practice questions |
| POST | `/submit-answers/` | Records a student's answers |
| GET | `/recommend-wrong-questions/` | Recommends questions similar to ones the student got wrong |
| GET | `/recommend-weak-subtopics/` | Finds the subtopics the student is weakest in |

## How it works

- Questions and attempts are stored in MongoDB, accessed asynchronously with Motor
- Similar questions are found with TF-IDF vectors and cosine similarity (scikit-learn), after text cleaning with NLTK

## Tech stack

Python · FastAPI · MongoDB (Motor) · scikit-learn · NLTK

## Run it

```bash
pip install -r requirements.txt
# set MONGO_URI in your environment
uvicorn app:app --reload
```

The web and mobile apps for iParhai were built with the MERN stack and React Native.
