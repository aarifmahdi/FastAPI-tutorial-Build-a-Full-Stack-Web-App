# FastAPI-tutorial-Build-a-Full-Stack-Web-App
documenting my journey of learning FastAPI following corey schafer's videos.

DAY 1 - 12th MAY 2026 (~ 25mins)

NOTES:
Goal (by the end of this playlist): I will be able to Build a full feature web application (FastAPI)

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


DAY 2 - 13th May 2026 (~ 45mins)

NOTES:
I'll be doing the following (today in in next few days):
- install fastAPI ✅ (did today)
- create a basic application
- build routes (that return JSON)
- run the app (from command line CLI)
- look at automatic documentation
- get dummy data
- create an API endpoint
- create HTML responses

uv is a fast python package manager (alternative of pip python package manager)
- To create a fastapi project, you can either:
    use uv (creates directory using uv commands)
or
    use pip (create a directory for your project then use pip)

for pip:
1. create a project directory (manually)
2. go into the project directory (cd project_directory)
3. install fastAPI in the project directory (by running):
pip install "fastapi[standard]"
*using [standard] is recommended!
*using quotes "" is recommended cuz some shells have problems with using square brackets [] without quotes

for uv: 
1. create a project directory (by running):
uv init project_name
2. go into the project directory (cd project_name)
3. uv add "fastapi[standard]"
*we used uv!

what does fastapi[standard] includes:
- fastapi framework
- uvicorn (ASGI server to run our application)
- uvicorn (fastAPI CLI command to run our application)

ASGI: Asynchronous Server Gateway Interface
(watch https://www.youtube.com/watch?v=TYIRWdgO9QQ every asgi concept in a single video ~3mins for reinforcement)
- ASGI provides interface b/w async capable web servers (eg: uvicorn, gunicorn) and web applications (eg: fastapi, django)
- ASGI is successor to WSGI (Web Server Gateway Interface, Synchronous interface)
*callable : just a fancy term for functions in Python (for accurate understanding, In Python, a callable is any object that can be executed using parentheses (), eg: functions/methods/classes)

- to open vscode from CLI (cmd in Windows) use command:
code . (make sure you're in the project directory which you wanna open in vscode)

for day3, continue from 8:12 (of video)

