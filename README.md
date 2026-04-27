# Queue Wait Time POC

Live wait-time estimator for a queue with two doorway sensors (one at the line entry, one at the service point).

## How it works

- Each entry/exit is a doorway crossing event from `GET /v3/doorways/{id}/events`
- Queue length = cumulative entries − cumulative exits
- Throughput = exit events in last 5 minutes ÷ 5 (people per minute)
- Estimated wait = queue length ÷ throughput (Little's Law)

The current page runs synthetic data so the visualization can be demoed without a real sensor pair.

## Run locally

Open `index.html` in a browser. No build step.
