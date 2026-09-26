# Adaptive Traffic Signal Simulator

A Python and Pygame simulation that compares a fixed-cycle traffic signal with a queue-adaptive, rule-based controller across a 4 × 4 grid of intersections.

## What it demonstrates

- A live visualization of vehicles moving through a city grid
- A fixed-time baseline that alternates signal direction on a 120-step cycle
- An adaptive controller that estimates traffic demand from simulated vehicles near each intersection
- Longer green phases when one direction has a heavier queue
- Priority for simulated ambulances
- A Matplotlib plot comparing each vehicle's recorded crossing time in both modes

## How the controller works

The adaptive mode counts north-south and east-west vehicles in a detection area around each intersection. It uses the difference between those counts to select the next direction and adjusts green duration to the observed queue. An ambulance in the detection area receives immediate priority.

Despite the repository's original “AI-Powered” name, this implementation is a rule-based adaptive heuristic. It does not train or run a machine-learning model, and it uses simulated vehicle positions rather than camera or sensor data.

## Requirements

- Python 3.10 or newer
- Pygame
- Matplotlib

## Run

```bash
python -m pip install -r requirements.txt
python traffic_signal_simulation.py
```

The simulator runs the fixed-cycle mode first, then the adaptive mode, and opens a comparison plot when both runs finish. Close the Pygame window to stop the current simulation.

## Reading the comparison

The plot shows recorded vehicle crossing times in simulation steps. Vehicle arrivals, direction, speed, and target intersection are randomized, so a single run is an exploratory demonstration rather than a controlled performance study. The model does not represent real road geometry, calibrated traffic demand, pedestrian phases, or real-world safety constraints.

## Project structure

- `traffic_signal_simulation.py` — Pygame simulation, signal controllers, vehicle movement, and comparison plot
- `requirements.txt` — Python dependencies

