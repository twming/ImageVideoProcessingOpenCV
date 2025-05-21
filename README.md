# ImageVideoProcessingOpenCV

### Activity : Raspberry Pi Installation and Setup
1. Go to https://www.raspberrypi.com/software/, download Raspberry Pi Imager.

<img src="https://github.com/twming/Computer_Vision_NN_Model/blob/Pi5/img/rasp-imager-download.png" alt="ImagerDownload" width="600">

2. Install Ubuntu Desktop 24.04.2 LTS (64-Bit), it will take about 20 mins to clone the SDCard (Other general purpose OS -> Ubuntu -> Ubuntu Desktop 24.04.2 LTS (64-Bit) )
<img src="https://github.com/twming/Computer_Vision_NN_Model/blob/Pi5/img/rasp-imager.png" alt="Imager" width="300">
<img src="https://github.com/twming/Computer_Vision_NN_Model/blob/Pi5/img/rasp-ubuntu.png" alt="Ubuntu" width="300">

3. System Configuration: Insert the cloned SDCard to RaspberryPi4/5, boot up the system, you need to setup below:

- Language: English
- Keyboard Layout: English(US)
- Wireless: SSID/Password
- Country/Zone: Singapore
- username/password: pi/pi (Require my password to log in)


4. Login to RaspberryPi4/5, open terminal, install XRDP remote access
<img src="https://github.com/twming/Computer_Vision_NN_Model/blob/Pi5/img/terminal.png" alt="Terminal" width="500">

```
sudo apt install -y ubuntu-gnome-desktop
sudo apt install -y xrdp
sudo adduser xrdp ssl-cert
sudo ufw enable
sudo ufw allow 3389/tcp
sudo ufw reload
```

5. Check your Raspberry Pi IP address
```
ip addr
```

> [!IMPORTANT] 
> - Please take note of the IP Address, as you need it to remote login after reboot

6. Create a py312 environment and activate it
```
sudo apt update
sudo apt install -y software-properties-common git curl
sudo apt install -y python3.12-venv
cd ~
python3 -m venv py312
source ~/py312/bin/activate
```

7. Install OpenCV, Matplotlib and Jupyter IDE
```
pip3 install opencv-python matplotlib jupyter argparse easydict
```

8. Reboot your Raspberry Pi
```
sudo poweroff
```

### Activity : Install YOLO5 on Raspberry Pi
```
cd ~
git clone https://github.com/ultralytics/yolov5  
cd yolov5
pip install -r requirements.txt
```
### Activity : Run YOLO5 on Raspberry Pi
```
cd ~/yolov5
python detect.py --source 0
```

