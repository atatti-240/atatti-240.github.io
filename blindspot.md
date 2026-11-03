## BlindSpot: Houston Commute Planner

**Project description:** BlindSpot tells Houston commuters when to leave and which way to go, before traffic hits. Waze and Google Maps react to congestion after it forms; BlindSpot predicts the things they miss. Built by a team in 48 hours.

**My role:** I owned the routing engine, the prediction models, and the backend.

### What it predicts

- **Freight trains blocking at-grade crossings**, learned per crossing for every 15-minute slot of the week
- **Crash-prone freeway stretches**, learned per road segment and hour, with a Faster vs. Safer slider that routes around them
- **Tomorrow's congestion**, a score per road and 15-minute slot, updated daily with a moving average
- **Why a road is slow**, splitting delay into causes (rush hour, crashes, events, trains, lane closures, rain, construction) and showing an icon for each on the map

### Live AI cameras

Real traffic-camera video runs through the team's computer-vision app, which boxes and counts vehicles, estimates speeds, and flags incidents. Confirmed incidents show up on the map and in alerts, and routes go around them.

### Planning

It computes the latest departure that still gets you there on time, pushes "leave earlier" / "new route" / "leave now" alerts, and says when a watched road clears. Live reports override predictions for the next 30 minutes, every answer shows a confidence level and data source, and errands with up to 3 stops get an optimized stop order.

### Tech Stack

Python backend (FastAPI, uv) and a Next.js / TypeScript frontend, with OpenStreetMap road data and METRO's GTFS transit timetable. Traffic and train data are synthetic for now, behind interfaces built for Houston TranStar and TrainWatch feeds.

[View the code on GitHub](https://github.com/atatti-240/houston-traffic-app)

[← Back to Portfolio](/)
