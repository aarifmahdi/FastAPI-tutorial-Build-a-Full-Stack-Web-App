# FastAPI-tutorial-Build-a-Full-Stack-Web-App
documenting my journey of learning FastAPI following corey schafer's videos.

DAY 1 - 13th MAY 2026 (~ 25mins)

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


DAY 2 - 14th May 2026 (~ 45mins)

NOTES:
I'll be doing the following (today in in next few days):
- install fastAPI ✅ (did today)
- create a basic application ✅ (did on 15th May 2026)
- build routes (that return JSON) ✅ (did on 15th May 2026 - still in process)
- run the app (from command line CLI) ✅ (did on 15th May 2026 - and now it's an everyday job)
- look at automatic documentation ✅ (did on 15th May 2026 - and now it's an everyday job, after building a route/api endpoint i have to look at this to test the api)
- get/return dummy data ✅ (both in HTML and JSON forms)
- create an API endpoint ✅ (did on 15th May 2026 - still in process. i think routes and api endpoints are same thing but depending on context we call it route or api endpoint. just like the parameter/argument terms, when we write the code we use the term routes, when we search for the web page/api we call it api endpoint)
- create HTML responses ✅

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

DAY 3 - 15th MAY 2026 (~ 25mins)

NOTES:
today, i built basic fastapi application with two lines of code.
then i created a home route "/".
then launched the application/server (uvicorn)
and saw api docs (both swaggerUI and modern docs)

- basic fastapi application code (2 lines):

from fastapi import FastAPI

app = FastAPI()

- fastapi uses decorator for routes
- home route: responds to GET request at root URL
- to run fastapi application, use fastapi command (in CLI in fastapi application directory ofcouurse):

fastapi dev main.py (if u installed fastapi using pip)
uv run fastapi dev main.py (if u installed fastapi using uv)

- u can run fastapi application in dev mode (fastapi dev command) OR production mode (fastapi run command)
- in dev mode, it reloads the server whenever we make changes in our code (dev mode is best for development/debugging)
- production mode is best for performance

- code that creates the root/home route:

@app.get("/")
def home():
    return {"message": "Hello, World!"}

*fastapi converts this return dictionary into JSON first (automatically)

/docs opens swaggerUI api docs (http://localhost:8000/docs)
/redoc opens a modern api doc (http://localhost:8000/redoc)

- api docs (swaggerUI) provide the exact command to write in terminal to get the response in CLI (instead of using the api docs)
*this way you can test your apis through terminal/CLI as well (its more cool imo)

for day4, continue from 14:49 (of video) AND before doing that, run the fastapi application (i.e. launch the server first)

DAY 4 - 16th MAY 2026 (~ 20mins)

NOTES:
today i created a route that returns JSON ("/api/posts" route)
tested this route (first way to test a route is by typing the URL on browser and seeing the results/response on the browser
second way to test a route is to go to the fastapi api docs http://localhost:8000/docs and try it out there!)

- returning JSON on an API endpoint (route) is GREAT for **PROGRAMMATIC ACCESS**
- **PROGRAMMATIC ACCESS**: FRONTEND and other services can connect to BACKEND i.e. get this JSON data through programmatic acces (i.e. through these api endpoints/routes) 

for day5, continue from 17:46 (of video) AND before doing that, run the fastapi application (i.e. launch the server first)
day5 will be interesting cuz we r gonna return HTML page on an api endpoint (for humans/users to see)


DAY 5 - 17th MAY 2026 (~ 35mins)

NOTES:
to display HTML in browser (for humans/users):
- make sure you have imported HTMLResponse from fastapi.repsonses
- set the paramater response_class=HTMLResponse (in the decorator of your route)
- return HTML in the function definiton
e.g:
                                                             👇
@app.get("/", response_class=HTMLResponse)
def home():
    return f"<h1>{posts[0]['title']}</h1>"

(test this api/route/endpoint, it should display/return HTML page in browser)

Q: what if we want to return same HTML in browser on 2 routes?
A: just stack the different routes on same route function
e.g:
@app.get("/", response_class=HTMLResponse, include_in_schema=False)
@app.get("/posts", response_class=HTMLResponse, include_in_schema=False)
def home():
    return f"<h1>{posts[0]['title']}</h1>"

👆here we stacked the routes on same route function home so now the home function is executed for route "/" as well as for rout "/posts"
means when we got to http://127.0.0.1:8000/ it gives the same HTML as on http://127.0.0.1:8000/posts (pre-requisite: ofcouurse when the server is running)

- learning: to get the same response on different routes in fastapi, simply stack the decorators/routes on the same route function

*NOTE/POINT TO REMEMBER: the api docs (at http://127.0.0.1:8000/docs) are meant specially for api routes (api routes are used for programmatic access/consumption).
HTML routes should not be dispayed in fastapi's api docs, HTML routes are for users to see in browser not for programmatic access/consumption)
to hide HTML routes (or any route) in the api docs, set the parameter include_in_schema=False in the decorator of your route)
e.g:                                          
                                                           👇
@app.get("/", response_class=HTMLResponse, include_in_schema=False)
@app.get("/posts", response_class=HTMLResponse, include_in_schema=False)
def home():
    # return {"message": "Hello, World!"}  # fastapi converts this dictionary into JSON first (automatically)
    return f"<h1>{posts[0]['title']}</h1>"

(you should do this for HTML routes or any route(s) that are not api routes, only include api routes in api docs)

api routes: routes that return JSON are api routes

SUMMARY (DAY1-DAY5):
✅ fastapi installed
✅ created basic fastapi application
✅ created routes
✅ returns dummy data (both HTML and JSON forms)
✅ we have automatic documentation (at http://127.0.0.1:8000/docs OR http://127.0.0.1:8000/redoc)
✅ the docs only show api routes (not the HTML routes)

NEXT TARGETs (DAY6 onwards)
for day6, continue from 22:39 (on yt)
