# SkyDock Autonomous Weed-Elimination Drone

SkyDock is an autonomous drone project designed to automatically identify and remove weeds within a defined perimeter using advanced flight control and machine learning. The drone performs a perimeter sweep to map the area and detect potential weeds using an onboard ML model. After completing the sweep, it generates a heatmap of weed locations and autonomously flies to the nearest candidate to verify and eliminate the weed using a targeted herbicide spray system.

The drone operates using a hybrid approach: it hovers for precision tasks and can deploy attached plane-like wings to glide between distant targets, saving battery and extending mission range. A secondary ML model confirms weed detections to avoid false positives before spraying. The sprayer uses image-based targeting to convert the weed's location in the camera frame to real-world coordinates, ensuring accurate application.

For safety and reliability, the drone includes:

* **Manual override controls** for immediate operator intervention.
* **Battery-aware autonomy**, which automatically returns the drone to a charging station when low on power, then resumes the mission when fully charged.
* **Tree and obstacle avoidance**, initially supported by manually placed beacons that create exclusion zones.

The project leverages **Mission Planner** for perimeter flight paths and telemetry integration, and a **Raspberry Pi 5** for onboard ML inference, data collection, and payload control. Custom drone hardware includes high-powered motors, a Matek H743 flight controller, GPS, airspeed sensors, and a precision sprayer system.

The repository is organized into key components:

* **flight\_control/** – Autonomous mission execution, waypoint following, glide mode logic
* **perception/** – ML-based weed detection, verification, and inference scripts
* **actuation/** – Sprayer targeting, centering, and herbicide release controls
* **power\_management/** – Battery monitoring, return-to-charge, and mission resume
* **avoidance/** – Tree avoidance via beacons and zone mapping
* **manual\_override/** – Real-time operator intervention logic
* **utils/** – Shared functions for telemetry, coordinate transforms, and logging

SkyDock’s goal is to deliver a fully autonomous, precise, and energy-efficient weed removal system capable of long-duration operation with minimal human intervention.

