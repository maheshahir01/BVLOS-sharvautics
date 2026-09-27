Team Sharvautics
Installation and Run Instructions
1. Tested Environment
•	Operating System: Ubuntu 26.04.1 under WSL2
•	ROS 2: Lyrical
•	Gazebo: Jetty (gz-sim 10.5.0)
•	PX4: v1.18.0-rc1 (tested commit fca3df86…)
•	Python: 3.14
•	pymavlink: 2.4.49
•	PyYAML: 6.0.3
•	pytest: 9.0.2
2. System Requirements
The supplied package was validated on Ubuntu 26.04.1 under WSL2. The complete GUI demonstration was validated in this environment. A bare Ubuntu 26.04 container was also used to test installation, PX4 build, ROS graph, four-UAV startup, dashboard operation and the headless mission.
The package has not been validated on a physical fresh machine, native Ubuntu installation, or Ubuntu 24.04. Package-manager patch versions may also change over time.
3. Source Package
Source archive:
UAV-X_Resilient_BVLOS_Swarm_Stage1_Source.zip
SHA256 checksum:
d0db03c03998b336c18b33d821c037ca608ec9bc44a5b71945e2e6816fa12a5c
4. Installation
Follow the steps below in order.
1.	Extract the source archive
unzip UAV-X_Resilient_BVLOS_Swarm_Stage1_Source.zip
2.	Enter the extracted project directory
cd UAV-X_Resilient_BVLOS_Swarm_Stage1_Source
3.	Check dependencies without changing the system (optional)
./install.sh --check
4.	Install and configure the required dependencies
./install.sh
The installation script checks the required environment, installs required base packages, sets up the ROS/PX4-related dependencies, installs Python requirements and prepares the project for execution. It is designed to avoid destructive changes to unrelated projects.
5. Verify the Installation
After installation, verify that the required environment is available. The project documentation and test suite provide additional verification.
./install.sh --check
pytest -q
6. Run the Stage 1 Demonstration
From the project root, run:
./run_demo.sh
The existing Stage 1 demonstration script remains available as an alternative:
./scripts/run_stage1_demo.sh
7. Headless Execution
For environments without a graphical display, run the headless demonstration:
./run_demo.sh --headless
8. Expected Demonstration
•	Four UAVs are launched in the simulated disaster-response environment.
•	The swarm surveys assigned Points of Interest (PoIs).
•	The system maintains end-to-end communication with the Ground Control Station (GCS).
•	UAVs can act as communication relays and the network can be reconfigured after communication degradation or relay failure.
•	A newly introduced high-priority PoI can be handled by the swarm.
•	A battery-fault scenario causes the affected UAV to return toward home when the fault occurs before mission completion, while remaining tasks can be reassigned.
•	Collision avoidance and geofence constraints are monitored.
•	The dashboard and final mission metrics can be used to observe the simulation.
9. Dashboard
When running the graphical demonstration, the project dashboard is available at:
http://localhost:8080
13. Quick Start
For an evaluator who already has the required Ubuntu environment:
unzip UAV-X_Resilient_BVLOS_Swarm_Stage1_Source.zip
cd UAV-X_Resilient_BVLOS_Swarm_Stage1_Source
./install.sh
./run_demo.sh


