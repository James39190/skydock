SkyDock Autonomous Weed-Elimination Drone

SkyDock is an innovative, autonomous drone solution for precision weed control in agricultural and environmental settings. By leveraging advanced flight planning, onboard machine learning, and a targeted herbicide delivery system, SkyDock automates the full weed management cycle, dramatically reducing manual labor and herbicide usage while offering environmental and economic benefits.

Table of Contents

Overview

Features

How It Works

Architecture

Safety & Reliability

Getting Started

Roadmap

Overview

SkyDock uses a two-phase approach: an initial perimeter sweep to detect and map potential weeds, followed by targeted engagement where each candidate is verified and treated. A heatmap of detections guides efficient routing to minimize flight time and battery consumption. Between tasks, the drone can switch to a glide mode—using fixed wings—to conserve energy during longer transits. Custom hardware, including a high-performance flight controller and Raspberry Pi 5, enables real-time processing and precise actuation. Its modular design ensures individual components—from perception to power management—can be upgraded or replaced, facilitating continuous improvement and adaptation.

Features

Autonomous Perimeter Sweep: Follows user-defined GPS boundaries, capturing images and logging candidate weed locations in real time.

ML-Based Detection & Verification: A primary model identifies possible weeds; a secondary classifier confirms true positives to prevent unnecessary spraying.

Precision Spraying System: Converts image coordinates to real-world spray commands for accurate herbicide application at the weed’s center.

Hybrid Flight Modes: Hovers for detection and spraying, then deploys fixed wings to glide optimally between distant targets, reducing power consumption.

Automated Power Management: Monitors battery levels, autonomously returns to a charging station when thresholds are reached, and resumes the mission after recharge.

Manual Exclusion Zones: Beacon-based beacons define tree or hazard zones that the drone will avoid.

Operator Override & Telemetry: Real-time control overrides and live telemetry streams ensure safe human intervention at any stage.

How It Works

Mission Setup: Define perimeter waypoints in Mission Planner and configure charging station and exclusion beacon locations.

Perimeter Sweep: Primary ML model processes each frame for possible weeds and logs GPS-tagged detections.

Heatmap Generation: Fuse logged points into a spatial heatmap; high-density zones become priority targets.

Target Engagement: Drone flies to the nearest hotspot; the secondary model verifies the weed before spraying.

Spraying: The system aligns the squirter to the weed’s center and releases herbicide precisely.

Energy Optimization: Ascend to optimal altitude and switch to glide mode for longer transits, leveraging passive lift to save power.

Battery Handling: If battery drops below the low threshold, the mission pauses and the drone returns to the charger; after full recharge, it picks up where it left off.

Cycle Continuation: Repeat steps 2–7 until all targets are treated or the mission is manually aborted.

Architecture

Flight Control: Interfaces with Mission Planner for waypoint navigation, mode switching, and telemetry feedback.

Perception: Manages image capture and dual-stage ML inference on a Raspberry Pi 5.

Actuation: Coordinates camera-to-world mapping and controls the precision squirter hardware.

Power Management: Tracks battery state, executes return-to-charge logic, and persists mission state for seamless resumption.

Avoidance System: Processes beacon signals to construct exclusion zones that dynamically influence path planning.

Operator Interface: Provides a manual override layer and telemetry dashboards for live monitoring.

Safety & Reliability

Dual-Stage Verification: Ensures high-confidence weed detection before spraying.

Conservative Thresholds: Protect against mission-critical failures with safe battery and altitude settings.

Beacon-Based Exclusion: Allows human operators to mark hazards and prevent collisions.

Manual Override: Instantly pause or redirect the drone at any time.

Environmental Compensation: Maintains stable flight in uneven terrain and windy conditions.

Getting Started

Clone the repositorygit clone https://github.com/freddygaffey/skydock.git

Install dependenciespip install -r requirements.txt

Configure Mission Planner: Define perimeter waypoints, charging station GPS coordinates, and place exclusion beacons.

Deploy ML Models: Train or load pretrained detection and verification models into the inference directory.

Launch SkyDockpython main_control.py

Refer to docs/SETUP.md for detailed instructions.

Roadmap

Phase 1 (Weeks 1–3): Mission Planner integration, data logging, and basic ML pipeline.

Phase 2 (Weeks 4–6): Heatmap logic, verification refinement, and precision actuation.

Phase 3 (Weeks 7–9): Battery management, glide optimization, and obstacle avoidance.

Phase 4 (Weeks 10–14): Environmental robustness testing, manual override polish, and UI enhancements.

Phase 5 (Months 4–6): Real-world data retraining, adaptive mission replanning, and full documentation.

