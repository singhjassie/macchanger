# macchanger
Python script to change macaddress of device's wifi insterface

# Features
* **Parser** - The script uses optparse module with help of which we can parse the argument from terminal before running script.If you forget to parse argument it will ask at runtime.
* **Random MacAddress** - The script will automatically genrate a valid random mac address if not passed manually.
* **Verify** - The script will verify if mac address get changed and print the new mac address. It uses re(regular expression) to search current mac address and match it with previous mac address to verify.

# Installation
1. Clone the package using git. You can also download zip file from github repository and then extract it.
```sh
git clone http://github.com:singhjassie/macchanger
```
2. Nevigate into the directory
```
cd macchanger
```
3. Make script executable to easily run script
```
chmod +x macchanger.py
```
> **Note**
>
>You first have to switch to super user before running the script.
# Usage
Enter the following command to see usage help
```
./macchanger --help
```
```sh
Usage: macchanger.py [options]

Options:
  -h, --help            show this help message and exit
  -m MAC_ADDRESS, --mac=MAC_ADDRESS
                        To give the new mac address
  -i INTERFACE, --interface=INTERFACE
                        To give the interface name
```

# Adding script to linux environment
Everytime you need to run the script you have to navigate to the macchanger directory and then type ./macchanger to run this command. This may be very overwhelming when you are in hurry. 
<br>
To avoid the problem, you may do so,
```
cp macchanger /usr/bin/macchanger
```
Now you can run the script from anywhere in terminal without "./" as below,
```
macchanger [options]
```
You can add command (macchanger -i \<interface-name>) script to the startup menu so that every time you turn on your device it will automatically. But this will not be helpful if you restart your Network manager.<br>
Alternatively, you can add this command to your wpasupplicant script (in case of wireless interface).
for example,
```sh
echo "macchanger -i wlan0" >> /etc/network/if-down.d/wpasupplicant
```
You may have different location wpasupplicant file on your machine. After adding this command to wpasupplicant you don't need to run this command manually. It will randomize the mac address every time NetworkManager restart.
<br>
Now you will be anonymously in public wifi. You can impersonate someone in same wireless network by changing MacAddress. To spoof someone on your wireless network you can use [this tool](http://github.com:singhjassie/networkspoofer).
<br>To get more security tools click [here](https://github.com/singhjassie?tab=repositories)