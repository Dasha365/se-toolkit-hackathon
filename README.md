# Trip Sketch

AI-powered travel planner that generates, saves, and refines personalized trip itineraries.

## Demo

Screenshots of the application:

- Trip creation form
- Generated itinerary view
- Saved trip history and regeneration

## Product context

### End users
People who want to quickly create a travel itinerary based on a few preferences and refine it later.

### Problem
Planning a trip from scratch can be time-consuming and overwhelming. Users often know only the destination, trip length, budget, and a few preferences, but still need to turn that into a realistic day-by-day plan.

### Your solution
Trip Sketch is a lightweight web app that uses an LLM to generate a structured itinerary, save it in a database, and let the user regenerate improved versions.

## Features

### Implemented features
- Generate a trip itinerary using an LLM
- Save generated trips to PostgreSQL
- View saved trip history
- Open full trip details
- Regenerate a trip with refinement instructions
- Additional preferences field for initial generation
- Web frontend for interaction
- Dockerized deployment on Ubuntu VM

### Not yet implemented features
- External APIs for real-time travel prices and schedules
- User authentication
- Search and filtering in trip history
- Stronger validation for refinement quality

## Usage

1. Open the frontend in the browser.
2. Enter destination, number of days, budget, interests, and travel style.
3. Optionally add additional preferences.
4. Click **Generate Trip**.
5. View the generated itinerary.
6. Open saved trips from the history panel.
7. Optionally refine an existing trip and generate a new version.

## Deployment

### VM OS
Ubuntu 24.04

### What should be installed on the VM
- Docker
- Docker Compose
- Git
- Python 3

### Step-by-step deployment instructions

1. Clone the repository:
   `git clone <repo-url>`

2. Open the project directory:
   `cd se-toolkit-hackathon`

3. Create a `.env` file in the project root with:
   `OPENAI_API_KEY=...`
   `OPENAI_BASE_URL=...`
   `OPENAI_MODEL=...`

4. Start backend and database:
   `docker compose up --build -d`

5. Start the frontend:
   `cd frontend`
   `python3 -m http.server 8080 --bind 0.0.0.0`

6. Open in browser:
   - Frontend: `http://<VM-IP>:8080`
   - Backend docs: `http://<VM-IP>:8000/docs`
