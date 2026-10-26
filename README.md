# Riyadh Smart Trip 🚗🚇

An interactive Python command-line application that helps users plan trips in Riyadh, estimate travel times, and compare car and metro options.

> **Note:** Traffic conditions, route durations, fuel costs, and metro fares are estimates based on sample data and the available station information. The application does not provide live traffic or turn-by-turn navigation.

## Overview

Riyadh Smart Trip helps users make more informed travel decisions by entering an origin, destination, and departure time.

The application estimates car travel duration based on simulated traffic patterns, checks for available metro routes, compares estimated travel times and costs, and recommends an option based on the user's priority.

Users can also save trips, manage saved records, view reports, and get a suggested departure time to arrive by a desired time.

## Features

| Feature | Description |
|---|---|
| Trip planning | Enter an origin, destination, and departure time |
| Traffic estimation | Estimate car travel duration based on the time of day |
| Transport comparison | Compare car and metro duration and estimated cost when a metro route is available |
| Smart recommendation | Choose fastest, lowest cost, or best balance of time and cost |
| Visual comparison | Display a Matplotlib chart comparing car and metro duration |
| Trip management | Save, view, update, and delete trips |
| Trip reports | View saved-trip statistics and the fastest estimated car and metro trips |
| Traffic report | Display available Riyadh traffic statistics |
| Departure suggestion | Find a suggested departure time for a desired arrival time |
| Input validation | Handle invalid times, trip numbers, and unavailable routes |

## User Stories

As a traveler, I can:

- Plan a trip and see its estimated duration and traffic period.
- Compare car and metro travel when a metro route is available.
- Choose a travel priority and receive a recommendation.
- View a chart comparing estimated travel times.
- Save, view, update, and delete trips.
- Review trip statistics and traffic information.
- Enter my desired arrival time and get a suggested departure time.
- Receive clear messages when input is invalid or route data is unavailable.

## Technologies Used

- **Python** — application logic and command-line interaction
- **Rich** — formatted terminal tables, panels, and messages
- **Questionary** — interactive menu and selection prompts
- **Matplotlib** — travel-time comparison charts
- **Requests** — retrieving metro station data where supported
- **JSON** — route data, station data, and saved trips

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/muathhhh/UNIT-PROJECT-1.git
cd UNIT-PROJECT-1
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the environment

**Windows — Git Bash:**

```bash
source venv/Scripts/activate
```

**Windows — PowerShell:**

```powershell
.\venv\Scripts\Activate.ps1
```

**Windows — Command Prompt:**

```bat
venv\Scripts\activate.bat
```

### 4. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 5. Run the application

```bash
python main.py
```

## Usage

Run `main.py` and use the arrow keys to select an option. Press Enter to confirm your selection.

| Option | Feature |
|---|---|
| 1 | Plan a Trip |
| 2 | View Saved Trips |
| 3 | View Trip Report |
| 4 | Update a Trip |
| 5 | Delete a Trip |
| 6 | Suggest Departure Time |
| 7 | Exit |

### Example: Planning a Trip

Enter your starting location, destination, and departure time when prompted.

```text
Starting location: KAFD
Destination: National Museum
Departure time (HH:MM): 08:00
```

The exact prompts may vary. If a matching metro route is available, the application displays the car and metro estimates, asks for your priority, and presents a recommendation and comparison chart.

After the operation finishes, press Enter to return to the main menu.

### Travel Priorities

- **Fastest Trip:** recommends the option with the shorter estimated travel time.
- **Lowest Cost:** recommends the option with the lower estimated cost.
- **Best Balance (Time + Cost):** compares normalized travel-time and cost scores.

### Tips

- Location names are case-insensitive.
- Car routes must exist in `routes.json`.
- Metro availability depends on the available station data and supported route logic.
- Some neighborhood-to-neighborhood journeys may have a car estimate but no supported metro route.
- Metro routes are limited to a single line; transfers are not currently supported.

## Project Structure

```text
UNIT-PROJECT-1/
├── main.py
├── trips.py
├── transport_advisor.py
├── metro_data.py
├── traffic_data.py
├── traffic_stats.py
├── storage.py
├── models.py
├── trip_charts.py
├── routes.json
├── locations.json
├── traffic_stats.json
├── requirements.txt
├── tests/
└── README.md
```

**Key files:**

- `main.py` — main menu and user interaction
- `trips.py` — trip planning
- `transport_advisor.py` — car/metro comparison and recommendations
- `metro_data.py` — metro station data and route estimation
- `traffic_data.py` — simulated traffic periods and duration estimates
- `traffic_stats.py` — traffic report
- `storage.py` — loading, saving, updating, and deleting trips
- `trip_charts.py` — comparison charts
- `routes.json` — sample car route data
- `locations.json` — metro station data
- `traffic_stats.json` — traffic statistics used by the report
- `requirements.txt` — Python dependencies

Saved trips are stored in `trips.json`. This file is created or updated by the application when trips are saved. Personal or local test data should not be committed to the repository unless intentionally included as sample data.

## Running the Tests

If the project includes its unit tests, run:

```bash
python -m unittest
```

Run the command from the project root while the virtual environment is active.

## Limitations

- Traffic estimates are simulated and are not live traffic measurements.
- Car routes use sample data.
- Car cost estimates cover fuel only, not parking, maintenance, or other expenses.
- Metro fares and durations are estimates.
- Metro route planning supports a single line and does not currently handle transfers.
- Recommendations depend on the available route data and estimation rules.

## Future Improvements

- Integrate a live traffic or maps API.
- Support metro transfers and multi-line journeys.
- Connect neighborhoods to nearby metro stations.
- Expand route coverage and improve cost estimates.
- Add more automated tests and error-handling scenarios.

## Author

**Muath Mohammad Sufani**
