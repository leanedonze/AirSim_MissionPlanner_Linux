<h2><p align="center"><b><ins> AirSim, UE4, Ardupilot and MissionPlanner </ins></b></p></h2>

<br>

---

<br>

- Figure out how to use AirSim in UE4 with Ardupilot and MissionPlanner
- UE4 with AirSim and Ardupilot is running on a Linux machine
- MissionPlanner is running on a Windows machine (could theoretically run on a Linux machine, but crahes often)

<br>

---

<br>

<h3><ins> Linux machine </ins></h3>

<br>

- Launch your UE4 project.
	```
	cd ~/UnrealEngine/Engine/Binaries/Linux
	```

	```
	./UE4Editor /home/leane/AirSim/Unreal/Environments/BlocksPlayground/Blocks.uproject
	```

<br>

- Press the "Play button" (UE4 will freeze until you launch Ardupilot).

<br>

- Launch Ardupilot. Replace "windows_ip" by the IP of your machine running Windows. Be careful, ```sim-port-in``` and ```sim-port-out``` have to be consistent with the JSON file used by UE4.
	```
	sim_vehicle.py -j 4 -v ArduCopter -f airsim-copter --console -C "--out=udpout:windows_ip:14550" -A "--sim-port-in=9003 --sim-port-out=9002" --console
	```

<br>

---

<h3><ins> Windows machine </ins></h3>

- Launch MissionPlanner
- On the top right corner, choose ```UDP```, ```115200``` and put ```windows_ip```
- A prompt will appear asking for the port, use ```14550``` (consistent with the linux command to launch Ardupilot)
