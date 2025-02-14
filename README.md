# v2ray Server with Interface

For this you need two servers, one in Iran and the other outside of Iran.</br>
you can google it or using websites like [Sindad](https://sindad.com/), [WebRamz](https://www.webramz.com/) or any other services you like, just make sure that your VPS is located in <strong>America</strong></br>
Note: You don't need anything fancy, even the most basic and simple plans of the VPS's will do the magic.
<hr>
</br>
Your server inside Iran will act as a router. It's only job is to route traffic from within the country to the main server (non-IR) which hosts the actual V2ray Server. </br>
All commands are base on debian-based linux distros. e.g. Ubuntu.</br></br>
Share it with your loved ones</br></br>
</br></br>
Let's get started.</br></br>

## on Your non-IR Server</br>

#### 1. Update & Upgrade the packages </br>
```shell script
sudo apt update && apt upgrade -y
``` 
#### 2. Install curl on your server </br>
```shell script
sudo apt install curl -y
```
#### 3. Run this command </br>
```shell script
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```
#### 4. Login to admin panel </br>
```shell script
YOUR_SERVER_IP_ADDRESS:54321
```
You Can login to your Panel with the following credentials. </br>
Username `admin` Password `admin`</br></br>
The app is in chinese, so use google chrome as your web browser, right click on the page and choose `translate to English`</br>
After you loged in into your server natigate to `panel setting, user setting` and change your admin user `password`</br></br></br>
Only use the following command if you have slow connections and got disconnected repeatedly </br>
#### 5. If you have slow connections </br>
```shell script
wget -N --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && bash bbr.sh
```
<hr>
That's it for your non-IR Server, now let's setup you IR Server.</br></br>

## on Your IR Server</br>

#### 1. Update & upgrade the packages </br>
```shell script
sudo apt update && apt upgrade -y
``` 
#### 2. Run the following commands </br>
First change the `YOUR_IR_SERVER_IP` & `YOUR_NON_IR_SERVER_IP`</br>
```shell script
sysctl net.ipv4.ip_forward=1
``` 
```shell script
iptables -t nat -A PREROUTING -p tcp --dport 22 -j DNAT --to-destination YOUR_IR_SERVER_IP
``` 
```shell script
iptables -t nat -A PREROUTING -j DNAT --to-destination YOUR_NON_IR_SERVER_IP
``` 
```shell script
iptables -t nat -A POSTROUTING -j MASQUERADE
``` 
Only use the following command if you have slow connections and got disconnected repeatedly </br>
#### 3. If you have slow connections </br>
```shell script
wget -N --no-check-certificate https://github.com/teddysun/across/raw/master/bbr.sh && chmod +x bbr.sh && bash bbr.sh
```

Now head over to the `apps` directory for instructions on how to connect.
</br></br>
Just in case you want to support me, I'd realy appriciate it.</br></br>

TRC20 `TT2AMeebAUGFcG9jLPA49xN1eMCyDekz6c` </br>

ERC20 `0x9A6471A8d01A66e81433d97aF3e1288f7C2E6a7b`

