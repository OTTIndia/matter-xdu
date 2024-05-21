Certainly! Here is a streamlined step-by-step guide for installing ESP-Matter on an Ubuntu Linux operating system:
Step 1: Update Your System

Ensure your system is up-to-date:

sh

sudo apt-get update
sudo apt-get upgrade

Step 2: Install Required Dependencies

Install the necessary packages for building and running ESP-Matter:

sh

sudo apt-get install git gcc g++ pkg-config libssl-dev libdbus-1-dev \
     libglib2.0-dev libavahi-client-dev ninja-build python3-venv python3-dev \
     python3-pip unzip libgirepository1.0-dev libcairo2-dev libreadline-dev

Step 3: Clone the ESP-Matter Repository

Create a directory for your projects and clone the ESP-Matter repository:

sh

mkdir -p ~/Projects
cd ~/Projects
git clone --depth 1 https://github.com/espressif/esp-matter.git

Step 4: Initialize Submodules

Navigate into the repository and initialize the submodules:

sh

cd esp-matter
git submodule update --init --depth 1

Step 5: Checkout Additional Submodules

Go to the connectedhomeip directory and checkout additional submodules:

sh

cd connectedhomeip/connectedhomeip
./scripts/checkout_submodules.py --platform esp32 linux --shallow

Step 6: Run the Installation Script

Return to the root of the esp-matter directory and run the installation script:

sh

cd ~/Projects/esp-matter
./install.sh

Step 7: Activate the Python Virtual Environment

Navigate back to the connectedhomeip directory and activate the Python virtual environment:

sh

cd connectedhomeip/connectedhomeip
source scripts/activate.sh

Step 8: Verify the Installation

List the contents of the output directory to verify the build:

sh

ls -al out/host

By following these steps, you should be able to successfully install ESP-Matter on your Ubuntu Linux system.
