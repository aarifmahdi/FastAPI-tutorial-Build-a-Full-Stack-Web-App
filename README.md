# FastAPI-tutorial-Build-a-Full-Stack-Web-App
documenting my journey of learning FastAPI following corey schafer's videos.

DAY 1 - 12th MAY 2026 (~ 25mins)

NOTES:
Goal: Be able to Build a full feature web application (FastAPI)

FastAPI features (to learn about):
- automatic API documentation (swaggerUI thing, now have a newer version as well)
- built-in data validation (ig its referring to "pydantic" models)
- "async" support

API returns JSON data (in this project)
(JSON is the most common format, otherwise an API can return data in many different formats JSON/XML/Plain text/HTML/CSV/YAML/Binary etc)

(
term: API routes
what are routes?

routes -> endpoints
)

frontend: frontend is built to present the backend/API results for a user (UI/UX related smth)

(
API endpoints
what are API endpoints?

endpoint -> URL
)

background task: an api can have background task(s) for eg: "forgot password functionality" - when u click on forgot password and it tells u to reset password, the background task is emailing the user for password reset.

dynamic pagination: website page ko neechy scroll krty krty when u hit the limit (eg: 50 videos per page) then u see load more pages button, that is dynamic pagination! (which loads more data on run-time i.e. dynamically)

we'll build (in this complete playlist):
- JSON REST API
- HTML pages
- database with SQLAlchemy (SQLite, PostgreSQL)
- pydantic models (for data validation)
- CRUD operations

- user registration/login 

- secure password hashing + JWT tokens

- file uploads
- background task (sending email)

- organize our code (with routers)
- async/await (when and how to use asynchronous vs synchronous)

* patterns + best practices (production-grade)
*testing
*deployment

for day 2, continue from 5:00 (of video)
