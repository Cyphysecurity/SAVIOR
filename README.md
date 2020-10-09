# SAVIOR: Securing Autonomous Vehicles with Robust Physical Invariants
This repository contains the implementation of SAVIOR on an aerial and ground vehicle. Each folder contains the specific files needed for each vehicle. On the aerial vehicles, the main controller is PX4 while on the ground vehicle the main controller is ROS Kinetic Kame.

## Getting Started

### Installing
Clone the current version of the project:
```
git clone https://github.com/Cyphysecurity/SAVIOR.git
```

Obtain all the submodules:
```
git submodule update --init --recursive
```

### Setting up the environment
Become a member of the group dialout:
```
sudo usermod -a -G dialout $USER
```
Download the script "ubuntu_sim_nuttx.sh" from the following link and run it (https://raw.githubusercontent.com/PX4/Devguide/v1.9.0/build_scripts/ubuntu_sim_nuttx.sh):
```
chmod +x ubuntu_sim_nuttx.sh
./ubuntu_sim_nuttx.sh
```

### Installing dependencies
Since once of the dependencies requires Python version 3.5 or above, make sure you use a version of Python that satisfies this requirement.

Install pip3 if your distribution did not come with it:
```
sudo apt install python3-pip
```
Then, proceed to install the dependencies:
```
sudo apt-get install python3-jinja2

sudo apt-get install python3-empy

sudo pip3 install catkin_pkg

sudo pip3 install numpy toml	(make sure you are running python 3.5 or above)

sudo pip3 install pyyaml
```
In order to compile for Intel Aero, we need to download and install the compiler for ARM Cortex processors. The compiler can be found here: https://packages.ubuntu.com/xenial/gcc-arm-none-eabi

Detailed instructions are also found in: https://dev.px4.io/v1.9.0/en/setup/dev_env_linux.html.

### Compile modules for simulation
Simply run the make on the Firmware folder:
```
make
```
The make command will by default build the code for the px4_sitl_default configuration.

### Compile firmware for Intel Aero:
Run the following command:
```
make intel_aerofc-v1_default
```
The make command will build the code for the Intel Aero platform.

### Acknowledgments

We thank the anonymous reviewers for their insightful com- ments. This work was partially supported by National Sci- ence Foundation (NSF) Awards 1834215, 1834216, 1929410, 1931573 and the Air Force Office of Scientific Research under award number FA9550-17-1-0135.

