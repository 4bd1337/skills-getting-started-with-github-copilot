# Copilot Agent Instructions for Mergington High School Activities

## Project Overview
- This is a FastAPI-based web app for managing extracurricular activities signups at Mergington High School.
- The backend is in `src/app.py` and exposes a simple REST API for activities and signups.
- The frontend is static HTML/CSS/JS in `src/static/` and interacts with the API via fetch calls.
- All data is stored in memory (no database); restarting the server resets all signups.

## Key Files & Structure
- `src/app.py`: FastAPI app, defines endpoints `/activities` (GET) and `/activities/{activity_name}/signup` (POST).
- `src/static/index.html`: Main UI, lists activities and provides signup form.
- `src/static/app.js`: Handles fetching activities and posting signups; updates UI dynamically.
- `src/static/styles.css`: Cyberpunk-themed styles for the UI.
- `src/README.md`: API usage, endpoints, and data model documentation.

## Developer Workflows
- **Install dependencies:** `pip install fastapi uvicorn`
- **Run server:** `python src/app.py` (default port: 8000)
- **Access API docs:** [http://localhost:8000/docs](http://localhost:8000/docs)
- **Frontend:** Open `src/static/index.html` directly or serve via FastAPI static files.
- **No database:** All data is lost on server restart; useful for demos and exercises.

## Patterns & Conventions
- **Activities** are keyed by name; each has description, schedule, max participants, and a list of signed-up emails.
- **Signups** are performed via POST to `/activities/{activity_name}/signup?email=...`.
- **Frontend** expects JSON responses and updates UI based on API results.
- **Cyberpunk UI:** Custom styles and background music (see `<audio>` in HTML).
- **No authentication/authorization**; all endpoints are open.
- **Error handling:** API returns JSON with `detail` on error; frontend displays messages in `#message` div.

## Integration Points
- **Frontend-backend communication:** Only via REST API endpoints described above.
- **Static assets:** All in `src/static/`.
- **No external DB or persistent storage.**

## Example: Adding a New Activity
- Update the activities data structure in `src/app.py`.
- No migrations or DB changes needed.

## Example: Customizing UI
- Edit `src/static/index.html` and `src/static/styles.css`.
- JS logic for API calls is in `src/static/app.js`.

---
For questions or unclear patterns, check `src/README.md` for API details or ask for clarification.
