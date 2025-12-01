# LoRa-SDR_Chat
Node-RED and GNURadio Scripts for "Developing an SDR-Based LoRa Communication System with a Web-Based Monitoring and Control Interface for Performance Analysis", ICOIN 2026
## Authors: Hung Viet Nguyen<sup>1</sup>, Hieu Minh Vi<sup>1</sup>, Duong Quy Nguyen<sup>1</sup>, Thanh Tu Duong<sup>1</sup>, Kim Khoa Nguyen<sup>2</sup>, Le Van Hau<sup>2</sup>
### <sup>1</sup>Faculty of Telecommunications 1, Posts and Telecommunications Institute of Technology, Hanoi, Vietnam
### <sup>2</sup>Department of Electrical Engineering, Ecole de technologie superieure, University of Quebec, Quebec, Canada
## Installation
### Backend
Firstly, we affirm to publicly use the source code [tapparelj/gr-lora_sdr](https://github.com/tapparelj/gr-lora_sdr) combined with the mqtt source code we built.
- Download the latest release of conda:
  - Linux PC:
  	```sh
  	wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
  	```
  - Raspberry Pi:
  	```sh
  	wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-aarch64.sh
  	```
  - Now run the downloaded file which is the Anaconda Installer script
	```sh
	bash Miniconda3-latest-Linux-x86_64.sh
	```
  - And reload the Shell
	```sh
	source ~/.bashrc
	```
  - Create environment to install all the dependencies of the module
  ```sh
	conda create -n grlora python=3.10
	```
- Start the conda environment GNU Radio 3.10 you just created
  ```sh
	conda activate grlora
	```
- Install the module from the anaconda channel [tapparelj](https://anaconda.org/tapparelj/gnuradio-lora_sdr) with:
	```sh
	conda install -c tapparelj -c conda-forge gnuradio-lora_sdr
	```
Next, the out of tree module gr-mqtt can be installed from source
- Clone our repository
  	```sh
	git clone https://github.com/Brauuwu/LoRa-SDR_Chat.git
	```
- Go to the cloned repository
	```sh
	cd LoRa-SDR_Chat/GNU_Radio/gr-mqtt
	```
- To build the code, create an appropriate folder and go in it:
	```sh
	mkdir build
	cd build
	```
- Finally compile the custom GNU Radio blocks.
	```sh
	make install ..
	```
### Frontend
- Install [Node-RED](https://nodered.org/docs/getting-started/raspberrypi)
- Run Node-RED and download nodes `node-red-dashboard` and `node-red-node-mysql` in Manage palletes or use this command
	```sh
	npm install node-red-dashboard node-red-node-mysql
	```
- Import [flow.js](https://github.com/Brauuwu/LoRa-SDR_Chat/blob/main/Node-RED/flows.json) into Node-RED
