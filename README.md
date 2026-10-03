# Optimizing-Generative-AI-on-Arm-Processors - Lab files from Optimizing Generative AI on Arm Processors course. 

The original lab files have some issues when running cmake and make commands. I have updated these lab files with updated working commands. for lab3 since i do not have raspberry pi device, i have modified it to include only graviton instructions. for lab1 we can execute all commands on graviton instance - there is no need for a raspberry pi device (good if you have one - then you see how it actually works on edge device)

- For labs, make sure to complete following steps on graviton instance before proceeding to jupyter notebooks:

Step 1
-----------
- Clone this repository:
git clone https://github.com/arm-university/AI-on-Arm/
- Change directory and run the server setup script:
```
cd AI-on-Arm
./setup_graviton.sh
source graviton_env/bin/activate 
jupyter lab --> this will give URL to connect to jupyter labs from localhost something liek http://127.0.0.1:8888/lab?token=<alphanumericcode>
```
Step 2
--------
- Make sure that your ssh config file is updated with current ip address of graviton host as these can change across reboots

example:
```
Host my-hostname
    HostName v.x.y.z ##ip address
    User ubuntu
    IdentityFile <path to xx.pem file>
    IdentitiesOnly yes
    Port 22
```
- Open a windows powershell and run the following command to open tunneling between graviton host and your windows machine
```
ssh -N -L 8888:127.0.0.1:8888 my-hostname
```
Step 3
--------

- open your browser and navigate to http://127.0.0.1:8888/lab?token=<alphanumericcode> --> this will load jupyterlab environment from graviton host.
- upload the lab files above to root location (if you want you can save original lab files first)
